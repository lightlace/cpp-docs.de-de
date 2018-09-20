---
title: 3.1.4 Omp_get_thread_num-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a21a682c051daffde16b3d5cfc63fd2d679c4de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444917"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num-Funktion

Die `omp_get_thread_num` Funktion gibt die Thread-Anzahl, innerhalb der Teams, die Threads, die Ausführung der Funktion. Die Thread-Anzahl liegt zwischen 0 und **omp_get_num_threads()**-1 (einschließlich). Die master-Thread des Teams ist Thread 0.

Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_thread_num(void);
```

Wenn über eine serielle Region aufgerufen `omp_get_thread_num` gibt 0 zurück. Wenn Sie von innerhalb eines geschachtelten parallelen Bereichs aufgerufen, die serialisiert wird, gibt diese Funktion 0 zurück.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- `omp_get_num_threads` funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.