---
title: Random_shuffle (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::random_shuffle
dev_langs:
- C++
helpviewer_keywords:
- random_shuffle function [STL/CLR]
ms.assetid: 0f9d93e2-f50f-40e6-bbe4-2ca3231a895e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d549270f7dafe288d50958491cc4d25e4c68e2f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="randomshuffle-stlclr"></a>random_shuffle (STL/CLR)
Sortiert eine Sequenz von `N` Elemente in einem Bereich in einer der `N`! möglichen per Zufall ausgewählten Anordnungen neu.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _RanIt> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Fn1> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last, _Fn1% _Func);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `random_shuffle`. Weitere Informationen finden Sie unter [Random_shuffle](../standard-library/algorithm-functions.md#random_shuffle).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)