---
title: A. 28 verwenden der Num_threads-Klausel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26238da1-902c-49b4-9559-0fbc9eaf7f36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fb0111645e1dba42fdd3fa28a885d1ce179ef6f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387915"
---
# <a name="a28---use-of-numthreads-clause"></a>A.28   Verwenden der num_threads-Klausel

Das folgende Beispiel zeigt die `num_threads` Klausel ([Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8"). Die parallelen Bereichs ist mit einem Maximum von 10 Threads ausgeführt.

```
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```