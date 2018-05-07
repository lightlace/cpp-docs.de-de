---
title: Push_heap (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::push_heap
dev_langs:
- C++
helpviewer_keywords:
- push_heap function [STL/CLR]
ms.assetid: 184fe1d9-5f75-4c11-adbb-84b6b5c8ecd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 12b9763c210eb9aa0480ff51a0be70d60400f6c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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