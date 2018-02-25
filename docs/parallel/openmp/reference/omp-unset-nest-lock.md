---
title: Omp_unset_nest_lock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_unset_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_unset_nest_lock OpenMP function
ms.assetid: 1721d061-3f9c-45d7-b479-a665cd0a121d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4facb30dc5f869b5be83f4221ef06312eba41251
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ompunsetnestlock"></a>omp_unset_nest_lock
Gibt eine omp_nest_lock_t-Sperre frei.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_unset_nest_lock(   
   omp_nest_lock_t *lock   
);  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `lock`  
 Eine Variable vom Typ [aufgerufen](../../../parallel/openmp/reference/omp-nest-lock-t.md) , die mit initialisiert wurde [Omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md), im Besitz von Threads und in der Funktion ausgeführt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [3.2.4 Omp_unset_lock and Omp_unset_nest_lock-Funktionen](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) ein Beispiel der Verwendung von `omp_unset_nest_lock`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)