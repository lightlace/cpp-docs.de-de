---
title: Partial_sum (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- partial_sum function [STL/CLR]
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c8141e93d7c8101c9bbfaea08c317748cd44f87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="partialsum-stlclr"></a>partial_sum (STL/CLR)
Berechnet eine Reihe von Summen in einem Eingabebereich vom ersten Element über die `i`th-Element und speichert das Ergebnis jeder Summe im `i`th-Element eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in dem die Sum-Vorgang wird von einem anderen angegebenen binären Vorgang ersetzt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek numerische Funktion `partial_sum`. Weitere Informationen finden Sie unter [Partial_sum](../standard-library/numeric-functions.md#partial_sum).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Numeric >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)