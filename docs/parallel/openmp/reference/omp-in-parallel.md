---
title: Omp_in_parallel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_in_parallel
dev_langs:
- C++
helpviewer_keywords:
- omp_in_parallel OpenMP function
ms.assetid: 1f01a1b4-78c5-496a-afb7-a43ecdad83d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ade0b6199d0b56fc124033aeb595fe3de40ba9f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426847"
---
# <a name="ompinparallel"></a>omp_in_parallel

Gibt, die ungleich NULL, wenn innerhalb eines parallelen Bereichs aufgerufen.

## <a name="syntax"></a>Syntax

```
int omp_in_parallel( );
```

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.6 Omp_in_parallel-Funktion](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

## <a name="example"></a>Beispiel

```
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="see-also"></a>Siehe auch

[Funktionen](../../../parallel/openmp/reference/openmp-functions.md)