---
title: 2.7.2.6 reduction
ms.date: 11/04/2016
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
ms.openlocfilehash: 54b326feb4e4ccf1f1da5c8152ffc8d1e4bd13b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456016"
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

Diese Klausel führt eine Reduzierung der skalaren Variablen in *Variablenliste*, mit dem Operator *Op*. Die Syntax der `reduction` -Klausel ist wie folgt:

> Verringerung der (*Op*: *Variablenliste*)

Eine Reduzierung wird in der Regel für eine Anweisung mit einem der folgenden Formate angegeben werden:

> *X* = *x* *Op* *Expr*
> *x* *Binop* = *Expr*
> *x* = *Expr* *Op* *x* (Ausnahme: zur Subtraktion) *x*++
> ++*x*
> *x*--
> --*x*

Dabei gilt:

*w*<br/>
Einer der Verringerung der Variablen in der `list`.

*variable-list*<br/>
Eine durch Trennzeichen getrennte Liste von skalaren Reduction-Variablen.

*expr*<br/>
Ein Ausdruck mit skalaren Typ, der nicht verweist *x*.

*op*<br/>
Keines überladenen Operators, aber einer der +, &#42;, -, &amp;, ^, &#124;, &amp; &amp;, oder &#124; &#124;.

*binop*<br/>
Keines überladenen Operators, aber einer der +, &#42;, -, &amp;, ^, oder &#124;.

Folgendes ist ein Beispiel für die `reduction` Klausel:

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

Wie im Beispiel gezeigt wird, kann ein Operator in einem Funktionsaufruf ausgeblendet werden. Der Benutzer sollte Achten Sie darauf, dass der Operator, in angegeben der `reduction` Klausel entspricht den Reduction-Vorgang.

Obwohl der Rechte Operand des der &#124; &#124; Operator hat keine Nebenwirkungen in diesem Beispiel, sie sind zulässig, jedoch sollte mit Vorsicht verwendet werden. In diesem Kontext kann ein Nebeneffekt auslösen, der garantiert nicht während der sequenziellen Ausführung der Schleife auftreten, während der parallelen Ausführung auftreten. Dieser Unterschied kann auftreten, da die Reihenfolge der Ausführung der Iterationen unbestimmt ist.

Der Operator wird den Anfangswert des vom Compiler verwendet wird, für die Verringerung der privaten Variablen zu bestimmen und um zu bestimmen, den Finalization-Operator verwendet werden. Explizites Angeben des Operators kann die Verringerung der Anweisung außerhalb der lexikalischen Umfang des Konstrukts. Eine beliebige Anzahl von `reduction` Klauseln können für die Direktive angegeben werden, aber eine Variable darf in nur einer `reduction` -Klausel für diese Anweisung.

Eine private Kopie der einzelnen Variablen im *Variablenliste* erstellt wird – einer für die einzelnen Threads, als ob die `private` Klausel verwendet worden. Die private Kopie gemäß dem Operator initialisiert wird (siehe die folgende Tabelle).

Am Ende des Bereichs für die die `reduction` -Klausel angegeben wurde, das ursprüngliche Objekt wird aktualisiert, und das Ergebnis der Kombination von des ursprünglichen Wert mit der endgültige Wert der jeder die private Kopien, die mithilfe des angegebenen Operators an. Die Verringerung der Operatoren sind alle assoziative (mit Ausnahme der Subtraktion), und der Compiler kann frei erneut zugeordnet werden, der Berechnung des endgültigen Werts. (Die partielle Ergebnisse einer Verringerung der Subtraktion werden hinzugefügt, um den endgültigen Wert zu erstellen.)

Der Wert des ursprünglichen Objekts wird unbestimmt, wenn der erste Thread die Klausel enthält erreicht, und so bleibt, bis die Verringerung der Berechnung abgeschlossen ist.  In der Regel wird die Berechnung abgeschlossen ist, am Ende des Konstrukts sein; aber wenn die `reduction` -Klausel wird verwendet, für ein Konstrukt, `nowait` ist auch angewendet, der Wert des ursprünglichen Objekts bleibt unbestimmten bis eine Barriere Synchronisierung durchgeführt wurde, um sicherzustellen, dass alle Threads den abgeschlossensind`reduction`Klausel.

Die folgende Tabelle enthält die Operatoren, die gültig sind und ihre kanonischen Initialisierungswerte. Der Wert für die eigentliche Initialisierung wird mit dem Datentyp der Reduction-Variable konsistent sein.

|Operator|Initialisierung|
|--------------|--------------------|
|+|0|
|&#42;|1|
|-|0|
|&amp;|~0|
|&#124;|0|
|^|0|
|&amp;&amp;|1|
|&#124;&#124;|0|

Die Einschränkungen fest, die `reduction` Klausel lauten wie folgt:

- Der Typ der Variablen in der `reduction` Klausel muss für die Reduction-Operator gültig sein, außer dass Zeiger und Verweistypen nicht zulässig sind.

- Eine Variable, die im angegebenen die `reduction` Klausel darf nicht sein **const**-qualifizierten.

- Variablen, die innerhalb eines parallelen Bereichs privat sind, bzw. die angezeigt werden, in, der `reduction` -Klausel einer **parallele** Richtlinie kann nicht angegeben werden, eine `reduction` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```
