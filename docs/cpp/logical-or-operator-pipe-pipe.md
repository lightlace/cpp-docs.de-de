---
title: 'Logischer OR-Operator: || | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37a7591e185b1436bb3cd0f8b56a625f71bf8ed2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073644"
---
# <a name="logical-or-operator-"></a>Logischer OR-Operator: ||

## <a name="syntax"></a>Syntax

> *logische-oder-Ausdruck* **||** *logische-und-Ausdruck*

## <a name="remarks"></a>Hinweise

Der logische OR-Operator (**||**) gibt den booleschen Wert "true" zurück, wenn einer oder beide Operanden TRUE ist, und andernfalls "false" wird zurückgegeben. Die Operanden werden implizit in den Typ konvertiert **"bool"** vor der Auswertung und das Ergebnis ist vom Typ **"bool"**. Das logische OR weist eine Assoziativität von links nach rechts auf.

Die Operanden für den logischen OR-Operator müssen nicht vom gleichen Typ sein, aber sie müssen Ganzzahltypen oder Zeigertypen sein. Die Operanden sind im Allgemeinen relationale oder Gleichheitsausdrücke.

Der erste Operand wird vollständig ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die Auswertung des logischen OR-Ausdrucks fortgesetzt wird.

Der zweite Operand wird nur ausgewertet, wenn der erste Operand als false (0) ausgewertet wird. Diese Auswertung eliminiert die unnötige Auswertung des zweiten Operanden, wenn der logische OR-Ausdruck TRUE ist.

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

Im Beispiel oben, wenn `x` entweder gleich `w`, `y` oder `z` ist, wird das zweite Argument für die `printf`-Funktion mit "true" ausgewertet, und der Wert 1 wird ausgegeben. Andernfalls wird dies mit "false" ausgewertet, und der Wert 0 (null) wird ausgegeben. Sobald eine der Bedingungen mit dem Ergebnis "true" ausgewertet wird, wird die Auswertung beendet.

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