---
title: Min (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::min
dev_langs:
- C++
helpviewer_keywords:
- min function [STL/CLR]
ms.assetid: 7a2c82d1-424c-48a9-a944-adcf95511aef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5449af49537a2a7633048415d06217edbc64783d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="min-stlclr"></a>min (STL/CLR)
Vergleicht zwei Objekte und gibt das kleinere der beiden zurück, wobei das Sortierkriterium möglicherweise von einem binären Prädikat angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _Ty> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `min`. Weitere Informationen finden Sie unter [min](../standard-library/algorithm-functions.md#min).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)