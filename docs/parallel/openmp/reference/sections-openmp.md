---
title: Abschnitte (OpenMP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- section
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- sections OpenMP directive
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32dab6784e4265432f596b585e098f6a77687117
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421543"
---
# <a name="sections-openmp"></a>sections (OpenMP)

Identifiziert die Codeabschnitte, die auf allen Threads aufgeteilt werden.

## <a name="syntax"></a>Syntax

```
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   } 
}
```

## <a name="arguments"></a>Argumente

*Klausel*<br/>
(Optional) NULL oder mehr Klauseln. Finden Sie im Abschnitt "Hinweise" eine Liste von unterstützten Klauseln **Abschnitte**.

## <a name="remarks"></a>Hinweise

Die **Abschnitte** Richtlinie kann 0 (null) oder mehrere enthalten **Abschnitt** Anweisungen.

Die **Abschnitte** -Anweisung unterstützt die folgenden OpenMP-Klauseln:

- [firstprivate](../../../parallel/openmp/reference/firstprivate.md)

- [lastprivate](../../../parallel/openmp/reference/lastprivate.md)

- [nowait](../../../parallel/openmp/reference/nowait.md)

- [private](../../../parallel/openmp/reference/private-openmp.md)

- [reduction](../../../parallel/openmp/reference/reduction.md)

Wenn **parallele** ebenfalls angegeben wird, `clause` kann jede beliebige Klausel von akzeptiert die **parallele** oder **Abschnitte** -Anweisungen außer `nowait`.

Weitere Informationen finden Sie unter [2.4.2 sections-Konstrukt](../../../parallel/openmp/2-4-2-sections-construct.md).

## <a name="example"></a>Beispiel

```
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="see-also"></a>Siehe auch

[Anweisungen](../../../parallel/openmp/reference/openmp-directives.md)