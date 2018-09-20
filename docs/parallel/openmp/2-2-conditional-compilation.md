---
title: 2.2 bedingte Kompilierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25b52ce624777efe85e27b8ce5e7941bc2f5dcba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440380"
---
# <a name="22-conditional-compilation"></a>2.2 Bedingte Kompilierung

Die _**OPENMP** Makroname wird durch OpenMP konforme Implementierungen als dezimale Konstante definiert *Yyyymm*, die das Jahr und Monat der genehmigten Spezifikation sein. Dieses Makro muss nicht das Subjekt einer **#define** oder **#undef** -präprozessanweisung.

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Wenn der Anbieter Erweiterungen mit OpenMP definieren, können sie weitere vordefinierte Makros angeben.