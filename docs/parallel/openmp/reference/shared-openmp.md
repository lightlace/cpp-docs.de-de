---
title: freigegeben (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Shared
dev_langs:
- C++
helpviewer_keywords:
- shared OpenMP clause
ms.assetid: 7887dc95-67a2-462f-a3a2-8e0632bf5d04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8287f96f80748272e29b22ed5c43c364f4353b86
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691676"
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
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.4 freigegebene](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) ein Beispiel der Verwendung von `shared`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)