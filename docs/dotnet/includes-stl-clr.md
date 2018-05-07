---
title: enthält (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::includes
dev_langs:
- C++
helpviewer_keywords:
- includes function [STL/CLR]
ms.assetid: 566307f4-92e0-4acc-ba49-caa48f3ec744
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 34b14f34dd83c405bfcd870314c318587df61134
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="includes-stlclr"></a>includes (STL/CLR)
Testet, ob ein sortierter Bereich alle Elemente enthält, die in einem zweiten sortierten Bereich enthalten sind, wobei das Sortier- oder Äquivalenzkriterium für die Elemente durch ein binäres Prädikat angegeben werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `includes`. Weitere Informationen finden Sie unter [enthält](../standard-library/algorithm-functions.md#includes).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)