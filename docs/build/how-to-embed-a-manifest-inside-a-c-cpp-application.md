---
title: 'Vorgehensweise: Einbetten eines Manifests in einer C/C++-Anwendung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a759533a8e88ef05e3660e0e9b36525df378334
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369051"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Gewusst wie: Einbetten eines Manifests in eine C/C++-Anwendung
Es wird empfohlen, dass eine C/C++-Anwendung (oder eine Bibliothek) ist das Manifest in die endgültige Binärdatei eingebettet werden, da so gewährleistet ist richtig Laufzeitverhalten in den meisten Szenarien. Standardmäßig [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] versucht, die das Manifest einbetten, wenn sie ein Projekt aus Quelldateien erstellt; finden Sie unter [Manifesten in Visual Studio](../build/manifest-generation-in-visual-studio.md) für Weitere Informationen. Wenn eine Anwendung mithilfe von Nmake erstellt wird, sind jedoch einige Änderungen an vorhandenen Makefile erforderlich. Dieser Abschnitt veranschaulicht das Ändern von vorhandenen Makefiles um automatisch das Manifest in die endgültige Binärdatei eingebettet.  
  
## <a name="two-approaches"></a>Zwei Ansätze  
 Es gibt zwei Möglichkeiten, die das Manifest in einer Anwendung oder eine Bibliothek einbetten.  
  
-   Wenn Sie einen inkrementellen Build nicht ausführen, können Sie direkt das Manifest mit einer ähnlich der folgenden Befehlszeile als Postbuildschritt einbetten:  
  
     **MT.exe-manifest MyApp.exe.manifest-outputresource:MyApp.exe;1**  
  
     oder  
  
     **MT.exe-manifest MyLibrary.dll.manifest-outputresource:MyLibrary.dll;2**  
  
     (1 für eine EXE-Datei für eine DLL 2).  
  
-   Wenn Sie einen inkrementellen Build durchführen, wird die Ressource direkt zu bearbeiten, wie hier gezeigt inkrementellen Buildvorgangs deaktivieren und dazu führen, dass eine vollständige Neuerstellung; aus diesem Grund sollte ein anderer Ansatz gewählt werden:  
  
    -   Verknüpfen Sie die Binärdatei, um die Datei MyApp.exe.manifest zu generieren.  
  
    -   Konvertieren Sie das Manifest in einer Ressourcendatei gespeichert.  
  
    -   Verknüpfen Sie erneut (inkrementell) die Manifestressource in die Binärdatei eingebettet.  
  
 Die folgenden Beispiele zeigen, wie Makefiles enthält beide Verfahren geändert werden.  
  
## <a name="makefiles-before"></a>Makefiles (vorher)  
 Betrachten Sie das Skript Nmake für MyApp.exe, eine einfache Anwendung erstellt, die aus einer Datei ein:  
  
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
  
 Wenn dieses Skript mit Visual C++ unverändert ausgeführt wird, erstellt es MyApp.exe erfolgreich. Außerdem erstellt der externe Manifestdatei MyApp.exe.manifest, für die Verwendung durch das Betriebssystem auf abhängige Assemblys zur Laufzeit laden.  
  
 Nmake-Skript für MyLibrary.dll sieht sehr ähnlich:  
  
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
 Zum Erstellen über eingebettet, Manifeste, die Sie haben vier kleine Änderungen an den ursprünglichen Makefiles vornehmen. Für die MyApp.exe-Makefile:  
  
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
  
 Für die MyLibrary.dll-Makefile:  
  
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
  
 Enthält nun zwei Dateien, die die eigentliche Arbeit, makefile.inc makefile.targ.inc und.  
  
 Erstellen Sie makefile.inc, und kopieren Sie das folgende hinein:  
  
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
  
 Jetzt erstellen Sie makefile.targ.inc, und kopieren Sie das folgende hinein:  
  
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