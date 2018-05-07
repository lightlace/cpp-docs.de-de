---
title: Next_permutation (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::next_permutation
dev_langs:
- C++
helpviewer_keywords:
- next_permutation function [STL/CLR]
ms.assetid: e36e821f-4b8d-461b-8074-69cd0175ccec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 36b21ecabb9ab44f1b5c233cffe6567dc8a99eb8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nextpermutation-stlclr"></a>next_permutation (STL/CLR)
Ordnet die Elemente in einem Bereich neu, damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöheren Permutation ersetzt wird, falls vorhanden, wobei die Bedeutung von „nächsthöher“ durch ein binäres Prädikat angegeben werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `next_permutation`. Weitere Informationen finden Sie unter [Next_permutation](../standard-library/algorithm-functions.md#next_permutation).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)