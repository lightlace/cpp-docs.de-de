---
title: Push_heap (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::push_heap
dev_langs: C++
helpviewer_keywords: push_heap function [STL/CLR]
ms.assetid: 184fe1d9-5f75-4c11-adbb-84b6b5c8ecd3
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da6ede7d42f5f431d49951d4e9e69f29ac8541da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pushheap-stlclr"></a>push_heap (STL/CLR)
Fügt ein Element hinzu, das sich am Ende eines Bereichs in einem vorhandenen Heap befindet, der aus den vorherigen Elementen im Bereich besteht.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `push_heap`. Weitere Informationen finden Sie unter [Push_heap](../standard-library/algorithm-functions.md#push_heap).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)