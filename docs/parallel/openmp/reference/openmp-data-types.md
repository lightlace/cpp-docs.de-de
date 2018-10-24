---
title: OpenMP-Datentypen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP data types
- omp_lock_t
- omp_nest_lock_t
dev_langs:
- C++
helpviewer_keywords:
- OpenMP data types
- omp_lock_t OpenMP data type
- omp_nest_lock_t OpenMP data type
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 254dffebc258867088f738b10a11bf48d31bd0a4
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990062"
---
# <a name="openmp-data-types"></a>OpenMP-Datentypen

Enthält Links zu den Datentypen, die in der OpenMP-API verwendet.

Die Visual C++-Implementierung von der OpenMP-standard umfasst die folgenden Datentypen.

Datentyp                           | Beschreibung
----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[omp_lock_t](#omp-lock-t)           | Ein Typ, der den Status einer Sperre, gibt an, ob die Sperre verfügbar ist oder wenn ein Thread eine Sperre besitzt enthält.
[omp_nest_lock_t](#omp-nest-lock-t) | Ein Typ, der eines der folgenden Angaben zu einer Sperre enthält:, ob die Sperre verfügbar ist, und die Identität des Threads, die Sperre und die Schachtelung Anzahl besitzt.

## <a name="omp-lock-t"></a>omp_lock_t

Ein Typ, der den Status einer Sperre, gibt an, ob die Sperre verfügbar ist oder wenn ein Thread eine Sperre besitzt enthält.

Die folgenden Funktionen verwenden `omp_lock_t`:

- [omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)
- [omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)
- [omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)
- [omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)
- [omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)

Weitere Informationen finden Sie unter [3.2 Lock-Funktionen](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) ein Beispiel der Verwendung von `omp_lock_t`.

## <a name="omp-nest-lock-t"></a>aufgerufen

Ein Typ, der die folgenden Angaben zu einer Sperre enthält:, ob die Sperre verfügbar ist, und die Identität des Threads, die Sperre und die Schachtelung Anzahl besitzt.

Die folgenden Funktionen verwenden `omp_nest_lock_t`:

- [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)
- [omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)
- [omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)
- [omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)
- [omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)

Weitere Informationen finden Sie unter [3.2 Lock-Funktionen](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) ein Beispiel der Verwendung von `omp_nest_lock_t`.
