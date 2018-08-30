---
title: 'Logischer Negationsoperator: ! | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4594a8b1a881b6fa92909e7c7014087ff6240de8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211817"
---
# <a name="logical-negation-operator-"></a>Logischer Negationsoperator: !

## <a name="syntax"></a>Syntax

```
! cast-expression
```

## <a name="remarks"></a>Hinweise

Der logische Negationsoperator (**!**) Kehrt die Bedeutung des Operanden. Der Operand muss ein arithmetischer Typ oder Zeigertyp sein (oder ein Ausdruck, der dem arithmetischen Typ oder dem Zeigertyp gleicht). Der Operand wird implizit in den Typ konvertiert **"bool"**. Das Ergebnis ist "true", wenn der konvertierte Operand FALSE ist. Das Ergebnis ist "false", wenn der konvertierte Operand TRUE ist. Das Ergebnis ist vom Typ **"bool"**.

Für einen Ausdruck *e*, der unäre Ausdruck `!e` entspricht dem Ausdruck `(e == 0)`, außer wenn überladene Operatoren beteiligt sind.

## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für "!"

Die **nicht** Operator ist eine alternative Schreibweise des **!**. Es gibt zwei Möglichkeiten, den Zugriff auf die **nicht** -Operator in Programmen: Fügen Sie die Headerdatei \<iso646.h >, oder Kompilieren Sie mit der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).

## <a name="example"></a>Beispiel

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md)<br/>
