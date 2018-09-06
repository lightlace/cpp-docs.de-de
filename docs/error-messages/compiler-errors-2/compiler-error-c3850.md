---
title: Compilerfehler C3850 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daa4b6128672b47891c563acfd4399952a17e7e6
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894537"
---
# <a name="compiler-error-c3850"></a>Compilerfehler C3850

> "*Char*': eine universelle Zeichenname gibt ein ungültiges Zeichen

## <a name="remarks"></a>Hinweise

Zeichen, die als universelle Zeichennamen dargestellt werden, müssen gültigen Unicode-Codepunkten im Bereich 0-10FFFF entsprechen. Ein universeller Zeichenname darf weder einen Wert im Unicode-Ersatzbereich, D800-DFFF, noch ein codiertes Ersatzzeichenpaar enthalten. Der Compiler generiert das Ersatzpaar automatisch aus einem gültigen Codepunkt.

Im als C kompilierten Code, kann ein universeller Zeichenname kein Zeichen im Bereich 0000-009F, darstellen mit den Ausnahmen hierzu sind 0024 ("$"), einschließlich 0040 ('\@") und 0060 ('' ').

In Code, der als C++ kompiliert wird, darf für einen universellen Zeichennamen jeder gültige Unicode-Codepunkt in einer Zeichenfolge oder in einem Zeichenliteral verwendet werden. Außerhalb eines Literals darf ein universeller Zeichenname weder Steuerzeichen in den Bereichen 0000-001F und 007F-009F (beide inklusive) oder ein Member des grundlegenden Quellzeichensatzes darstellen.  Weitere Informationen finden Sie unter [Zeichensätze](../../cpp/character-sets.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3850 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C3850.cpp
int main() {
   int \u0019 = 0;   // C3850, not in allowed range for an identifier
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point
}
```