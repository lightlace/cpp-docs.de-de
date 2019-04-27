---
title: Verwenden von C oder C++ in __asm-Blöcken
ms.date: 08/30/2018
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
ms.openlocfilehash: 0949eba769bed33da8fe39bb41500a2ba02af224
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166554"
---
# <a name="using-c-or-c-in-asm-blocks"></a>Verwenden von C oder C++ in __asm-Blöcken

** Microsoft-spezifisch **

Da Inlineassemblyanweisungen mit C oder C++-Anweisungen kombiniert werden können, können sie mit dem Namen auf C- oder C++-Variablen verweisen und viele andere Elemente dieser Sprachen.

Ein `__asm` blockieren, kann die folgenden Sprachelemente verwenden:

- Symbole, einschließlich der Bezeichnungen und Variablen-und Funktionsnamen

- Konstanten, einschließlich der symbolische Konstanten und `enum` Mitglieder

- Makros und Präprozessordirektiven

- Kommentare (beide __/ \* \* /__ und __//__ )

- Geben Sie die Namen (wo ein MASM zulässig wäre)

- `typedef` Namen, die in der Regel der Verwendung Operatoren wie z. B. **PTR** und **Typ** oder die Angabe von Struktur oder Union-Elemente

Innerhalb einer `__asm` blockieren, können Sie ganzzahlige Konstanten mit C-Schreibweise oder Assembler Basis Notation angeben (0 x 100 und 100 h sind äquivalent, z. B.). Dadurch können Sie definieren (mit `#define`) eine Konstante in C und klicken Sie dann in C oder C++ und Assembly Teile des Programms. Sie können auch angeben, Konstanten in oktalen abgrenzen, indem Sie mit 0. 0777 gibt z. B. eine oktale Konstante.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Verwenden von Operatoren in __asm-Blöcken](../../assembler/inline/using-operators-in-asm-blocks.md)

- [Mithilfe von C oder C++ Symbols_in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [Zugreifen auf C- oder C++-Daten in __asm-Blöcken](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Schreiben von Funktionen mit der Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>
