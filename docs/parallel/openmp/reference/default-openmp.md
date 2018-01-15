---
title: Standard (OpenMP) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: default
dev_langs: C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25b1dd9eb2dcdd5a0a41992ed562ddd290014e25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="default-openmp"></a>default (OpenMP)
Gibt das Verhalten des ohne bereichseinschränkung Variablen in einem parallelen Bereich an.  
  
## <a name="syntax"></a>Syntax  
  
```  
default(shared | none)  
```  
  
## <a name="remarks"></a>Hinweise  
 `shared`, die im Endeffekt dasselbe ist wenn die `default` -Klausel nicht angegeben, bedeutet, dass jede Variable in einem parallelen Bereich behandelt werden, als wäre es mit angegeben wurden die [freigegebenen](../../../parallel/openmp/reference/shared-openmp.md) Klausel. `none`bedeutet, dass alle Variablen in einem parallelen Bereich, der nicht mit begrenzt sind verwendet die [private](../../../parallel/openmp/reference/private-openmp.md), [freigegebenen](../../../parallel/openmp/reference/shared-openmp.md), [Verringerung](../../../parallel/openmp/reference/reduction.md), [Firstprivate](../../../parallel/openmp/reference/firstprivate.md), oder [Lastprivate](../../../parallel/openmp/reference/lastprivate.md) -Klausel führt dazu, dass ein Compilerfehler ausgelöst.  
  
 `default`gilt für die folgenden Direktiven:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.5 Standard](../../../parallel/openmp/2-7-2-5-default.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) ein Beispiel der Verwendung von `default`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)