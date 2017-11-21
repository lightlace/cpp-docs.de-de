---
title: Omp_get_dynamic | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_get_dynamic
dev_langs: C++
helpviewer_keywords: omp_get_dynamic OpenMP function
ms.assetid: efa843c5-7266-4a75-8db3-22992663d9db
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3f74f9d8f4f4bcff90c1b8204851814adfe84a4f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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