---
title: Compilerwarnung (Stufe 2) C4146 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41d21f2be76e67c58599e214df764316dc845e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044625"
---
# <a name="compiler-warning-level-2-c4146"></a>Compilerwarnung (Stufe 2) C4146

einem vorzeichenlosen Typ wurde ein unärer minus-Operator zugewiesen.

Typen ohne Vorzeichen können nur positive Werte enthalten, damit unäres minus (Negation) nicht in der Regel bei Anwendung auf einen Typ ohne Vorzeichen sinnvoll ist. Sowohl die Operanden und das Ergebnis sind nicht negativ.

In der Praxis geschieht dies, wenn es sich bei der Programmierer versucht, den minimalen ganzzahligen Wert express-2147483648 handelt. Dieser Wert kann nicht als-2147483648 geschrieben werden, da der Ausdruck in zwei Stufen verarbeitet wird:

1. Die Anzahl 2147483648 wird ausgewertet. Da es größer als der maximal zulässige Ganzzahl-Wert 2147483647 handelt, ist der Typ des 2147483648 nicht [Int](../../c-language/integer-types.md), aber `unsigned int`.

1. Unäres minus wird auf den Wert mit einem Ergebnis ohne Vorzeichen, der gleich 2147483648 angewendet.

Der Typ ohne Vorzeichen des Ergebnisses kann unerwartetes Verhalten verursachen. Wenn das Ergebnis wird in einem Vergleich verwendet, und klicken Sie dann ein Vergleich ohne Vorzeichen werden, z. B. verwendet kann Wenn der andere Operand ein `int`. Hier wird erläutert, warum das nachfolgende Beispielprogramm nur eine Zeile ausgegeben.

Die erwartete zweite Zeile `1 is greater than the most negative int`, wird nicht ausgegeben werden, da `((unsigned int)1) > 2147483648` ist "false".

Sie können die C4146 vermeiden, indem Sie INT_MIN von limits.h, das den Typ aufweist **signiert Int**.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4146 generiert:

```
// C4146.cpp
// compile with: /W2
#include <stdio.h>

void check(int i)
{
    if (i > -2147483648)   // C4146
        printf_s("%d is greater than the most negative int\n", i);
}

int main()
{
    check(-100);
    check(1);
}
```