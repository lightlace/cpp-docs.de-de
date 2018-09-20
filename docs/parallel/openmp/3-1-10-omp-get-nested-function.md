---
title: 3.1.10 Omp_get_nested-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d019dd757080bbc87ff7aaab1a8745b2a3156b39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392280"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested-Funktion

Die `omp_get_nested` Funktion gibt einen Wert ungleich NULL, wenn die geschachtelten Parallelität aktiviert ist und 0 zurück, wenn er deaktiviert ist. Weitere Informationen zu geschachtelten Parallelität finden Sie Abschnitt 3.1.9 auf Seite "40". Es wird folgendes Format verwendet:

```
#include <omp.h>
int omp_get_nested(void);
```

Wenn eine Implementierung der geschachtelten Parallelität nicht implementiert werden, gibt diese Funktion immer 0 zurück.