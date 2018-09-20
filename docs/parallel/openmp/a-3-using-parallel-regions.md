---
title: A. 3 Verwenden von parallelen Bereichen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82bc1655584af300cb2d36a62250595839d74551
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413080"
---
# <a name="a3---using-parallel-regions"></a>A.3   Verwenden von parallelen Bereichen

Die `parallel` Richtlinie ([Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8") in gröbere paralleler Programme verwendet werden kann. Im folgenden Beispiel ist jeder Thread in den parallelen Bereich entscheidet, welcher Teil der globalen Array `x` zum abarbeiten, basierend auf der Thread-Anzahl:

```
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```