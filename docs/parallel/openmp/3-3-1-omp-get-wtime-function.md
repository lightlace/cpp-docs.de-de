---
title: 3.3.1 Omp_get_wtime-Funktion | Microsoft-Dokumentation
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
ms.openlocfilehash: 8ec022e9c7e27c848ef535481993dd18dc45f695
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430766"
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime-Funktion

Die `omp_get_wtime` Funktion gibt einen Gleitkommawert mit doppelter Genauigkeit in Sekunden seit einigen"in der Vergangenheit" die verstrichene wanduhrzeit gleich.  Die tatsächliche "Zeit in der Vergangenheit" ist ein beliebiger, aber es ist definitiv nicht ändern, während der Ausführung des Anwendungsprogramms. Es wird folgendes Format verwendet:

```
#include <omp.h>
double omp_get_wtime(void);
```

Es ist davon auszugehen, dass die Funktion zum Messen der verstrichenen Zeit, wie im folgenden Beispiel gezeigt verwendet wird:

```
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Die zurückgegebenen Uhrzeiten sind "pro-Thread Zeit", indem Sie die vorgesehen ist, dass sie nicht erforderlich sind, um global über alle Threads, die Teilnahme an einer Anwendungs hinweg konsistent.