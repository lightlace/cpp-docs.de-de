---
title: Omp_destroy_nest_lock | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_destroy_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_destroy_nest_lock OpenMP function
ms.assetid: 0ab1352b-668f-43dd-b441-31ec4cc53e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37ac75158705a26b10b077652f51396dcd591740
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104041"
---
# <a name="ompdestroynestlock"></a>omp_destroy_nest_lock
Hebt die Initialisierung einer omp_nest_lock_t-Sperre.  
  
## <a name="syntax"></a>Syntax  
  
```  
void omp_destroy_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
### <a name="parameters"></a>Parameter
  
*lock*<br/>
Eine Variable vom Typ [aufgerufen](../../../parallel/openmp/reference/omp-nest-lock-t.md) , die mit initialisiert wurde [Omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [3.2.2 Omp_destroy_lock- und Omp_destroy_nest_lock-Funktionen](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) ein Beispiel der Verwendung von `omp_destroy_nest_lock`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)