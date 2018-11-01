---
title: 'Unärer Plus- und Negationsoperatoren: + und -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
ms.openlocfilehash: c1d5fc926b396f1ec44b9e44e79721e2ca4a0908
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580907"
---
# <a name="unary-plus-and-negation-operators--and--"></a>Unärer Plus- und Negationsoperatoren: + und -

## <a name="syntax"></a>Syntax

```
+ cast-expression
- cast-expression
```

## <a name="-operator"></a>+-Operator

Das Ergebnis des unären plus -Operators (**+**) ist der Wert des Operanden. Der Operand für den unären Plus-Operator muss ein arithmetischer Typ sein.

Ganzzahlige Erweiterung wird für ganzzahlige Operanden ausgeführt. Der resultierende Typ ist der Typ, in den der Operand heraufgestuft wird. Daher, ist der Ausdruck `+ch`, wobei `ch` ist vom Typ **Char**, führt zu Typ **Int**; der Wert bleibt unverändert. Finden Sie unter [Standardkonvertierungen](standard-conversions.md) für Weitere Informationen zur Durchführung der heraufstufung.

## <a name="--operator"></a>--Operator

Der unäre Negationsoperator (**-**) erzeugt den negativen Wert des Operanden. Der Operand für den unären Negationsoperator muss ein arithmetischer Typ sein.

Ganzzahlige Erweiterung wird für ganzzahlige Operanden durchgeführt, und der resultierende Typ ist der Typ, auf den der Operand erweitert wird. Finden Sie unter [Standardkonvertierungen](standard-conversions.md) für Weitere Informationen zur Ausführung der heraufstufung.

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Eine unäre Negation von Mengen ohne Vorzeichen wird ausgeführt, indem der Wert des Operanden von 2^n subtrahiert wird, wobei n die Anzahl von Bits in einem Objekt des angegebenen vorzeichenlosen Typs ist.

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)