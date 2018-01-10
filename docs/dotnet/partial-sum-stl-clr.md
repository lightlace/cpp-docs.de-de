---
title: Partial_sum (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::partial_sum
dev_langs: C++
helpviewer_keywords: partial_sum function [STL/CLR]
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7200fbf4adb7866125cfd8956b7b35ad5d5a2657
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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