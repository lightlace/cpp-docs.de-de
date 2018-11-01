---
title: 2.5.2 parallel sections-Konstrukt
ms.date: 11/04/2016
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
ms.openlocfilehash: 1b74dacb9730a14364d7202918ae195cbf691955
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533665"
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections-Konstrukt

Die **parallel Sections-** Richtlinie stellt eine Verknüpfung-Form für die Angabe einer **parallele** Region mit nur einem einzelnen **Abschnitte** Richtlinie. Die Semantik ist identisch mit explizit angeben, ein **parallele** unmittelbar nach der Richtlinie eine **Abschnitte** Richtlinie. Die Syntax der **parallel Sections-** Richtlinie lautet wie folgt:

```
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

Die *Klausel* kann eine der Klauseln, die vom akzeptiert die **parallele** und **Abschnitte** -Anweisungen außer der **Nowait** Klausel.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **Parallele** -Anweisung finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **Abschnitte** -Anweisung finden Sie unter [Abschnitt 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) auf Seite "14".