---
title: Omp_set_num_threads | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae9dbe52dba47208844b73175f20edcc591a3ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444943"
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads

Die Anzahl der Threads in weiteren Regionen parallel legt fest, es sei denn, durch Überschreiben einer [Num_threads](../../../parallel/openmp/reference/num-threads.md) Klausel.

## <a name="syntax"></a>Syntax

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Parameter

*num_threads*<br/>
Die Anzahl der Threads in den parallelen Bereich.

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [3.1.1 Omp_set_num_threads-Funktion](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

## <a name="example"></a>Beispiel

Finden Sie unter [Omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) ein Beispiel der Verwendung von `omp_set_num_threads`.

## <a name="see-also"></a>Siehe auch

[Funktionen](../../../parallel/openmp/reference/openmp-functions.md)