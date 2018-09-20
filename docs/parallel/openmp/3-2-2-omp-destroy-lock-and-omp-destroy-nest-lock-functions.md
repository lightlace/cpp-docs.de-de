---
title: 3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7b762614e406e5fb4497ec901ad8f65dae15a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433869"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock- und omp_destroy_nest_lock-Funktionen

Diese Funktionen stellen sicher, dass die Spitzen beim Sperren der Variable *Sperre* ist nicht initialisiert. Es wird folgendes Format verwendet:

```
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Es ist entweder dieser Routinen durch eine Sperre-Variable aufrufen, die nicht initialisiert oder entsperrt ist nicht kompatibel.