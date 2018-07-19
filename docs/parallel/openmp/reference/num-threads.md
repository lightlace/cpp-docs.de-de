---
title: Num_threads | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd57950d083c4f89ee2aa5962ad1e07a55a9a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691885"
---
# <a name="numthreads"></a>num_threads
Legt die Anzahl der Threads in einem Team Thread fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `num`  
 Die Anzahl von threads  
  
## <a name="remarks"></a>Hinweise  
 Die `num_threads` -Klausel besitzt die gleiche Funktionalität wie die [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) Funktion.  
  
 `num_threads` gilt für die folgenden Direktiven:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [parallele](../../../parallel/openmp/reference/parallel.md) ein Beispiel der Verwendung von `num_threads` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)