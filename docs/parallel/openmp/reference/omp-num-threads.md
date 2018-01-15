---
title: OMP_NUM_THREADS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_NUM_THREADS
dev_langs: C++
helpviewer_keywords: OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5f6af2ff547ddb95b6d4ef6b9c6d353399c17c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
Legt die maximale Anzahl von Threads in den parallelen Bereich, es sei denn, durch Überschreiben [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) oder [Num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `num`  
 Die maximale Anzahl von Threads ab, die in den parallelen Bereich, bis zu 64 in der Visual C++-Implementierung werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die **OMP_NUM_THREADS** -Umgebungsvariable kann überschrieben werden, indem die [Omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) Funktion oder durch [Num_threads](../../../parallel/openmp/reference/num-threads.md).  
  
 Der Standardwert von `num` in der Visual C++-Implementierung des OpenMP-Standards ist die Anzahl virtueller Prozessoren, einschließlich der Hyperthreading-CPUs.  
  
 Weitere Informationen finden Sie unter [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl legt die **OMP_NUM_THREADS** -Umgebungsvariable um 16:  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 Der folgende Befehl zeigt die aktuelle Einstellung der **OMP_NUM_THREADS** -Umgebungsvariablen angegeben:  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Umgebungsvariablen](../../../parallel/openmp/reference/openmp-environment-variables.md)