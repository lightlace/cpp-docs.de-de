---
title: Omp_unset_lock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_unset_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_lock OpenMP function
ms.assetid: 68fcb728-040b-4bad-979e-aaecb9097a4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe6d24c6d4fe6cd1df1eea6f0e575ff5c7947c56
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417045"
---
# <a name="ompunsetlock"></a>omp_unset_lock

Gibt eine Sperre frei.

## <a name="syntax"></a>Syntax

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Eine Variable vom Typ [Omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , die mit initialisiert wurde [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md), im Besitz von Threads und in der Funktion ausgeführt.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

## <a name="example"></a>Beispiel

Finden Sie unter [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) ein Beispiel der Verwendung von `omp_unset_lock`.

## <a name="see-also"></a>Siehe auch

[Funktionen](../../../parallel/openmp/reference/openmp-functions.md)