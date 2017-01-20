---
title: "/RELEASE (Pr&#252;fsumme festlegen)"
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
  - "/release"
  - "VC.Project.VCLinkerTool.SetChecksum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RELEASE (Linkeroption)"
  - "Prüfsumme festlegen"
  - "RELEASE (Linkeroption)"
  - "-RELEASE (Linkeroption)"
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /RELEASE (Pr&#252;fsumme festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RELEASE  
```  
  
## Hinweise  
 Die \/RELEASE\-Option legt die Prüfsumme im Header einer EXE\-Datei fest.  
  
 Das Betriebssystem benötigt die Prüfsumme für Gerätetreiber.  Legen Sie die Prüfsumme für Releasebuilds der Gerätetreiber fest, um die Kompatibilität mit zukünftigen Betriebssystemen zu gewährleisten.  
  
 Die Option **\/RELEASE** wird standardmäßig festgelegt, wenn die Option [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) angegeben ist.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Prüfsumme setzen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)