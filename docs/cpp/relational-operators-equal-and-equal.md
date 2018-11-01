---
title: 'Relationale Operatoren: &lt;, &gt;, &lt;=, und &gt;='
ms.date: 11/04/2016
f1_keywords:
- <
- '>'
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators [C++], syntax
- '>= operator'
- greater than or equal to operators [C++]
- greater than operators [C++]
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
ms.openlocfilehash: 52a3c10e6da42f6c181d3f93de13168e22141bec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458954"
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>Relationale Operatoren: &lt;, &gt;, &lt;=, und &gt;=

## <a name="syntax"></a>Syntax

```
expression < expression
expression > expression
expression <= expression
expression >= expression
```

## <a name="remarks"></a>Hinweise

Die binären relationalen Operatoren bestimmen die folgenden Beziehungen:

- Kleiner als (**\<**)

- Größer als (**>**)

- Kleiner als oder gleich (**\<=**)

- Größer als oder gleich (**>=**)

Die relationalen Operatoren haben Assoziativität von links nach rechts. Beide Operanden aus relationalen Operatoren müssen vom arithmetischen oder vom Zeigertyp sein. Sie ergeben Werte des Typs **"bool"**. Der zurückgegebene Wert ist **"false"** (0), wenn die Beziehung im Ausdruck, andernfalls "false ist", der zurückgegebene Wert ist **"true"** (1).

## <a name="example"></a>Beispiel

```cpp
// expre_Relational_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << "The true expression 3 > 2 yields: "
         << (3 > 2) << endl
         << "The false expression 20 < 10 yields: "
         << (20 < 10) << endl;
}
```

Die Ausdrücke im vorherigen Beispiel müssen in Klammern gesetzt werden, da der Operator zum Einfügen des Datenstroms (**<<**) hat Vorrang vor den relationalen Operatoren. Daher würde der erste Ausdruck ohne Klammern wie folgt ausgewertet:

```cpp
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");
```

Die üblichen arithmetischen Konvertierungen finden Sie im [Standardkonvertierungen](standard-conversions.md) werden auf die Operanden arithmetischen Typs angewendet.

## <a name="comparing-pointers"></a>Vergleichen von Zeigern

Wenn zwei Zeiger auf Objekte vom gleichen Typs verglichen werden, wird das Ergebnis nach der Position der Objekte bestimmt, auf die im Adressbereich des Programms gezeigt wird. Zeiger können auch mit einem konstanten Ausdruck, der auf 0 oder ein Zeiger des Typs ergibt verglichen werden `void *`. Wenn ein zeigervergleich mit einem Zeiger vom Typ erfolgt `void *`, der andere Zeiger implizit in den Typ konvertiert wird `void *`. Anschließend wird verglichen.

Zwei Zeiger verschiedener Typen können nicht verglichen werden, es sei denn:

- Ein Typ ist ein Klassentyp, der vom anderen Typ abgeleitet wird.

- Mindestens einer der Zeiger wird explizit konvertiert (umgewandelt) Geben Sie `void *`. (Der andere Zeiger implizit in den Typ konvertiert wird `void *` für die Konvertierung.)

Zwei Zeiger desselben Typs, die auf dasselbe Objekt zeigen, sind beim Vergleich garantiert gleich. Wenn zwei Zeiger auf nicht statische Member eines Objekts verglichen werden, gelten folgende Regeln:

- Der Klassentyp ist keine **Union**, und wenn die zwei Member nicht durch getrennt sind ein *Zugriffsspezifizierer*, z. B. **öffentliche**, **geschützt**, oder **private**, der Zeiger auf das Element deklariert letzten Vergleich einen größeren Wert als der Zeiger auf den zuvor deklarierten Member.

- Wenn die beiden Elemente durch getrennt sind ein *Zugriffsspezifizierer*, sind die Ergebnisse nicht definiert.

- Wenn der Klassentyp ist eine **Union**, Zeiger auf unterschiedliche Datenmember, **Union** Vergleich gleich.

Wenn zwei Zeiger auf Elemente desselben Arrays oder auf ein Element über das Ende des Arrays hinaus zeigen, erzielt der Zeiger auf das Objekt mit dem höheren Index einen höheren Wert. Der Vergleich von Zeigern ist nur dann garantiert gültig, wenn der Zeiger auf Objekte im gleichen Array oder auf die Position verweist, die eine Stelle nach dem Ende des Arrays liegt.

## <a name="see-also"></a>Siehe auch

[Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)<br/>
[C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C-Operatoren (relational) und C-Gleichheitsoperatoren](../c-language/c-relational-and-equality-operators.md)