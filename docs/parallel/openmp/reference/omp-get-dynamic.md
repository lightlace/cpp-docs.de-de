---
title: Omp_get_dynamic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d97cae8091f88c283412b36ef757b03c72f7580d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="ompgetdynamic"></a>omp_get_dynamic
Gibt einen Wert, der angibt, wenn die Anzahl der Threads, die in nachfolgenden parallelen Bereich verfügbar, die von der Laufzeit angepasst werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
int omp_get_dynamic();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wird die dynamische Anpassung der Threads aktiviert.  
  
## <a name="remarks"></a>Hinweise  
 Dynamische Anpassung des Threads wird angegeben, mit [Omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) und [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md).  
  
 Weitere Informationen finden Sie unter [3.1.7 Omp_set_dynamic-Funktion](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) ein Beispiel der Verwendung von `omp_get_dynamic`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)