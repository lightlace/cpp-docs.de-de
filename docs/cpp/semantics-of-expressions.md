---
title: Semantik von Ausdrücken
ms.date: 11/19/2018
helpviewer_keywords:
- grammar, expressions
- expressions [C++], semantics
- expression evaluation
- expression evaluation, about expression evaluation
ms.assetid: 4a792154-533b-48b9-8709-31bfc170f0a7
ms.openlocfilehash: d2ce510478bcf1574429c85f704552e6b73100ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331212"
---
# <a name="semantics-of-expressions"></a>Semantik von Ausdrücken

Ausdrücke werden entsprechend der Rangfolge und Gruppierung ihrer Operatoren ausgewertet. ([Operatorrangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md) in [lexikalische Konventionen](../cpp/lexical-conventions.md), zeigt den Beziehungen der C++ Operatoren für Ausdrücke vorgeben.)

## <a name="order-of-evaluation"></a>Reihenfolge der Auswertung

Betrachten Sie das folgende Beispiel:

```cpp
// Order_of_Evaluation.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main()
{
    int a = 2, b = 4, c = 9;

    cout << a + b * c << "\n";
    cout << a + (b * c) << "\n";
    cout << (a + b) * c << "\n";
}
```

```Output
38
38
54
```

![Auswertungsreihenfolge in einem Ausdruck](../cpp/media/vc38zv1.gif "Auswertungsreihenfolge in einem Ausdruck") <br/>
Reihenfolge der Auswertung von Ausdruck

Die Reihenfolge der Auswertung des in der obigen Abbildung dargestellten Ausdrucks wird durch die Reihenfolge und die Assoziativität der Operatoren bestimmt:

1. Multiplikation (*) weist die höchste Priorität in diesem Ausdruck auf. Daher wird der Teilausdruck `b * c` zuerst ausgewertet.

1. Addition (+) besitzt die zweithöchste Priorität, sodass `a` dem Produkt von `b` und `c` hinzugefügt wird.

1. Verschiebung nach links (<<) hat die niedrigste Priorität im Ausdruck, aber es gibt zwei vorkommen. Da der Left Shift-Operator von links nach rechts gruppiert, wird zuerst der linke und dann der rechte Teilausdruck ausgewertet.

Wenn Teilausdrücke mit Klammern gruppiert werden, werden die Rangfolge sowie die Reihenfolge der Auswertung des Ausdrucks geändert, wie in der folgenden Abbildung gezeigt.

![Die Reihenfolge der Auswertung eines Ausdrucks mit Klammern](../cpp/media/vc38zv2.gif "Reihenfolge der Auswertung eines Ausdrucks mit Klammern") <br/>
Reihenfolge der Auswertung von Ausdrücken mit Klammern

Ausdrücke, wie in der Abbildung oben, werden ausschließlich für ihre Nebeneffekte ausgewertet – in diesem Fall, um Informationen zum Standardausgabegerät zu übertragen.

## <a name="notation-in-expressions"></a>Notation in Ausdrücken

Die Programmiersprache C++ gibt beim Angeben von Operanden bestimmte Kompatibilitäten an. Die folgende Tabelle zeigt die Typen der Operanden an Operatoren, die Operanden des Typs erfordern akzeptable *Typ*.

### <a name="operand-types-acceptable-to-operators"></a>Operandentypen, die für Operatoren zulässig sind

|Typ erwartet|Typen zulässig|
|-------------------|-------------------|
|*Typ*|`const` *type*<br /> `volatile` *type*<br /> *type*&<br /> `const` *Typ*&<br /> `volatile` *Typ*&<br /> `volatile const` *type*<br /> `volatile const` *Typ*&|
|*type* \*|*type* \*<br /> `const` *Typ* \*<br /> `volatile` *Typ* \*<br /> `volatile const` *Typ* \*|
|`const` *type*|*Typ*<br /> `const` *type*<br />`const` *Typ*&|
|`volatile` *type*|*Typ*<br /> `volatile` *type*<br /> `volatile` *Typ*&|

Da die vorangehenden Regeln immer in Kombination verwendet werden können, kann ein const-Zeiger auf ein flüchtiges Objekt angegeben werden, wo ein Zeiger erwartet wird.

