---
title: 3.3.1 Omp_get_wtime-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71296d23df72464ed730713566c95e2403760a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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