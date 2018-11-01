---
title: 2.6.4 atomic-Konstrukt
ms.date: 11/04/2016
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
ms.openlocfilehash: 1f477a59ef475fda9bd0daeeb4edac18a3eeedb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677655"
---
# <a name="264-atomic-construct"></a>2.6.4 atomic-Konstrukt

Die `atomic` Richtlinie stellt sicher, dass eine bestimmte Speicheradresse atomar aktualisiert wird, anstatt eine Offenlegung für die Möglichkeit, mehrere gleichzeitige Threads zu schreiben. Die Syntax der `atomic` Richtlinie lautet wie folgt:

```
#pragma omp atomic new-lineexpression-stmt
```

Die Ausdrucksanweisung muss es sich um einen der folgenden Formate aufweisen:

*X binop*= *Expr*

x++

++x

x--

--x

In den vorherigen Ausdrücken:

- *X* ist ein l-Wert-Ausdruck mit skalaren Typ.

- *Expr* ist ein Ausdruck mit skalaren Typ und keinen Verweis auf das Objekt vom angegebenen *x*.

- `binop` ist kein überladenen Operators und ist einer der +, \*, -, /, &, ^, &#124;, <\<, oder >>.

Obwohl es Implementierung definiert ist, gibt an, ob eine Implementierung ersetzt alle `atomic` Direktiven mit **kritische** Direktiven, die die gleiche eindeutige *Name*, `atomic` Richtlinie ermöglicht bessere Optimierung. Häufig Hardware-Anweisungen stehen zur Verfügung, das unteilbare Update mit den geringsten Aufwand ausführen kann.

Nur das Laden und den Speicher für das Objekt vom angegebenen *x* atomar sind; die Auswertung von *Expr* ist nicht unteilbar. Um Racebedingungen zu vermeiden, alle Updates des Speicherorts parallel geschützt werden sollte, mit der `atomic` Direktive, mit Ausnahme derjenigen, die bekannt ist, dass Racebedingungen kostenlos zur Verfügung gestellt.

Einschränkungen für die `atomic` Richtlinie lauten wie folgt:

- Alle atomic Verweise auf den Speicherort X in der gesamten Anwendung muss einen kompatiblen Typ sein.

## <a name="examples"></a>Beispiele:

```
extern float a[], *p = a, b;
/* Protect against races among multiple updates. */
#pragma omp atomic
a[index[i]] += b;
/* Protect against races with updates through a. */
#pragma omp atomic
p[i] -= 1.0f;

extern union {int n; float x;} u;
/* ERROR - References through incompatible types. */
#pragma omp atomic
u.n++;
#pragma omp atomic
u.x -= 1.0f;
```