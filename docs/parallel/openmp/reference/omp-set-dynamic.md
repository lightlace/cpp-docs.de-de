---
title: Omp_set_dynamic | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6032503f0b9ccb7d3492f1337165c9db7ec2113a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373908"
---
# <a name="ompsetdynamic"></a>omp_set_dynamic

Gibt an, dass die Anzahl der Threads, die in nachfolgenden parallelen Bereich zur Verfügung, die von der Laufzeit angepasst werden kann.

## <a name="syntax"></a>Syntax

```
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Parameter

*val*<br/>
Ein Wert, der angibt, ob die Anzahl der Threads, die in nachfolgenden parallelen Bereich zur Verfügung, die von der Laufzeit angepasst werden kann.  Wert ungleich null der Common Language Runtime die Anzahl der Threads, wenn der Wert 0 anpassen kann, wird die Laufzeit die Anzahl der Threads nicht dynamisch angepasst.

## <a name="remarks"></a>Hinweise

Die Anzahl von Threads wird durch festgelegten Wert nie übersteigen [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).

Verwendung [Omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) zum Anzeigen der aktuellen Einstellung des `omp_set_dynamic`.

Die Einstellung für `omp_set_dynamic` überschreibt die Einstellung der [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) -Umgebungsvariablen angegeben.

Weitere Informationen finden Sie unter [3.1.7 Omp_set_dynamic-Funktion](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

## <a name="example"></a>Beispiel

```
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="see-also"></a>Siehe auch

[Funktionen](../../../parallel/openmp/reference/openmp-functions.md)