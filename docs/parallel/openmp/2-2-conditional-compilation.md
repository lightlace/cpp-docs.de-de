---
title: 2.2 Bedingte Kompilierung
ms.date: 11/04/2016
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
ms.openlocfilehash: 9dc107ee9e5328df205d4b6f826f71c23abfb3ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658548"
---
# <a name="22-conditional-compilation"></a>2.2 Bedingte Kompilierung

Die _**OPENMP** Makroname wird durch OpenMP konforme Implementierungen als dezimale Konstante definiert *Yyyymm*, die das Jahr und Monat der genehmigten Spezifikation sein. Dieses Makro muss nicht das Subjekt einer **#define** oder **#undef** -präprozessanweisung.

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Wenn der Anbieter Erweiterungen mit OpenMP definieren, können sie weitere vordefinierte Makros angeben.