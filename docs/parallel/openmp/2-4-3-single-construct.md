---
title: 2.4.3 single-Konstrukt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81abf5324c215b9011ecbd774626a213c2eda653
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376498"
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