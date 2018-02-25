---
title: Num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b9d12b8216033b5ffe6499290f1c2b5742152b2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [parallele](../../../parallel/openmp/reference/parallel.md) ein Beispiel der Verwendung von `num_threads` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)