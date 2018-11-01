---
title: 3.1.6 omp_in_parallel-Funktion
ms.date: 11/04/2016
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
ms.openlocfilehash: 2f251cb994771278c7f4e3f50f01e02126f6f88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482042"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel-Funktion

Die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, wenn sie in der dynamischen Wertebereich, einen parallel ausgeführten parallelen Bereichs aufgerufen wird; andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_in_parallel(void);
```

Diese Funktion gibt einen Wert ungleich NULL, wenn der erfolgt innerhalb einer Region parallele Ausführung, einschließlich der verschachtelten Bereiche, die serialisiert werden.