---
title: Omp_set_num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_num_threads
dev_langs:
- C++
helpviewer_keywords:
- omp_set_num_threads OpenMP function
ms.assetid: dae0bf3f-cd7a-4413-89de-6149ac1f4fa7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce4768c60480e20a48dd3b41d608216259c81530
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ompsetnumthreads"></a>omp_set_num_threads
Die Anzahl der Threads in nachfolgenden parallele Regionen, legt fest, es sei denn, durch Überschreiben einer [Num_threads](../../../parallel/openmp/reference/num-threads.md) Klausel.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_set_num_threads(  
   int num_threads  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `num_threads`  
 Die Anzahl der Threads in der parallelen Bereich.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [3.1.1 Omp_set_num_threads-Funktion](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md) ein Beispiel der Verwendung von `omp_set_num_threads`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)