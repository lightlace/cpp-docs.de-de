---
title: 3.1.5 omp_get_num_procs-Funktion
ms.date: 11/04/2016
ms.assetid: bbfbf17b-0c68-4ba6-a25d-07c36ecb551f
ms.openlocfilehash: 3c515381bbd9bb654ef1f41a9ecab1bc138ca946
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531221"
---
# <a name="315-ompgetnumprocs-function"></a>3.1.5 omp_get_num_procs-Funktion

Die `omp_get_num_procs` Funktion gibt die Anzahl der Prozessoren, die zum Zeitpunkt für die Anwendung verfügbar sind die Funktion wird aufgerufen. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_num_procs(void);
```