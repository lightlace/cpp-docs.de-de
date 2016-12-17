---
title: "Gewusst wie: Einbetten eines Manifests in eine C/C++-Anwendung"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Einbetten von Manifesten"
  - "Makefiles, Aktualisieren zum Einbetten von Manifesten"
  - "Manifeste [C++]"
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Gewusst wie: Einbetten eines Manifests in eine C/C++-Anwendung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es wird empfohlen, bei C\/C\+\+\-Anwendungen \(oder Bibliotheken\) das Manifest in die endgültige Binärdatei einzubetten, weil dadurch in den meisten Szenarien ein ordnungsgemäßes Laufzeitverhalten sichergestellt wird.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] versucht standardmäßig, beim Erstellen eines Projekts aus Quelldateien das Manifest einzubetten. Weitere Informationen finden Sie unter [Manifestgenerierung in Visual Studio](../build/manifest-generation-in-visual-studio.md).  Wenn eine Anwendung jedoch mit nmake erstellt wird, sind einige Änderungen am vorhandenen Makefile erforderlich.  Dieser Abschnitt veranschaulicht, wie vorhandene Makefiles geändert werden müssen, um das Manifest automatisch in die endgültige Binärdatei einzubetten.  
  
## Zwei Ansätze  
 Es gibt zwei Möglichkeiten, das Manifest in eine Anwendung oder Bibliothek einzubetten.  
  
-   Wenn Sie keinen inkrementellen Build durchführen, können Sie das Manifest direkt einbetten, indem Sie eine Befehlszeile wie die folgende als Postbuildschritt verwenden:  
  
     **mt.exe –manifest MyApp.exe.manifest \-outputresource:MyApp.exe;1**  
  
     oder  
  
     **mt.exe –manifest MyLibrary.dll.manifest \-outputresource:MyLibrary.dll;2**  
  
     \(1 für eine EXE\-Datei, 2 für eine DLL\-Datei\)  
  
-   Wenn Sie einen inkrementellen Build durchführen, wird bei einer direkten Bearbeitung der Ressource, wie hier gezeigt, der inkrementelle Buildvorgang deaktiviert und eine vollständige Neuerstellung durchgeführt. Aus diesem Grund sollte ein anderer Ansatz gewählt werden:  
  
    -   Verknüpfen Sie die Binärdatei, um die Datei MyApp.exe.manifest zu generieren.  
  
    -   Konvertieren Sie das Manifest in eine Ressourcendatei.  
  
    -   Stellen Sie die Verknüpfung \(inkrementell\) wieder her, um die Manifestressource in die Binärdatei einzubetten.  
  
 Die folgenden Beispiele zeigen, wie Makefiles geändert werden, um beide Methoden einzubinden.  
  
## Makefiles \(vorher\)  
 Betrachten Sie das Skript nmake für MyApp.exe, eine einfache, aus einer Datei erstellte Anwendung:  
  
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
  
 Wenn dieses Skript mit Visual C\+\+ unverändert ausgeführt wird, wird "MyApp.exe" erfolgreich erstellt.  Es erstellt außerdem die externe Manifestdatei MyApp.exe.manifest, die vom Betriebssystem zur Laufzeit zum Laden abhängiger Assemblys verwendet wird.  
  
 Das nmake\-Skript für MyLibrary.dll sieht sehr ähnlich aus:  
  
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
  
## Makefiles \(nachher\)  
 Für einen Buildvorgang mit eingebetteten Manifesten müssen Sie vier kleine Änderungen an den ursprünglichen Makefiles vornehmen.  Für die MyApp.exe\-Makefile:  
  
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
  
 Für die MyLibrary.dll\-Makefile:  
  
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
  
 Die Makefile enthält nun zwei Dateien, die die eigentliche Arbeit übernehmen: makefile.inc und makefile.targ.inc.  
  
 Erstellen Sie makefile.inc, und fügen Sie den folgenden Code ein:  
  
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
  
 Erstellen Sie nun makefile.targ.inc, und fügen Sie den folgenden Code ein:  
  
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
  
## Siehe auch  
 [Manifestgenerierung für C\/C\+\+\-Programme](../build/understanding-manifest-generation-for-c-cpp-programs.md)