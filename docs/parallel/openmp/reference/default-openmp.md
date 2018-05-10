---
title: Standard (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fc39951270138e9bd243172b289e7bd96190f14
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="default-openmp"></a>default (OpenMP)
Gibt das Verhalten des ohne bereichseinschränkung Variablen in einem parallelen Bereich an.  
  
## <a name="syntax"></a>Syntax  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>Hinweise  
 `shared`, die im Endeffekt dasselbe ist wenn die `default` -Klausel nicht angegeben, bedeutet, dass jede Variable in einem parallelen Bereich behandelt werden, als wäre es mit angegeben wurden die [freigegebenen](../../../parallel/openmp/reference/shared-openmp.md) Klausel. `none` bedeutet, dass alle Variablen in einem parallelen Bereich, der nicht mit begrenzt sind verwendet die [private](../../../parallel/openmp/reference/private-openmp.md), [freigegebenen](../../../parallel/openmp/reference/shared-openmp.md), [Verringerung](../../../parallel/openmp/reference/reduction.md), [Firstprivate](../../../parallel/openmp/reference/firstprivate.md), oder [Lastprivate](../../../parallel/openmp/reference/lastprivate.md) -Klausel führt dazu, dass ein Compilerfehler ausgelöst.  
  
 `default` gilt für die folgenden Direktiven:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.5 Standard](../../../parallel/openmp/2-7-2-5-default.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) ein Beispiel der Verwendung von `default`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)