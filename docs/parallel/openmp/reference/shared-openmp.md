---
title: freigegeben (OpenMP) | Microsoft-Dokumentation
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
ms.openlocfilehash: 078d4b01d2c797fa11c3603c79a341f75e11f18c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115475"
---
# <a name="shared-openmp"></a>shared (OpenMP)
Gibt an, dass eine oder mehrere Variablen, die auf allen Threads freigegeben werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
shared(var)  
```  
  
### <a name="parameters"></a>Parameter
  
*var*<br/>
Eine oder mehrere Variablen freigeben. Wenn mehr als eine Variable angegeben ist, trennen Sie Namen durch ein Komma.  
  
## <a name="remarks"></a>Hinweise  
 Eine weitere Möglichkeit zum Teilen von Variablen zwischen Threads ist mit der [Copyprivate](../../../parallel/openmp/reference/copyprivate.md) Klausel.  
  
 `shared` gilt für die folgenden Anweisungen:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.4 freigegebene](../../../parallel/openmp/2-7-2-4-shared.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [private](../../../parallel/openmp/reference/private-openmp.md) ein Beispiel der Verwendung von `shared`.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)