---
title: "/Qpar-report (Auto-Parallelizer-Berichtsebene) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /Qpar-report (Auto-Parallelizer-Berichtsebene)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die Berichtsfunktion des Compilers [Auto\-Parallelizer](../../parallel/auto-parallelization-and-auto-vectorization.md) und gibt die Ebene der Informationsmeldungen für die Ausgabe während der Kompilierung an.  
  
## Syntax  
  
```  
/Qpar-report:{1}{2}  
```  
  
## Hinweise  
 **\/Qpar\-report:1**  
 Gibt eine Informationsmeldung für Schleifen an, die parallel ausgeführt werden.  
  
 **\/Qpar\-report:2**  
 Gibt eine Informationsmeldung für Schleifen an, die parallel ausgeführt werden und auch für Schleifen, die nicht, zusammen mit einen Ursachencode parallel ausgeführt werden.  
  
 Nachrichten werden an Stdout gesendet.  Wenn keine Informationsmeldungen angezeigt werden, enthält der Code keine Schleifen oder die Berichterstellungsebene wurde nicht festgelegt, um Bericht\-Schleifen, die nicht parallel ausgeführt werden, zu melden.  Weitere Informationen zu Ursachencodes und Meldungen finden Sie unter [Vectorizer\- and Parallelizer\-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### So legen Sie die \/Qpar\-report\-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie im Dialogfeld **Eigenschaftenseiten** unter **C\/C\+\+ Command Line** aus.  
  
3.  Geben Sie im Feld **Zusätzliche Optionen** `/Qpar-Bericht: 1` oder `/Qpar-Bericht:2` ein.  
  
### So legen Sie die Compileroption "\/Qpar\-report" programmgesteuert fest  
  
-   Verwenden Sie hierzu das Codebeispiel unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/Q\-Optionen \(Operationen auf niedriger Ebene\)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/?LinkId=263662)