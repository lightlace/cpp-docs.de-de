---
title: 2.5.1 parallel for-Konstrukt
ms.date: 11/04/2016
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
ms.openlocfilehash: e74fa958a70fb10aadd39ccc6b4e56670bc072b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590332"
---
# <a name="251-parallel-for-construct"></a>2.5.1 parallel for-Konstrukt

Die **für parallele** Richtlinie ist eine Abkürzung für eine **parallele** Bereich, nur eine einzige enthält **für** Richtlinie. Die Syntax der **für parallele** Richtlinie lautet wie folgt:

```
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

Mit dieser Direktive können alle Klauseln der der **parallele** Richtlinie und die **für** , außer die Richtlinie der `nowait` -Klausel, wobei identische Bedeutung und den gleichen Einschränkungen. Die Semantik ist identisch mit explizit angeben, ein **parallele** unmittelbar nach der Richtlinie eine **für** Richtlinie.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **Parallele** -Anweisung finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf 8.

- **für** -Anweisung finden Sie unter [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11".

- Daten-Attribut-Klauseln, finden Sie unter [2.7.2 Datenfreigabe-Attribut Klauseln](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.