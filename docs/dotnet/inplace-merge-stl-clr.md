---
title: Inplace_merge (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::inplace_merge
dev_langs:
- C++
helpviewer_keywords:
- inplace_merge function [STL/CLR]
ms.assetid: e6948c03-8c5b-4a7c-915c-0a531946a321
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 583f2f4399552cf1673cc5acd3b3d5c2233ae962
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129150"
---
# <a name="inplacemerge-stlclr"></a>inplace_merge (STL/CLR)
Kombiniert die Elemente von zwei aufeinander folgenden sortierten Bereichen in einen einzelnen sortierten Bereich, wobei das Sortierkriterium durch ein binäres Prädikat angegeben werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `inplace_merge` Weitere Informationen finden Sie unter [Inplace_merge](../standard-library/algorithm-functions.md#inplace_merge).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)