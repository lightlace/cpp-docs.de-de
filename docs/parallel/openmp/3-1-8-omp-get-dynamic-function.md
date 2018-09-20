---
title: 3.1.8 Omp_get_dynamic-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c30f49eaf91353d6a7cd9bd26e0e10e95cb6acd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426782"
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