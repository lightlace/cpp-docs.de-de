---
title: 3.1.10 omp_get_nested-Funktion
ms.date: 11/04/2016
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
ms.openlocfilehash: a4db1e21f344f5cc58e2027b0816f9c8fb40b3bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519920"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested-Funktion

Die `omp_get_nested` Funktion gibt einen Wert ungleich NULL, wenn die geschachtelten Parallelität aktiviert ist und 0 zurück, wenn er deaktiviert ist. Weitere Informationen zu geschachtelten Parallelität finden Sie Abschnitt 3.1.9 auf Seite "40". Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_nested(void);
```

Wenn eine Implementierung der geschachtelten Parallelität nicht implementiert werden, gibt diese Funktion immer 0 zurück.