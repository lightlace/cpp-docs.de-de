---
title: Omp_get_nested | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20a7378ba7e7f6dcec55cfe265dd0873bdc1fd38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46371952"
---
# <a name="ompgetnested"></a>omp_get_nested

Gibt einen Wert, der angibt, ob geschachtelte Parallelität aktiviert ist.

## <a name="syntax"></a>Syntax

```
int omp_get_nested( );
```

## <a name="return-value"></a>Rückgabewert

Wenn ungleich NULL, geschachtelte Parallelität aktiviert ist.

## <a name="remarks"></a>Hinweise

Geschachtelte Parallelität wird angegeben, mit [Omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) und [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).

Weitere Informationen finden Sie unter [3.1.10 Omp_get_nested-Funktion](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

## <a name="example"></a>Beispiel

Finden Sie unter [Omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) ein Beispiel der Verwendung von `omp_get_nested`.

## <a name="see-also"></a>Siehe auch

[Funktionen](../../../parallel/openmp/reference/openmp-functions.md)