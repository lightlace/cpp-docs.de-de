---
title: 3.1.8 omp_get_dynamic-Funktion
ms.date: 11/04/2016
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
ms.openlocfilehash: d9476894e5aff4cc7bb9c67fbbeb14d185b65f5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566425"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic-Funktion

Die **Omp_get_dynamic** Funktion gibt einen Wert ungleich NULL zurück, wenn die dynamische Anpassung des Threads ist aktiviert, und andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_dynamic(void);
```

Wenn die dynamische Anpassung der Anzahl der Threads in die Implementierung nicht implementiert werden, gibt diese Funktion immer 0 zurück.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- Eine Beschreibung der dynamischen Thread Anpassung, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.