---
title: 3.1.6 Omp_in_parallel-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ba6c35d42f8497869894bd5ec95b83f0c8793f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404617"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel-Funktion

Die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, wenn sie in der dynamischen Wertebereich, einen parallel ausgeführten parallelen Bereichs aufgerufen wird; andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_in_parallel(void);
```

Diese Funktion gibt einen Wert ungleich NULL, wenn der erfolgt innerhalb einer Region parallele Ausführung, einschließlich der verschachtelten Bereiche, die serialisiert werden.