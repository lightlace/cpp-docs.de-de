---
title: 2.5.2 parallel Sections-Konstrukt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 073d0561fe4bfbb96ed88681a077da6fc985c963
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402329"
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