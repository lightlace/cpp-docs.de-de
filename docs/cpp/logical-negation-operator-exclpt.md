---
title: 'Logischer Negationsoperator: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
- Not
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 7b37e5108ca01d782c13508c0cd7a96b096cd745
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216407"
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
