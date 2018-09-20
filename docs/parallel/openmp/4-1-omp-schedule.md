---
title: 4.1 OMP_SCHEDULE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0dce411-2351-4ee9-a1cc-c0322a58b65c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cbdad5ab56ea6979ae2b5952b092b5e85c7bdfa8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433451"
---
# <a name="41-ompschedule"></a>4.1 OMP_SCHEDULE

**OMP_SCHEDULE** gilt nur für **für** und **für parallele** Direktiven, die den Zeitplantyp **Runtime**. Der Zeitplan Typ und die Block-Größe für alle Schleifen kann zur Laufzeit festgelegt werden, durch Festlegen dieser Umgebungsvariablen, um einen der Zeitplantypen erkannt und ein optionales *Chunk_size*.

Für **für** und **für parallele** Direktiven, die einen Zeitplantyp aufweisen **Runtime**, **OMP_SCHEDULE** wird ignoriert. Der Standardwert für diese Umgebungsvariable wird die Implementierung definiert. Wenn der optionale *Chunk_size* festgelegt ist, wird der Wert muss positiv sein. Wenn *Chunk_size* ist nicht festgelegt ist, wird der Wert 1 wird davon ausgegangen werden, außer im Fall von einem **statische** Zeitplan. Für eine **statische** planen, die standardmäßige Segmentgröße zum Bereich Iteration Schleife geteilt durch die Anzahl der Threads, die angewendet werden, um die Schleife festgelegt ist.

Beispiel:

```
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **für** -Anweisung finden Sie unter [Abschnitt 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) auf Seite "11".

- **für die parallele** -Anweisung finden Sie unter [Abschnitt 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) auf Seite "16".