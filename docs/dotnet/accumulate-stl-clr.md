---
title: Accumulate (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::accumulate
dev_langs:
- C++
helpviewer_keywords:
- accumulate function [STL/CLR]
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 128fe8e46c24b8e0595fe19c0075933d3e5069a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="accumulate-stlclr"></a>accumulate (STL/CLR)
Berechnet die Summe aller Elemente in einem angegebenen Bereich, einschließlich einigen Anfangswerten, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die auf ähnliche Weise mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek numerische Funktion `accumulate`. Weitere Informationen finden Sie unter [ansammeln](../standard-library/numeric-functions.md#accumulate).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Numeric >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)