---
title: Lastprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: lastprivate
dev_langs: C++
helpviewer_keywords: lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7ad36a68078856706a4d1d994e72fd001c36dbaf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 `lastprivate`gilt für die folgenden Direktiven:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Abschnitte](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Weitere Informationen finden Sie unter [2.7.2.3 Lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Zeitplan](../../../parallel/openmp/reference/schedule.md) ein Beispiel der Verwendung von `lastprivate` Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Klauseln](../../../parallel/openmp/reference/openmp-clauses.md)