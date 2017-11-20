---
title: Typenkonflikt (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::mismatch
dev_langs: C++
helpviewer_keywords: mismatch function [STL/CLR]
ms.assetid: 77876875-44bb-4476-afd9-390da4eaac16
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 373ef101bfd764ccae7b4de8cb11caf11e1ff142
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mismatch-stlclr"></a>mismatch (STL/CLR)
Vergleicht zwei Bereiche elementweise entweder auf Gleichheit oder Äquivalenz, wie von einem binären Prädikat angegeben, und sucht die erste Position, an der ein Unterschied auftritt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
            _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `mismatch`. Weitere Informationen finden Sie unter [Konflikt](../standard-library/algorithm-functions.md#mismatch).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)