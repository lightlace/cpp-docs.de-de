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
ms.openlocfilehash: 16b298b92a4ba40d9091499a1821ad4f3c413d6c
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854523"
---
# <a name="using-c-or-c-in-__asm-blocks"></a>Verwenden von C oder C++ in __asm-Blöcken

**Microsoft-spezifisch**

Da Inline-Assemblyanweisungen mit c- C++ oder-Anweisungen gemischt werden können, können C++ Sie auf c-oder-Variablen anhand des Namens verweisen und viele andere Elemente dieser Sprachen verwenden.

Ein `__asm`-Block kann die folgenden Sprachelemente verwenden:

- Symbole, einschließlich Bezeichnungen und Variablen-und Funktionsnamen

- Konstanten, einschließlich symbolischer Konstanten und `enum` Membern

- Makros und Präprozessordirektiven

- Kommentare (sowohl __/\* \*/__ als auch __//__ )

- Typnamen (wo ein MASM-Typ zulässig wäre)

- `typedef` Namen, die im Allgemeinen mit Operatoren wie **ptr** und **Type** oder zum Angeben von Struktur-oder Union-Membern verwendet werden.

In einem `__asm`-Block können Sie ganzzahlige Konstanten mit C-Notation oder Assembler-Basis-Notation angeben (z. b. 0x100 und 100 h sind äquivalent). Dies ermöglicht es Ihnen, eine Konstante in c zu definieren (mit `#define`) und diese dann sowohl in c C++ -als auch in assemblyteilen des Programms zu verwenden. Sie können auch Konstanten im Oktal angeben, indem Sie Sie mit 0 (null) vorangestellt werden. 0777 gibt z. b. eine oktale Konstante an.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Verwenden von Operatoren in __asm-Blöcken](../../assembler/inline/using-operators-in-asm-blocks.md)

- [Verwenden von C C++ -oder Symbols_in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [Zugreifen auf C- oder C++-Daten in __asm-Blöcken](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [Schreiben von Funktionen mit der Inlineassembly](../../assembler/inline/writing-functions-with-inline-assembly.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>
