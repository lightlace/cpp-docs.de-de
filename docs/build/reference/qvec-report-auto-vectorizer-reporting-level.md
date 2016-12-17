---
title: "/Qvec-report (Auto-Vectorizer-Berichtsebene)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# /Qvec-report (Auto-Vectorizer-Berichtsebene)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die Berichtsfunktion des Compilers [Automatische Vektorisierung](../../parallel/auto-parallelization-and-auto-vectorization.md) und der Ebene der Informationsmeldungen für die Ausgabe bei der Kompilierung an.  
  
## Syntax  
  
```  
/Qvec-report:{1}{2}  
```  
  
## Hinweise  
 **\/Qvec\-report:1**  
 Gibt eine Informationsmeldung für Schleifen aus, die vektorisiert werden.  
  
 **\/Qvec\-report:2**  
 Gibt eine Informationsmeldung für Schleifen, die vektorisiert werden und für Schleifen, die nicht vektorisiert werden, zusammen mit einem Ursachencode aus.  
  
 Informationen zum Ursachencodes und Meldungen, finden Sie unter [Vectorizer\- and Parallelizer\-Meldungen](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### So die Compileroption \/Qvec\-report\- in Visual Studio fest  
  
1.  In **Projektmappen\-Explorer** öffnen Sie das Kontextmenü für das Projekt und dann **Eigenschaften** aus.  
  
2.  Im Dialogfeld **Eigenschaftenseiten** unter **C\/C\+\+**, wählen Sie **Befehlszeile** aus.  
  
3.  Im Feld **Zusätzliche Optionen** den Namen `/Qvec-report:1` oder `/Qvec-report:2` ein.  
  
### So die \/Qvec\-report\- Compileroption programmgesteuert fest  
  
-   Verwenden Sie das Codebeispiel in <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/Q\-Optionen \(Operationen auf niedriger Ebene\)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Parallele Programmierung in systemeigenem Code](http://go.microsoft.com/fwlink/?LinkId=263662)