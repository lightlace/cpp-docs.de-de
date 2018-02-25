---
title: Omp_set_lock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_set_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_lock OpenMP function
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 40d56dd19764ac1c252e7c483d7ef6758e2bcb04
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ompsetlock"></a>omp_set_lock
Blöcke thread Ausführung, bis eine Sperre verfügbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_set_lock(  
   omp_lock_t *lock  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `lock`  
 Eine Variable vom Typ [Omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , die mit initialisiert wurde [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [3.2.3 Omp_set_lock- und Omp_set_nest_lock-Funktionen](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).  
  
## <a name="examples"></a>Beispiele  
 Finden Sie unter [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) ein Beispiel der Verwendung von `omp_set_lock`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)