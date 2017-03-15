---
title: "/NXCOMPAT (kompatibel mit Datenausf&#252;hrungsverhinderung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/NXCOMPAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NXCOMPAT (Linkeroption)"
  - "NXCOMPAT (Linkeroption)"
  - "-NXCOMPAT (Linkeroption)"
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /NXCOMPAT (kompatibel mit Datenausf&#252;hrungsverhinderung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass eine ausführbare Datei mit der Windows\-Funktion zur Datenausführungsverhinderung kompatibel ist.  
  
## Syntax  
  
```  
/NXCOMPAT[:NO]  
```  
  
## Hinweise  
 Standardmäßig ist **\/NXCOMPAT** aktiviert.  
  
 **\/NXCOMPAT:NO** kann verwendet werden, um eine ausführbare Datei explizit als mit der Datenausführungsverhinderung inkompatibel zu kennzeichnen.  
  
 Weitere Informationen über die Datenausführungsverhinderung finden Sie in diesen Artikeln:  
  
-   [Eine ausführliche Beschreibung der Funktion der Datenausführungsverhinderung \(DEP\) erhalten Sie unter](http://go.microsoft.com/fwlink/?LinkID=157771) auf der Hilfe\- und Supportwebsite von Microsoft.  
  
-   [Datenausführungsverhinderung](http://go.microsoft.com/fwlink/?LinkID=157770) auf der MSDN\-Website  
  
-   [Datenausführungsverhinderung \(Windows Embedded\)](http://go.microsoft.com/fwlink/?LinkID=157768) auf der MSDN\-Website  
  
### So legen Sie diese Linkeroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)