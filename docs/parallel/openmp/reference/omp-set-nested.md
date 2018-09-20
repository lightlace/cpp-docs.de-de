---
title: Omp_set_nested | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d66c71bdd897471527ead5cc896471bec61193c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409219"
---
# <a name="ompsetnested"></a>omp_set_nested

Ermöglicht geschachtelte Parallelität.

## <a name="syntax"></a>Syntax

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Parameter

*val*<br/>
Wenn ungleich NULL ist, können geschachtelte Parallelität. Bei NULL wird die geschachtelte Parallelität deaktiviert.

## <a name="remarks"></a>Hinweise

Geschachtelte OMP Parallelität kann mit aktiviert werden `omp_set_nested`, oder durch Festlegen der [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) -Umgebungsvariablen angegeben.

Die Einstellung für `omp_set_nested` überschreibt die Einstellung der `OMP_NESTED` -Umgebungsvariablen angegeben.

Wenn aktiviert, kann die Umgebungsvariable ein andernfalls operational Programm unterbrechen, da die Anzahl der Threads beim Schachteln von paralleler Bereichen exponentiell.  Z. B. eine Funktion, die rekursiv 6-Mal klicken Sie mit der Anzahl der Threads OMP auf 4 erfordert 4.096 (4, um die Leistungsfähigkeit von 6) threads im Allgemeinen, die Anzahl der Threads übersteigt die Anzahl der Prozessoren, wird die Leistung Ihrer Anwendung beeinträchtigt. Eine Ausnahme wäre, dass die e/a Anwendungen gebunden.

Verwendung [Omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) zum Anzeigen der aktuellen Einstellung des `omp_set_nested`.

Weitere Informationen finden Sie unter [3.1.9 Omp_set_nested-Funktion](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).

## <a name="example"></a>Beispiel

```
// omp_set_nested.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_nested(1);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_nested( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_nested( ));
        }
}
```

```Output
1
1
```

## <a name="see-also"></a>Siehe auch

[Funktionen](../../../parallel/openmp/reference/openmp-functions.md)