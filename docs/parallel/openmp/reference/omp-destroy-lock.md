---
title: Omp_destroy_lock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_destroy_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_destroy_lock OpenMP function
ms.assetid: b73ab036-b76f-4e42-82ff-c89db2edf7c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c24f09bbad550633c68c403c89362a293265111
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019925"
---
# <a name="ompdestroylock"></a>omp_destroy_lock
Hebt die Initialisierung einer Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_destroy_lock(  
   omp_lock_t *lock  
);  
```  
  
### <a name="parameters"></a>Parameter
  
*lock*<br/>
Eine Variable vom Typ [Omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , die mit initialisiert wurde [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md) ein Beispiel der Verwendung von `omp_destroy_lock`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)