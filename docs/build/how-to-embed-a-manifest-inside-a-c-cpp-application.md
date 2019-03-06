---
title: 'Vorgehensweise: Einbetten eines Manifests in eine C/C++-Anwendung'
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
ms.openlocfilehash: b1bff23c91b465d697cc52a2b893ece5be3764b1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412899"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Vorgehensweise: Einbetten eines Manifests in eine C/C++-Anwendung

Es wird empfohlen, dass eine C/C++-Anwendung (oder Bibliothek) haben das Manifest in die endgültige Binärdatei eingebettet werden, da so gewährleistet, dass richtige Laufzeitverhalten führen konnte in den meisten Szenarien. Standardmäßig versucht Visual Studio das Manifest eingebettet, wenn es sich um ein Projekt aus Quelldateien erstellt. finden Sie unter [Manifest Generation in Visual Studio](../build/manifest-generation-in-visual-studio.md) für Weitere Informationen. Wenn eine Anwendung mithilfe von Nmake erstellt wird, gibt jedoch einige Änderungen an der vorhandenen Makefile erforderlich. In diesem Abschnitt wird veranschaulicht, wie vorhandene Makefiles zum Einbetten von des Manifests in die endgültige Binärdatei automatisch geändert wird.

## <a name="two-approaches"></a>Zwei Ansätze

Es gibt zwei Möglichkeiten, um das Manifest in eine Anwendung oder Bibliothek eingebettet.

- Wenn Sie einen inkrementellen Build nicht ausführen können Sie direkt über die Befehlszeile etwa wie folgt einen Postbuildschritt Manifest einbetten:

   **mt.exe -manifest MyApp.exe.manifest -outputresource:MyApp.exe;1**

   oder

   **mt.exe -manifest MyLibrary.dll.manifest -outputresource:MyLibrary.dll;2**

   (1 für eine EXE-Datei, 2 für eine DLL-Datei).

- Wenn Sie einen inkrementellen Build durchführen, wird die Ressource direkt bearbeiten, wie hier gezeigt Deaktivieren des inkrementellen Buildvorgangs und dazu führen, dass eine vollständige Neuerstellung; aus diesem Grund sollte ein anderer Ansatz gewählt werden:

   - Verknüpfen Sie die Binärdatei, um die MyApp.exe.manifest-Datei zu generieren.

   - Konvertieren Sie das Manifest in eine Ressourcendatei.

   - Verknüpfen Sie erneut (inkrementell) um die Manifestressource in die Binärdatei einzubetten.

Die folgenden Beispiele zeigen, wie Makefiles, um beide Verfahren integrieren geändert wird.

## <a name="makefiles-before"></a>Makefiles (vorher)

Betrachten Sie das Nmake-Skript für MyApp.exe, eine einfache Anwendung erstellt, die aus einer Datei ein:

```
# build MyApp.exe
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
```

Wenn dieses Skript mit Visual C++ unverändert ausgeführt wird, erstellt es MyApp.exe erfolgreich. Außerdem erstellt die externe Manifestdatei MyApp.exe.manifest, für die Verwendung durch das Betriebssystem abhängige Assemblys zur Laufzeit geladen werden.

Das Nmake-Skript für MyLibrary.dll sieht ähnlich aus:

```
# build MyLibrary.dll
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
```

## <a name="makefiles-after"></a>Makefiles (nachher)

Die Erstellung mit eingebettet, Manifeste, die Sie haben vier kleine Änderungen an den ursprünglichen Makefiles vornehmen. Für die Makefile MyApp.exe:

```
# build MyApp.exe
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_EXE)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

Für die Makefile MyLibrary.dll:

```
# build MyLibrary.dll
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_DLL)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

Enthält nun zwei Dateien, die die eigentliche Arbeit, makefile.inc und makefile.targ.inc ausführen.

Erstellen Sie makefile.inc, und fügen Sie die folgenden:

```
# makefile.inc -- Include this file into existing makefile at the very top.

# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
_VC_MANIFEST_INC=1
_VC_MANIFEST_BASENAME=__VC90.Debug

!else
CPPFLAGS=$(CPPFLAGS) /MD
_VC_MANIFEST_INC=0
_VC_MANIFEST_BASENAME=__VC90

!endif

####################################################
# Specifying name of temporary resource file used only in incremental builds:

!if "$(_VC_MANIFEST_INC)" == "1"
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res
!else
_VC_MANIFEST_AUTO_RES=
!endif

####################################################
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:

!if "$(_VC_MANIFEST_INC)" == "1"

#MT_SPECIAL_RETURN=1090650113
#MT_SPECIAL_SWITCH=-notify_resource_update
MT_SPECIAL_RETURN=0
MT_SPECIAL_SWITCH=
_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \
link $** /out:$@ $(LFLAGS)

!else

_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1

!endif

####################################################
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:

!if "$(_VC_MANIFEST_INC)" == "1"

_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \
    $(_VC_MANIFEST_BASENAME).auto.rc \
    $(_VC_MANIFEST_BASENAME).auto.manifest

!else

_VC_MANIFEST_CLEAN=

!endif

# End of makefile.inc
####################################################
```

Nun erstellen Sie makefile.targ.inc aus, und fügen Sie die folgenden:

```
# makefile.targ.inc - include this at the very bottom of the existing makefile

####################################################
# Commands to generate initial empty manifest file and the RC file
# that references it, and for generating the .res file:

$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc

$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest
    type <<$@
#include <winuser.h>
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"
<< KEEP

$(_VC_MANIFEST_BASENAME).auto.manifest :
    type <<$@
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>
</assembly>
<< KEEP

# end of makefile.targ.inc
```

## <a name="see-also"></a>Siehe auch

[Manifestgenerierung für C/C++-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)
