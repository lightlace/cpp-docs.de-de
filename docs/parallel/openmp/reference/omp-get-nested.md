---
title: Omp_get_nested | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_get_nested OpenMP function
ms.assetid: e9784847-516e-40d3-89f7-b8b6898d8667
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df6a3fafdb749031ae5e55a58e1e26ccad76985c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetnested"></a>omp_get_nested
Gibt einen Wert, der angibt, ob geschachtelte Parallelität aktiviert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
int omp_get_nested( );  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn ungleich NULL, geschachtelte Parallelität aktiviert ist.  
  
## <a name="remarks"></a>Hinweise  
 Geschachtelte Parallelität wird angegeben, mit [Omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) und [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md).  
  
 Weitere Informationen finden Sie unter [3.1.10 Omp_get_nested-Funktion](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) ein Beispiel der Verwendung von `omp_get_nested`.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../../parallel/openmp/reference/openmp-functions.md)