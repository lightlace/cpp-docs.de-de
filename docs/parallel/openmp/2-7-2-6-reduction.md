---
title: 2.7.2.6 Reduzierung der | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 759a2ee50f047fbd5777481d009332be998ad359
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

Diese Klausel führt eine Reduzierung der skalaren Variablen in *Variablenliste*, mit dem Operator *Op*. Die Syntax der `reduction` -Klausel ist wie folgt:

> Verringerung (*Op*: *Variablenliste*)

Eine Verkleinerung ist in der Regel für eine Anweisung mit einem der folgenden Formate angegeben werden:

> *X* = *x* *Op* *Expr*  
> *X* *Binop* = *Expr*  
> *X* = *Expr* *Op* *x* (mit Ausnahme von Subtraktion)  
> *x*++  
> ++*x*  
> *x*--  
> --*x*  

Dabei gilt:

*w*  
Einer der Reduction-Variablen, die im angegebenen der `list`.

*variable-list*  
Eine durch Trennzeichen getrennte Liste von skalaren Reduction-Variablen.

*expr*  
Ein Ausdruck mit skalaren Typ, der nicht verweist *x*.

*op*  
Keines überladenen Operators, aber eine der +, &#42;, -, &amp;, ^, &#124;, &amp; &amp;, oder &#124; &#124;.

*binop*  
Keines überladenen Operators, aber eine der +, &#42;, -, &amp;, ^, oder &#124;.

Im folgenden ist ein Beispiel für die `reduction` Klausel:  
  
```cpp  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
Wie im Beispiel gezeigt wird, kann ein Operator in einem Funktionsaufruf ausgeblendet. Der Benutzer sollte Achten Sie darauf, dass der Operator, in angegeben der `reduction` Klausel entspricht den Reduction-Vorgang.

Obwohl der Rechte Operand des der &#124; &#124; Operator hat keine Nebenwirkungen in diesem Beispiel, sie sind zulässig, jedoch mit Vorsicht verwendet werden soll. In diesem Kontext kann ein Nebeneffekt, der mit Sicherheit nicht auftreten, während die sequenzielle Ausführung der Schleife, während der parallelen Ausführung auftreten. Dieser Unterschied kann auftreten, da die Reihenfolge der Ausführung der Iterationen unbestimmt ist.

Der Operator wird den Anfangswert aller privaten Variablen, die vom Compiler verwendet werden, für die Verkürzung der Dauer zu ermitteln und bestimmen den Finalisierung-Operator verwendet. Explizites Angeben von den Operator ermöglicht die Reduzierung der Anweisung außerhalb der lexikalische Ausmaß des Konstrukts. Eine beliebige Anzahl von `reduction` Klauseln können für die Direktive angegeben werden, aber eine Variable kann in höchstens eine angezeigt werden `reduction` -Klausel für diese Richtlinie.

Eine private Kopie jeder Variablen in *Variablenliste* erstellt wird – einer für jeden Thread, als ob die `private` hatte-Klausel verwendet wurde. Die private Kopie wird gemäß dem Operator initialisiert (siehe die folgende Tabelle).

Am Ende des Bereichs für die die `reduction` -Klausel angegeben wurde, das ursprüngliche Objekt wird aktualisiert, und das Ergebnis einer Kombination aus den ursprünglichen Wert mit den endgültigen Wert der einzelnen privaten Kopien mithilfe des angegebenen Operators wieder. Die Reduzierungsoperatoren alle assoziativ (mit Ausnahme von Subtraktion) sind, und der Compiler kann kostenlos erneut zugeordnet werden, die Berechnung des endgültigen Wert. (Die Teilergebnisse einer Subtraktion Verringerung werden hinzugefügt, um den endgültigen Wert zu bilden.)

Der Wert des ursprünglichen Objekts wird unbestimmt, wenn der erste Thread die enthaltende-Klausel erreicht und bleibt, bis die Reduzierung der Berechnung abgeschlossen ist.  Normalerweise ist die Berechnung abgeschlossen am Ende des Konstrukts, jedoch, wenn die `reduction` -Klausel wird verwendet, auf ein Konstrukt, `nowait` wird auch angewendet, der Wert des ursprünglichen Objekts bleibt unbestimmt bis eine Barriere Synchronisierung ausgeführt wurde, um sicherzustellen, dass alle Threads den abgeschlossensind`reduction`Klausel.

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
||||0|

Die Einschränkungen fest, die `reduction` Klausel lauten wie folgt:

- Der Typ der Variablen in der `reduction` Klausel muss für die Reduction-Operator gültig sein, außer dass Zeigertypen und Verweistypen nicht zulässig sind.

- Eine Variable, die im angegebenen der `reduction` Klausel darf nicht sein **const**-qualifizierten.

- Variablen, die innerhalb eines parallelen Bereichs privaten sind bzw. die angezeigt werden, in, der `reduction` -Klausel der eine **parallele** Richtlinie kann nicht angegeben werden, eine `reduction` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden.

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
