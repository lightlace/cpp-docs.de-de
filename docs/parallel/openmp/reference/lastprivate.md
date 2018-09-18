---
title: Lastprivate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c87dfc47f7f2554e75567a1de4ea9cb2e06eaa00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028193"
---
# <a name="lastprivate"></a>lastprivate
Gibt an, dass der umschließenden Kontext Version der Variablen ist gleich der privaten Version der Thread der letzten Iteration (for-Schleife-Konstrukt) oder der letzte Abschnitt (#pragma Abschnitte) ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
lastprivate(var)  
```  
  
### <a name="parameters"></a>Parameter
  
*var*<br/>
Die Variable, die gleich der privaten Version der Thread ausgeführt, der letzten Iteration (for-Schleife-Konstrukt) oder der letzte Abschnitt (#pragma Abschnitte wird) festgelegt ist.  
  
## <a name="remarks"></a>Hinweise  
 `lastprivate` gilt für die folgenden Anweisungen:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.3 Lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Zeitplan](../../../parallel/openmp/reference/schedule.md) ein Beispiel der Verwendung von `lastprivate` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)