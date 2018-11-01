---
title: 3.3.1 omp_get_wtime-Funktion
ms.date: 11/04/2016
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
ms.openlocfilehash: 544a1bc9a613a2888cb7c5e68e54fdfae1b1c333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460566"
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