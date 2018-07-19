---
title: 3.1.4 Omp_get_thread_num-Funktion | Microsoft Docs
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
ms.openlocfilehash: fad749b91470f7834169fe8ed734f1d627aa228e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686070"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num-Funktion
Die `omp_get_thread_num` Funktion gibt die Thread-Anzahl, innerhalb der Teams des Threads, die Ausführung der Funktion. Die Thread-Anzahl liegt zwischen 0 und **omp_get_num_threads()**-1 (einschließlich). Die master-Thread des Teams ist 0.  
  
 Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 Wenn von einem seriellen Region aufgerufen `omp_get_thread_num` gibt 0 zurück. Wenn Sie von innerhalb eines geschachtelten parallelen Bereichs aufgerufen, die serialisiert wird, gibt diese Funktion 0 zurück.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   `omp_get_num_threads` funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.