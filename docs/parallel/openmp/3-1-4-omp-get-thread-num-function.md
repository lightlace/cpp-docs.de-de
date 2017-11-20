---
title: 3.1.4 Omp_get_thread_num-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9beb9e81d767a11b4ca701725ac44cc19cd3c3e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
-   `omp_get_num_threads`funktionieren, finden Sie unter [Abschnitt 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) auf Seite 37.