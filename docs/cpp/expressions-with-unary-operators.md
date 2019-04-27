---
title: Ausdrücke mit unären Operatoren
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
ms.openlocfilehash: a13b86755a5e309a51a0e2e14faa1157b7e95ea0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62183869"
---
# <a name="expressions-with-unary-operators"></a>Ausdrücke mit unären Operatoren

Unäre Operatoren werden nur auf einen Operanden in einem Ausdruck angewendet. Die unären Operatoren lauten wie folgt:

- [Der Dereferenzierungsoperator (*)](../cpp/indirection-operator-star.md)

- [Address-of-Operator (&)](../cpp/address-of-operator-amp.md)

- [Unärer plus -Operator (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Unärer Negationsoperator (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Logischer Negationsoperator (!)](../cpp/logical-negation-operator-exclpt.md)

- [Einerkomplementoperator (~)](../cpp/one-s-complement-operator-tilde.md)

- [Präfixinkrement-Operator (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Präfixdekrement-Operator (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Umwandlungsoperator)](../cpp/cast-operator-parens.md)

- [Sizeof-operator](../cpp/sizeof-operator.md)

- [__uuidof-operator](../cpp/uuidof-operator.md)

- [__alignof-operator](../cpp/alignof-operator.md)

- [New-operator](../cpp/new-operator-cpp.md)

- [Delete-operator](../cpp/delete-operator-cpp.md)

Diese Operatoren weisen eine Assoziativität von rechts nach links auf. Unäre Ausdrücke umfassen im Allgemeinen Syntax, die einem Postfix oder primären Ausdruck vorausgeht.

Folgende Formen von unären Ausdrücken sind möglich:

- *postfix-expression*

- `++` *unary-expression*

- `--` *unary-expression*

- *unary-operator* *cast-expression*

- **sizeof** *unary-expression*

- `sizeof(` *type-name* `)`

- `decltype(` *expression* `)`

- *allocation-expression*

- *deallocation-expression*

Alle *Postfix-Expression* gilt eine *Unary-Expression*, und da jeder primärer Ausdruck gilt eine *Postfix-Expression*, ist primäre Ausdrücke betrachtet ein *Unary-Expression* auch. Weitere Informationen finden Sie unter [Postfixausdrücke](../cpp/postfix-expressions.md) und [Primärausdrücke](../cpp/primary-expressions.md).

Ein *unäroperator* besteht aus einem oder mehreren der folgenden Symbole: `* & + - ! ~`

Die *Cast-Expression* ist ein unärer Ausdruck mit einer optionalen Umwandlung, den Typ ändern. Weitere Informationen finden Sie unter [Umwandlungsoperator: ()](../cpp/cast-operator-parens.md).

Ein *Ausdruck* kann ein beliebiger Ausdruck sein. Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).

Die *Zuweisungsausdruck* bezieht sich auf die **neue** Operator. Die *Aufhebung der Zuordnung-Expression* bezieht sich auf die **löschen** Operator. Weitere Informationen finden Sie unter den Links weiter oben in diesem Thema.

## <a name="see-also"></a>Siehe auch

[Ausdruckstypen](../cpp/types-of-expressions.md)