---
title: A. 8 angeben von parallelen Abschnitten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d969f1a0e9d9b282104ee00a3b2d06610533ad4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440419"
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Angeben von parallelen Abschnitten

Im folgenden Beispiel (für [Abschnitt 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) auf 14) Funktionen *x-Achse enthält*, *Yaxis*, und *Zaxis* gleichzeitig ausgeführt werden können. Die erste `section` Richtlinie ist optional.  Beachten Sie, dass alle `section` Anweisungen müssen in der lexikalischen Wertebereich angezeigt werden die `parallel sections` zu erstellen.

```
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```