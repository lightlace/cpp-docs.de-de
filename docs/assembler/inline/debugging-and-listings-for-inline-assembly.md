---
title: "Debuggen und Listen für die Inlineassembly | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fea943c30d48ac122ae5d848306e4fe251f58da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Debuggen und Listen für die Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Programme mit Inline-Assemblycode können mit einem Debugger auf Quellcodeebene gedebuggt werden, wenn beim Kompilieren mit der [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) Option.  
  
 Innerhalb des Debuggers können Sie Haltepunkte für C- oder C++ und Assemblersprache Zeilen festlegen. Wenn Sie gemischten Assembly und der Modus aktivieren, können Sie die Quell- und den disassemblierten Form der Assemblycode anzeigen.  
  
 Beachten Sie, dass mehrere Assemblyanweisungen oder Quellsprache-Anweisungen in einer Zeile platzieren Debuggen behindern kann. Im Modus "Quelle" können Sie den Debugger verwenden, Festlegen von Haltepunkten in einer einzelnen Zeile, jedoch nicht auf einzelne Anweisungen in derselben Zeile. Das gleiche Prinzip gilt für eine `__asm` Block als C-Makro, der erweitert, um einen einzelnen logischen Zeile wird definiert.  
  
 Bei der Erstellung einer gemischten Quell- und die Assembly, die mit der [Angabe von/FAS](../../build/reference/fa-fa-listing-file.md) (Compileroption), die Liste enthält sowohl die Quell-als auch die Assembly Formen von jeder Zeile Assemblersprache. Makros werden in den Codebeispielen nicht erweitert, aber sie werden erweitert, während der Kompilierung.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)