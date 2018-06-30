---
title: Verwenden von C oder C++ in __asm-Blöcken | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembly, mixing instructions with C/C++ statements
- symbols, in __asm blocks
- macros, __asm blocks
- preprocessor directives, used in __asm blocks
- type names, used in __asm blocks
- preprocessor directives
- preprocessor, directives
- constants, in __asm blocks
- comments, in __asm blocks
- typedef names, used in __asm blocks
- __asm keyword [C++], C/C++ elements in
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96ed46cdf44ccacee806dd03bf7eacca26eec32d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120944"
---
# <a name="using-c-or-c-in-asm-blocks"></a>Verwenden von C oder C++ in __asm-Blöcken

** Microsoft-spezifisch **

Da Inlineassemblyanweisungen mit C- oder C++-Anweisungen kombiniert werden können, können sie finden Sie anhand des Namens in C oder C++-Variablen und viele andere Elemente von diesen Sprachen verwenden.

Ein `__asm` Block kann die folgenden Sprachelemente verwenden:

- Symbole, z. B. Bezeichnungen und Variablen- und Funktionsnamen verwendet

- Konstanten, einschließlich symbolische Konstanten und `enum` Elemente

- Makros und Präprozessordirektiven

- Kommentare (beide __/ \* \* /__ und __//__ )

- Geben Sie Namen (ablegen, wo ein MASM-Typ zulässig wäre)

- `typedef` Namen, z. B. in der Regel mit Operatoren verwendet **PTR** und **Typ** oder die Angabe der Struktur oder Union-Member

Innerhalb einer `__asm` blockieren, können Sie ganzzahlige Konstanten mit C-Schreibweise oder Assembler Basis Notation angeben (0 x 100 und 100 h gleichwertig sind; z. B.). Dadurch können Sie definieren (mit `#define`) eine Konstante in C# und verwenden Sie es in C- oder C++ und Assembly Teile des Programms. Sie können auch Konstanten in angeben oktale durch eine 0 voranstellen. 0777 gibt z. B. eine oktale Konstante.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Verwenden von Operatoren in __asm-Blöcken](../../assembler/inline/using-operators-in-asm-blocks.md)

- [Verwenden von C- oder C++ Symbols_in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [Zugreifen auf C- oder C++-Daten in __asm-Blöcken](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Schreiben von Funktionen mit der Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)
