---
title: Unique_copy (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::unique_copy
dev_langs: C++
helpviewer_keywords: unique_copy function [STL/CLR]
ms.assetid: 37aa5b06-42c5-420d-94c5-00f00ad26471
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ca88897a16a78dcb0f331f2ce56db29ab692a3c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="uniquecopy-stlclr"></a>unique_copy (STL/CLR)
Kopiert Elemente aus einem Quellbereich in einen Zielbereich mit Ausnahmen von doppelten Elementen, die nebeneinander angeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `unique_copy`. Weitere Informationen finden Sie unter [Unique_copy](../standard-library/algorithm-functions.md#unique_copy).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)