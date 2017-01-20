---
title: "Vorteile der Inlineassembly"
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
helpviewer_keywords: 
  - "Assembler [C++], Vorteile"
  - "Inlineassembly [C++], Informationen über die Inlineassembly"
  - "Inlineassembly [C++], Verwenden"
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Vorteile der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Da der Inlineassembler nicht Schritte der separaten Assemblys und des Links erfordert, ist es einfacher als ein separater Assembler.  Inlineassemblycode kann jede C\-Variable oder Funktionsnamen verwenden, der im Gültigkeitsbereich befindet, daher ist es einfach, mit dem C\-Code des Programms zu integrieren.  Da der Assemblycode mit C\# oder inline C\+\+\-Anweisungen kombiniert werden kann, kann er Aufgaben ausführen, die lästig oder in C oder C\+\+ nicht möglich sind.  
  
 Wird vom Inlineassembly:  
  
-   Schreiben von Funktionen in Assemblersprache.  
  
-   Geschwindigkeit\-wichtige Codeabschnitte Stelle\-optimieren.  
  
-   Festlegen des direkten Hardware zugriffs für Gerätetreiber.  
  
-   Schreibeneinleitung und Epilogcode für „nackte“ Aufrufe.  
  
 Inlineassembly ist ein Tool für spezielle Zwecke.  Wenn Sie an den Anschluss eine Anwendung auf verschiedenen Computern planen, möchten Sie wahrscheinlich MACHINE spezifischen Code in einem separaten Modul ablegen.  Da der Inlineassembler nicht die ganze von der Microsoft Macro Assemblers \(MASM\) und Direktiven Daten unterstützt, stellen Sie möglicherweise es einfacher, MASM für solche Module verwendet werden soll.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)