---
title: Wenn (OpenMP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4aaad878040534fd198bcdf4a93d7820fd89adc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404812"
---
# <a name="if-openmp"></a>if (OpenMP)

Gibt an, ob eine Schleife parallel oder seriell ausgeführt werden soll.

## <a name="syntax"></a>Syntax

```
if(expression)
```

### <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Ein ganzzahliger Ausdruck, der, wenn er (ungleich null), "true" ausgewertet wird der Code in den parallelen Bereich zur parallelen Ausführung verursacht. Wenn der Ausdruck "false" (null) ergibt, wird der parallele Bereich seriell (von einem einzelnen Thread) ausgeführt.

## <a name="remarks"></a>Hinweise

`if` gilt für die folgenden Anweisungen:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)

Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).

## <a name="example"></a>Beispiel

```
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="see-also"></a>Siehe auch

[Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)