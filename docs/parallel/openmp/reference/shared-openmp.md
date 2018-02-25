---
title: freigegeben (OpenMP) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90491e6e8b415c79e21b4fa518f7e60327ac823e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="shared-openmp"></a>shared (OpenMP)
Gibt an, dass eine oder mehrere Variablen auf allen Threads freigegeben werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
shared(var)  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `var`  
 Eine weitere Variablen freigeben. Wenn mehr als eine Variable angegeben wird, trennen Sie Namen durch ein Komma.  
  
## <a name="remarks"></a>Hinweise  
 Eine weitere Möglichkeit zum Freigeben von Variablen auf Threads ist mit der [Copyprivate](../../../parallel/openmp/reference/copyprivate.md) Klausel.  
  
 `shared` gilt für die folgenden Direktiven:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.4 freigegebene](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) ein Beispiel der Verwendung von `shared`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)