---
title: Make_heap (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::make_heap
dev_langs:
- C++
helpviewer_keywords:
- make_heap function [STL/CLR]
ms.assetid: bc1bed28-7a26-4540-901d-5584cd117ea1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1446cba1661e11c18b540bcb60dcb8385e74d76
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="makeheap-stlclr"></a>make_heap (STL/CLR)
Konvertiert Elemente aus einem angegebenen Bereich in einen Heap, in dem das erste Element das größte ist und für den ein Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `make_heap`. Weitere Informationen finden Sie unter [Make_heap](../standard-library/algorithm-functions.md#make_heap).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)