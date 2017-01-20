---
title: "/WINMD (Windows-Metadaten generieren)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadata"
dev_langs: 
  - "C++"
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /WINMD (Windows-Metadaten generieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aktiviert die Generierung einer Windows \(.winmd Runtime\-Metadaten\).  
  
```  
  
/WINMD[:{NO|ONLY}]  
```  
  
## Hinweise  
 \/WINMD  
 Die Standardeinstellung für [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] \- Apps.  Der Linker generiert die binäre ausführbare Datei und die .winmd\-Metadatendatei.  
  
 \/WINMD:NO  
 Der Linker generiert nur die binäre ausführbare Datei, jedoch keine WINMD\-Datei.  
  
 \/WINMD:ONLY  
 Der Linker generiert nur die WINMD\-Datei, nicht jedoch die binäre ausführbare Datei.  
  
 Standardmäßig verfügt der Ausgabedateiname das Formular `binaryname`.winmd.  Um einem anderen Dateinamen anzugeben, verwenden Sie die Option [\/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie den Ordner **Linker** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Windows\-Metadaten** aus.  
  
4.  Im Dropdown\-Listenfeld **Windows\-Metadaten generieren** wählen Sie die Option aus, die Sie suchen.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)