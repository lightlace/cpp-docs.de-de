---
title: "/Qpar (Automatische Parallelisierung) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration"
dev_langs: 
  - "C++"
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Qpar (Automatische Parallelisierung)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die [Automatische Parallelisierung](../../parallel/auto-parallelization-and-auto-vectorization.md)\-Funktion des Compilers, die Schleifen im Code automatisch zu parallelisieren.  
  
## Syntax  
  
```  
/Qpar  
```  
  
## Hinweise  
 Wenn der Compiler automatisch Schleifen im Code parallelisiert, überträgt der Berechnung zu mehreren Prozessorkernen.  Eine Schleife parallelisiert wird, wenn der Compiler bestimmt, dass sie gültig ist, dies nachzuholen und dass Parallelisierung Leistung verbessert wird.  
  
 Die `#pragma loop()`\-Direktive sind verfügbar, den Optimierer helfen, bestimmte Schleifen zu parallelisieren.  Weitere Informationen finden Sie unter [Schleife](../../preprocessor/loop.md).  
  
 Informationen darüber, wie Sie die für die automatische Parallelisierung, finden Sie unter [\/Qpar\-report \(Auto\-Parallelizer\-Berichtsebene\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).  
  
### So die Compileroption \/Qpar\- in Visual Studio fest  
  
1.  In **Projektmappen\-Explorer** öffnen Sie das Kontextmenü für das Projekt und dann **Eigenschaften** aus.  
  
2.  Im Dialogfeld **Eigenschaftenseiten** unter **C\/C\+\+**, wählen Sie **Befehlszeile** aus.  
  
3.  Im Feld **Zusätzliche Optionen** geben Sie `/Qpar` ein.  
  
### So die \/Qpar\- Compileroption programmgesteuert fest  
  
-   Verwenden Sie das Codebeispiel in <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/Q\-Optionen \(Operationen auf niedriger Ebene\)](../../build/reference/q-options-low-level-operations.md)   
 [\/Qpar\-report \(Auto\-Parallelizer\-Berichtsebene\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\#pragma loop\(\)](../../preprocessor/loop.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/?LinkId=263662)