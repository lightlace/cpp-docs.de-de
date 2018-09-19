---
title: Verwenden von C- oder C++-Symbolen in __asm-Blöcken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ba8426e2a7ae1152a41fafa0c239498801c6e4d
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678892"
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>Verwenden von C- oder C++-Symbolen in __asm-Blöcken

**Microsoft-spezifisch**

Ein `__asm` Block kann auf jeder C- oder C++-Symbol, in der Block steht verweisen. (C und C++-Symbole sind Variablennamen, Funktionsnamen, und die Bezeichnungen; die, Namen, die nicht der symbolischen Konstanten oder `enum` Member. Sie können keine C++-Memberfunktionen Funktionen aufrufen.)

Einige Einschränkungen gelten für die Verwendung von C- und C++-Symbolen:

- Jede Assembly-Language-Anweisung kann nur eine C- oder C++-Symbol enthalten. Mehrere Symbole können angezeigt werden, in der gleichen Assemblyanweisung nur mit **Länge**, **Typ**, und **Größe** Ausdrücke.

- Funktionen, die auf die verwiesen wird einer `__asm` Block (Prototyp) weiter oben in das Programm deklariert werden. Andernfalls vom Compiler nicht unterscheiden Funktionsnamen und Bezeichnungen in der `__asm` Block.

- Ein `__asm` Block keine Symbole für C- oder C++ mit der gleichen Schreibweise wie MASM reservierte Wörter (unabhängig von der Schreibweise) nicht verwendet werden. MASM-reservierten Wörter enthalten Anweisungsnamen, z. B. **PUSH** und Namen, z. B. SI zu registrieren.

- Struktur- und Unionmember Tags werden nicht erkannt. `__asm` Blöcke.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>