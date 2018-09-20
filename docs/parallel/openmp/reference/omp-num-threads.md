---
title: OMP_NUM_THREADS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9612eefaf2b5706a4034dc027c0fc43618fd048a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436857"
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS

Legt die maximale Anzahl von Threads in den parallelen Bereich fest, es sei denn, durch außer Kraft gesetzt [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [Num_threads](../../../parallel/openmp/reference/num-threads.md).

## <a name="syntax"></a>Syntax

```
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Parameter

*num*<br/>
Die maximale Anzahl von Threads, die Sie in den parallelen Bereich, bis zu 64 in der Visual C++-Implementierung verwenden möchten.

## <a name="remarks"></a>Hinweise

Die **OMP_NUM_THREADS** Umgebungsvariable kann überschrieben werden, indem die [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) Funktion oder durch [Num_threads](../../../parallel/openmp/reference/num-threads.md).

Der Standardwert von `num` in der Visual C++-Implementierung der OpenMP-Standard ist die Anzahl virtueller Prozessoren, einschließlich CPUs mit Hyperthreading.

Weitere Informationen finden Sie unter [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).

## <a name="example"></a>Beispiel

Der folgende Befehl legt die **OMP_NUM_THREADS** -Umgebungsvariable auf 16:

```
set OMP_NUM_THREADS=16
```

Der folgende Befehl zeigt die aktuelle Einstellung der **OMP_NUM_THREADS** -Umgebungsvariablen angegeben:

```
set OMP_NUM_THREADS
```

## <a name="see-also"></a>Siehe auch

[Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)