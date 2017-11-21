---
title: Adjacent_find (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::adjacent_find
dev_langs: C++
helpviewer_keywords: adjacent_find function
ms.assetid: 48bf57ea-b128-4d16-97c5-01d8a378369f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1cf088deace9f900007bee500f216fa2fbc8e7b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="adjacentfind-stlclr"></a>adjacent_find (STL/CLR)
Sucht zwei benachbarte Elemente, die entweder gleich sind oder eine angegebene Bedingung erfüllen.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `adjacent_find`. Weitere Informationen finden Sie unter [Adjacent_find](../standard-library/algorithm-functions.md#adjacent_find).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)