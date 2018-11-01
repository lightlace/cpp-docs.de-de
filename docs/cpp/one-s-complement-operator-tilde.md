---
title: 'Eine&#39;s Komplementoperator: ~'
ms.date: 11/04/2016
f1_keywords:
- "~"
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: d8fb8ca56932669ff85646f2aa0c10691122013b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469777"
---
# <a name="one39s-complement-operator-"></a>Eine&#39;s Komplementoperator: ~

## <a name="syntax"></a>Syntax

```
~ cast-expression
```

## <a name="remarks"></a>Hinweise

Der Einerkomplementoperator (`~`), der manchmal als „bitweiser Komplementoperator“ bezeichnet wird, ergibt eine bitweise Einerkomplement seines Operanden. Das bedeutet, dass jedes Bit, das 1 im Operanden ist, 0 im Ergebnis ist. Umgekehrt ist jedes Bit, das 0 im Operanden ist, im Ergebnis 1. Der Operand für den Einerkomplementoperator muss ein ganzzahliger Typ sein.

## <a name="operator-keyword-for-"></a>Operator-Schlüsselwort für ~

Die **Compl** -Operator ist die ausgeschriebene Variante von `~`. Es gibt zwei Möglichkeiten, den Zugriff auf die **Compl** -Operator in Programmen: Fügen Sie die Headerdatei `iso646.h`, oder Kompilieren Sie mit [/Za](../build/reference/za-ze-disable-language-extensions.md).

## <a name="example"></a>Beispiel

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

In diesem Beispiel ist der neue Wert, der `y` zugewiesen ist, das Einerkomplement des Werts ohne Vorzeichen 0xFFFF oder 0x0000.

Ganzzahlige Erweiterung wird für ganzzahlige Operanden durchgeführt, und der resultierende Typ ist der Typ, auf den der Operand erweitert wird. Finden Sie unter [Standardkonvertierungen](standard-conversions.md) für Weitere Informationen über die Ausführung der heraufstufung.

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit unären Operatoren](../cpp/expressions-with-unary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Unäre arithmetische Operatoren](../c-language/unary-arithmetic-operators.md)