## <a name="ambiguous-expressions"></a>Mehrdeutige Ausdrücke

Bestimmte Ausdrücke sind mehrdeutig. Diese Ausdrücke treten am häufigsten auf, wenn der Wert eines Objekts mehrfach im selben Ausdruck geändert wird. Diese Ausdrücke basieren auf einer bestimmten Auswertungsreihenfolge, wenn sie von der Sprache nicht definiert wird. Betrachten Sie das folgende Beispiel:

```
int i = 7;

func( i, ++i );
```

Die Programmiersprache C++ gewährleistet nicht die Reihenfolge, in der Argumente zu einem Funktionsaufruf ausgewertet werden. Daher könnte `func` im vorhergehenden Beispiel die Werte 7 und 8 oder 8 und 8 für die Parameter empfangen, je nachdem, ob die Parameter von links nach rechts oder von rechts nach links ausgewertet werden.

## <a name="c-sequence-points-microsoft-specific"></a>C++-Sequenzpunkte (Microsoft-spezifisch)

Zwischen aufeinanderfolgenden "Sequenzpunkten" kann der Wert eines Objekts nur einmal durch einen Ausdruck geändert werden.

Die C++-Sprachendefinition gibt derzeit keine Sequenzpunkte an. Microsoft C++ verwendet dieselben Sequenzpunkte wie ANSI C für jeden beliebigen Ausdruck, der C-Operatoren einbezieht und nicht überladene Operatoren beinhaltet. Wenn Operatoren überladen werden, wird die Semantik von Operatorseqenzierung in Funktionsaufrufsequenzierung geändert. Microsoft C++ verwendet folgende Sequenzpunkte:

- Linker Operand des logischen AND-Operators (& &). Der linke Operand des logischen AND-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen. Es gibt keine Garantie, dass der rechte Operand des logischen AND-Operators ausgewertet wird.

- Linker Operand des logischen OR-Operators (&#124;&#124;). Der linke Operand des logischen OR-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen. Es gibt keine Garantie, dass der rechte Operand des logischen OR-Operators ausgewertet wird.

- Linker Operand des Komma-Operators. Der linke Operand des Komma-Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen. Beide Operanden des Komma-Operators werden immer ausgewertet.

- Funktionsaufrufoperator. Der Funktionsaufrufausdruck und alle Argumente für eine Funktion, einschließlich Standardargumente, werden ausgewertet und alle Nebeneffekte werden vor dem Eintritt in die Funktion abgeschlossen. Es gibt keine festgelegte Reihenfolge der Auswertung unter den Argumenten bzw. beim Funktionsaufrufausdruck.

- Der erste Operand des bedingten Operators. Der erste Operand des bedingten Operators wird vollständig ausgewertet, und alle Nebeneffekte werden vor dem Fortsetzen abgeschlossen.

- Das Ende eines vollständigen Initialisierungsausdrucks, wie das Ende einer Initialisierung in einer Deklarationsanweisung.

- Der Ausdruck in einer Ausdrucksanweisung. Ausdrucksanweisungen bestehen aus einem optionalen Ausdruck, dem ein Semikolon (;) folgt. Der Ausdruck wird vollständig für die Nebeneffekte ausgewertet.

- Der steuernde Ausdruck in einer Auswahlanweisung ("if" oder "switch"). Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor der von der Auswahl abhängige Code ausgeführt wird.

- Der steuernde Ausdruck einer while- oder do-Anweisung. Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor eine beliebige Anweisung in der nächsten Iteration der while- oder do-Schleife ausgeführt wird.

- Jede der drei Ausdrücke einer for-Anweisung. Jeder Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden geschlossen, bevor zum nächsten Ausdruck gewechselt wird.

- Der Ausdruck in einer return-Anweisung. Der Ausdruck wird vollständig ausgewertet, und alle Nebeneffekte werden abgeschlossen, bevor die Steuerung an die aufrufende Funktion zurückgegeben wird.

## <a name="see-also"></a>Siehe auch

[Ausdrücke](../cpp/expressions-cpp.md)