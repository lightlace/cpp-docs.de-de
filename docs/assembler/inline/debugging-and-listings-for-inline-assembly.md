---
title: "Debuggen und Listen f&#252;r die Inlineassembly | Microsoft Docs"
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
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], Debuggen"
  - "Probleme, __asm-Blöcke"
  - "Debuggen [C++], Inlineassemblycode"
  - "Inlineassembly, Debuggen"
  - "Inlineassembly, Auflistungen"
  - "Debugger auf Quellcodeebene"
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Debuggen und Listen f&#252;r die Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Bei Programmen, die Inlineassemblycode enthalten, können mit einem SOURCE LEVEL\-Debugger gedebuggt werden, wenn Sie mit der [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) Option kompilieren.  
  
 Innerhalb des Debuggers können Sie Haltepunkte in C oder C\+\+ und Assemblersprachen von Zeilen festlegen.  Wenn Sie mehrere assembly\- Quellspalten und aktivieren Sie den Modus können Sie die Quelle und disassembliertes Form des Assemblycodes anzeigen.  
  
 Beachten Sie, dass mehrere Assemblyanweisungen Quelle oder legt sprachanweisungen Debugging können in einer eigenen Zeile hemmen.  Quellspalten im Modus können Sie den Debugger können Sie Haltepunkte in einer einzigen Zeile jedoch nicht für einzelne Anweisungen in der gleichen Zeile festzulegen.  Das gleiche Prinzip gilt für `__asm` einen Block, der als Wechselstrom\-Makro definiert wird, das zu einer einzelnen logischen Zeile erstreckt.  
  
 Wenn Sie eine gemischte quell\- und Umwandlungsliste mit der Compileroption [\/FAs](../../build/reference/fa-fa-listing-file.md) erstellen, die die Listen enthalten Quell\- und Assembly Assemblersprachen formulare jeder Zeile.  Makros werden nicht in den Listen erweitert, sie werden jedoch während der Kompilierung erweitert.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)