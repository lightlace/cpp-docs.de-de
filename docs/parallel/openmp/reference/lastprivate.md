---
title: Lastprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7945edb879d81bb50753619c1206b9da575dbcda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="lastprivate"></a>lastprivate
Gibt an, dass der umschließenden Kontext Version der Variablen festgelegt, wird die private Version der Thread ausgeführt, der letzten Iteration (for-Schleife-Konstrukt) oder der letzte Abschnitt (#pragma Abschnitte wird) gleich.  
  
## <a name="syntax"></a>Syntax  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 `var`  
 Die Variable, die die private Version der Thread ausgeführt, der letzten Iteration (for-Schleife-Konstrukt) oder der letzte Abschnitt (#pragma Abschnitte wird) gleich festgelegt ist.  
  
## <a name="remarks"></a>Hinweise  
 `lastprivate` gilt für die folgenden Direktiven:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.3 Lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Zeitplan](../../../parallel/openmp/reference/schedule.md) ein Beispiel der Verwendung von `lastprivate` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)