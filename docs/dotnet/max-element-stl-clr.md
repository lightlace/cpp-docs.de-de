---
title: Max_element (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::max_element
dev_langs:
- C++
helpviewer_keywords:
- max_element function [STL/CLR]
ms.assetid: c6274bae-1216-4285-b395-254280253dae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 84fb1fb7a3b99889f5a2926fcdb786316dd5abe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="maxelement-stlclr"></a>max_element (STL/CLR)
Sucht das erste Vorkommen des größten Elements in einem angegebenen Bereich, in dem das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `max_element`. Weitere Informationen finden Sie unter [Max_element](../standard-library/algorithm-functions.md#max_element).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)