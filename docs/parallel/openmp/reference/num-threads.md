---
title: Num_threads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: num_threads
dev_langs: C++
helpviewer_keywords: num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d07c2f59572b5e771013d5162f974d865ed97880
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
  
 `num_threads`gilt für die folgenden Direktiven:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.3 parallel-Konstrukt](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [parallele](../../../parallel/openmp/reference/parallel.md) ein Beispiel der Verwendung von `num_threads` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)