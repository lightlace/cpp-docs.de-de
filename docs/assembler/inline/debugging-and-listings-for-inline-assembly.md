---
title: Debuggen und Listen für die Inlineassembly | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 457402626edcdb2be05923aa33bbd26b1cab7137
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050115"
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