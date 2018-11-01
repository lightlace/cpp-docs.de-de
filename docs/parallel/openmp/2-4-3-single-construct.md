---
title: 2.4.3 single-Konstrukt
ms.date: 11/04/2016
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
ms.openlocfilehash: 7dda98ee83ee08adc29830a9c4ada71a208705fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466364"
---
# <a name="243-single-construct"></a>2.4.3 single-Konstrukt

Die **einzelne** -Direktive identifiziert ein Konstrukt, das angibt, dass die zugehörigen strukturierte Block von nur einem Thread im Team (nicht unbedingt der master-Thread) ausgeführt wird. Die Syntax der **einzelne** Richtlinie lautet wie folgt:

```
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Die Klausel ist eine der folgenden:

**Private (** *Variablenliste* **)**

**Firstprivate (** *Variablenliste* **)**

**Copyprivate (** *Variablenliste* **)**

**nowait**

Ist eine implizite Barriere nach der **einzelne** erstellen, es sei denn, eine **Nowait** -Klausel angegeben ist.

Einschränkungen für die **einzelne** Richtlinie lauten wie folgt:

- Nur eine einzige **Nowait** Klausel darf sich auf eine **einzelne** Richtlinie.

- Die **Copyprivate** Klausel darf nicht verwendet werden, mit der **Nowait** Klausel.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **private**, **Firstprivate**, und **Copyprivate** Klauseln finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.