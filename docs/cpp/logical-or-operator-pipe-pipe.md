---
title: 'Logischer OR-Operator: ||'
ms.date: 06/14/2018
f1_keywords:
- '||'
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 5db1af870644d1552aeac813edce0985a31d95b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368681"
---
# <a name="logical-or-operator-"></a>Logischer OR-Operator: ||

## <a name="syntax"></a>Syntax

> *logical-or-expression* **||** *logical-and-expression*

## <a name="remarks"></a>Hinweise

Der logische OR-Operator (**||**) gibt den booleschen Wert "true" zurück, wenn einer oder beide Operanden TRUE ist, und andernfalls "false" wird zurückgegeben. Die Operanden werden implizit in den Typ konvertiert **"bool"** vor der Auswertung und das Ergebnis ist vom Typ **"bool"**. Das logische OR weist eine Assoziativität von links nach rechts auf.

Die Operanden für den logischen OR-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein. Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.

Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen OR-Ausdrucks fortgesetzt wird.

Der zweite Operand wird nur ausgewertet, wenn der erste Operand als false (0) ausgewertet wird. Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der logische OR-Ausdruck TRUE ist.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

Im Beispiel oben, wenn `x` entweder gleich `w`, `y` oder `z` ist, wird das zweite Argument für die `printf`-Funktion mit TRUE ausgewertet, und der Wert 1 wird ausgegeben. Andernfalls wird dies mit "false" ausgewertet, und der Wert 0 (null) wird ausgegeben. Sobald eine der Bedingungen mit dem Ergebnis "true" ausgewertet wird, wird die Auswertung beendet.

## <a name="operator-keyword-for-124124"></a>Operator-Schlüsselwort für&#124;&#124;

Die **oder** -Operator ist die ausgeschriebene Variante von **||**. Es gibt zwei Möglichkeiten, den Zugriff auf die **oder** -Operator in Programmen: Fügen Sie die Headerdatei \<iso646.h >, oder Kompilieren Sie mit der [/Za](../build/reference/za-ze-disable-language-extensions.md) -Compileroption (spracherweiterungen deaktivieren).

## <a name="example"></a>Beispiel

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>Siehe auch

[C++-Built-Operatoren, Rangfolge und Assoziativität](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C-Operatoren (logisch)](../c-language/c-logical-operators.md)