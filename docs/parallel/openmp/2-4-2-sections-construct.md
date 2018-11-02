---
title: 2.4.2 sections-Konstrukt
ms.date: 11/04/2016
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
ms.openlocfilehash: 2d9fca08eecd382c9d3df60159c13ac188a1ab85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486813"
---
# <a name="242-sections-construct"></a>2.4.2 sections-Konstrukt

Die **Abschnitte** -Direktive identifiziert ein noniterative Arbeit sharing-Konstrukt, das einen Satz von Konstrukten gibt an, die auf die Threads in einem Team aufgeteilt werden. Jeder Abschnitt wird von einem Thread im Team einmal ausgeführt. Die Syntax der **Abschnitte** Richtlinie lautet wie folgt:

```
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

Die Klausel ist eine der folgenden:

**Private (** *Variablenliste* **)**

**Firstprivate (** *Variablenliste* **)**

**Lastprivate (** *Variablenliste* **)**

**Verringerung der (** *Operator* **:**  *Variablenliste* **)**

**nowait**

Jeder Abschnitt vorangestellt ist eine **Abschnitt** Richtlinie, obwohl der **Abschnitt** Richtlinie ist optional für den ersten Abschnitt. Die **Abschnitt** Anweisungen müssen innerhalb der lexikalischen Wertebereich angezeigt werden die **Abschnitte** Richtlinie. Besteht eine implizite Barriere am Ende einer **Abschnitte** zu erstellen, es sei denn, eine **Nowait** angegeben ist.

Einschränkungen für die **Abschnitte** Richtlinie lauten wie folgt:

- Ein **Abschnitt** Richtlinie muss nicht außerhalb der lexikalischen Wertebereich angezeigt werden. die **Abschnitte** Richtlinie.

- Nur eine einzige **Nowait** Klausel darf sich auf eine **Abschnitte** Richtlinie.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **private**, **Firstprivate**, **Lastprivate**, und **Verringerung** Klauseln finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.