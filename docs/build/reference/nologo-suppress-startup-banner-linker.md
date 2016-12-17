---
title: "/NOLOGO (Startbanner unterdr&#252;cken) (Linker)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.SuppressStartupBanner"
  - "/nologo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOLOGO (Linkeroption)"
  - "Banner, Unterdrücken des Starts"
  - "Copyrightmeldung"
  - "NOLOGO (Linkeroption)"
  - "-NOLOGO (Linkeroption)"
  - "Startbanner unterdrücken (Linkeroption)"
  - "Versionsnummern, Verhindern der Linkeranzeige"
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# /NOLOGO (Startbanner unterdr&#252;cken) (Linker)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOLOGO  
```  
  
## Hinweise  
 Die \/NOLOGO\-Option verhindert die Anzeige der Copyrightmeldung und der Versionsnummer.  
  
 Sie unterdrückt auch die Wiedergabe von Befehlsdateien.  Weitere Einzelheiten finden Sie unter [LINK\-Befehlsdateien](../../build/reference/link-command-files.md).  
  
 Standardmäßig werden diese Informationen vom Linker an das Ausgabefenster gesendet.  In der Befehlszeile werden sie an die Standardausgabe gesendet und können in eine Datei umgeleitet werden.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Diese Option sollte nur in der Befehlszeile verwendet werden.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Diese Linkeroption kann nicht über ein Programm geändert werden.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)