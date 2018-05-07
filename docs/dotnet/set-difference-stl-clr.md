---
title: Set_difference (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set_difference
dev_langs:
- C++
helpviewer_keywords:
- set_difference function [STL/CLR]
ms.assetid: 47a34d92-53d7-4065-9302-9e2e70e46c4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 057b56c44df50fdd3c59a689650262e5e952f359
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="setdifference-stlclr"></a>set_difference (STL/CLR)
Vereinigt alle Elemente, die zu dem einen, jedoch nicht zu einem anderen sortierten Quellbereich gehören, in einen einzelnen, sortierten Zielbereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `set_difference`. Weitere Informationen finden Sie unter [Set_difference](../standard-library/algorithm-functions.md#set_difference).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)