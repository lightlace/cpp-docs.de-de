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
ms.openlocfilehash: 97cf6ccad0a3b30c0abfa0076ea9c6a30b205d67
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065199"
---
# <a name="openmp-data-types"></a>OpenMP-Datentypen

Enthält Links zu den Datentypen, die in der OpenMP-API verwendet.

Die Visual C++-Implementierung von der OpenMP-standard umfasst die folgenden Datentypen.

|Datentyp|Beschreibung|
|---------|-----------|
|[omp_lock_t](#omp-lock-t)|Ein Typ, der den Status einer Sperre, gibt an, ob die Sperre verfügbar ist oder wenn ein Thread eine Sperre besitzt enthält.|
|[omp_nest_lock_t](#omp-nest-lock-t)|Ein Typ, der eines der folgenden Angaben zu einer Sperre enthält:, ob die Sperre verfügbar ist, und die Identität des Threads, die Sperre und die Schachtelung Anzahl besitzt.|

## <a name="omp-lock-t"></a>omp_lock_t

Ein Typ, der den Status einer Sperre, gibt an, ob die Sperre verfügbar ist oder wenn ein Thread eine Sperre besitzt enthält.

Die folgenden Funktionen verwenden `omp_lock_t`:

- [omp_init_lock](openmp-functions.md#omp-init-lock)
- [omp_destroy_lock](openmp-functions.md#omp-destroy-lock)
- [omp_set_lock](openmp-functions.md#omp-set-lock)
- [omp_unset_lock](openmp-functions.md#omp-unset-lock)
- [omp_test_lock](openmp-functions.md#omp-test-lock)

Weitere Informationen finden Sie unter [3.2 Lock-Funktionen](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_lock](openmp-functions.md#omp-init-lock) ein Beispiel der Verwendung von `omp_lock_t`.

## <a name="omp-nest-lock-t"></a>aufgerufen

Ein Typ, der die folgenden Angaben zu einer Sperre enthält:, ob die Sperre verfügbar ist, und die Identität des Threads, die Sperre und die Schachtelung Anzahl besitzt.

Die folgenden Funktionen verwenden `omp_nest_lock_t`:

- [omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock)
- [omp_destroy_nest_lock](openmp-functions.md#omp-destroy-nest-lock)
- [omp_set_nest_lock](openmp-functions.md#omp-set-nest-lock)
- [omp_unset_nest_lock](openmp-functions.md#omp-unset-nest-lock)
- [omp_test_nest_lock](openmp-functions.md#omp-test-nest-lock)

Weitere Informationen finden Sie unter [3.2 Lock-Funktionen](../../../parallel/openmp/3-2-lock-functions.md).

### <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_nest_lock](openmp-functions.md#omp-init-nest-lock) ein Beispiel der Verwendung von `omp_nest_lock_t`.
