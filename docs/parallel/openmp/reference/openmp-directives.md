---
title: OpenMP-Anweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 983a71920e9e7ce390ab8c64e81886db0d459450
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389446"
---
# <a name="openmp-directives"></a>OpenMP-Anweisungen

Enthält Links zu Anweisungen, die in der OpenMP-API verwendet.

Visual C++ unterstützt die folgenden OpenMP-Anweisungen:

|Direktive|Beschreibung|
|---------------|-----------------|
|[atomic](../../../parallel/openmp/reference/atomic.md)|Gibt an, dass eine Speicheradresse, die automatisch aktualisiert werden.|
|[barrier](../../../parallel/openmp/reference/barrier.md)|Synchronisiert alle Threads in einem Team. Alle Threads anhalten die Barriere, bis alle Threads die Barriere ausführen.|
|[critical](../../../parallel/openmp/reference/critical.md)|Gibt an, dass Code nur in einem Thread zu einem Zeitpunkt ausgeführt wird.|
|[flush](../../../parallel/openmp/reference/flush-openmp.md)|Gibt an, dass alle Threads die gleiche Ansicht der Arbeitsspeicher für alle freigegebenen Objekte.|
|[for](../../../parallel/openmp/reference/for-openmp.md)|Bewirkt, dass die Arbeit einer for-Schleife innerhalb eines parallelen Bereichs zwischen Threads aufgeteilt werden.|
|[master](../../../parallel/openmp/reference/master.md)|Gibt an, dass nur die master Threadshould einen Abschnitt des Programms ausgeführt.|
|[Sortiert](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Gibt diesen Code in eine parallele Schleife wie eine sequenzielle Schleife ausgeführt werden soll.|
|[parallel](../../../parallel/openmp/reference/parallel.md)|Definiert einen parallelen Bereich, also Code, die von mehreren Threads gleichzeitig ausgeführt werden.|
|[Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)|Identifiziert die Codeabschnitte, die auf allen Threads aufgeteilt werden.|
|[single](../../../parallel/openmp/reference/single.md)|Sie können angeben, dass ein Abschnitt des Codes in einem einzelnen Thread, der nicht unbedingt die master-Thread ausgeführt werden soll.|
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Gibt an, dass eine Variable einem Thread zugehörig ist.|

## <a name="see-also"></a>Siehe auch

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)