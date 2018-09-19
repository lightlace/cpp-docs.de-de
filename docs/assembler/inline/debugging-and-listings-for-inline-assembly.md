---
title: Debuggen und Listen für die Inlineassembly | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
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
ms.openlocfilehash: b6cca954ae15252b97d883ba8491fdb98e506f68
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689288"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Debuggen und Listen für die Inlineassembly

**Microsoft-spezifisch**

Programme mit Inline-Assemblycode können mit einem Debugger auf Quellcodeebene gedebuggt werden, bei der Kompilierung mit der ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) Option.

Innerhalb des Debuggers können Sie Haltepunkte in C oder C++ und Assemblysprache Zeilen festlegen. Wenn Sie gemischten Assembly und die Source-Modus aktivieren, können Sie sowohl die Quell-als auch die disassemblierten Form von Code für die Assembly anzeigen.

Beachten Sie, dass mehrere Assemblyanweisungen oder Source-Sprache-Anweisungen in einer Zeile einfügen Debuggen erschweren kann. Im Quellmodus können Sie den Debugger verwenden, zum Festlegen von Breakpoints in einer einzelnen Zeile jedoch nicht in einzelnen Anweisungen in der gleichen Zeile. Das gleiche Prinzip gilt für eine `__asm` blockieren, die definiert, wie ein C-Makro, das in einer einzelnen logischen Zeile erweitert wird.

Bei der Erstellung von einem gemischten Quelle und einer Assembly, die Liste, die mit der [/FAS](../../build/reference/fa-fa-listing-file.md) -Compileroption verwenden, die Liste enthält sowohl die Quell-als auch die Assembly Formulare jeder Zeile der Assemblysprache. Makros werden in Codebeispielen nicht erweitert, aber sie werden erweitert, während der Kompilierung.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden der Assemblysprache in __asm-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>