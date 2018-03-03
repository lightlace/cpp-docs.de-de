---
title: 3.3.1 Omp_get_wtime-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f89a71d1b91a27dfdd0abf13be4a5f0e30b3fd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime-Funktion
Die `omp_get_wtime` Funktion gibt einen Gleitkommawert mit doppelter Genauigkeit in Sekunden seit einigen"in der Vergangenheit" die verstrichene wanduhrzeit gleich.  Die tatsächliche "Zeit in der Vergangenheit" ist ein beliebiger, aber es wird sichergestellt, dass nicht so ändern Sie während der Ausführung der Anwendung. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 Es wird erwartet, dass die Funktion verwendet wird, um verstrichene Zeiten zu messen, wie im folgenden Beispiel gezeigt:  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Die Häufigkeit zurückgegeben sind "threadspezifisches Zeiten", indem die dafür vorgesehen ist, dass sie nicht erforderlich sind, für die Threads, die für die Teilnahme an einer Anwendung Global konsistent sein.