---
title: Swap_ranges (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::swap_ranges
dev_langs:
- C++
helpviewer_keywords:
- swap_ranges function [STL/CLR]
ms.assetid: 3fb39a84-b088-48f1-8bb7-2bbe68b048a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 41f115884bfec33062928d2b74bf0d4545d90dae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="swapranges-stlclr"></a>swap_ranges (STL/CLR)
Vertauscht die Elemente eines Bereichs mit den Elementen eines anderen gleich großen Bereichs.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt2 swap_ranges(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `swap_ranges`. Weitere Informationen finden Sie unter [Swap_ranges](../standard-library/algorithm-functions.md#swap_ranges).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)