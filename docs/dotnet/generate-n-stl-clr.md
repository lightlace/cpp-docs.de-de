---
title: Generate_n (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::generate_n
dev_langs:
- C++
helpviewer_keywords:
- generate_n function [STL/CLR]
ms.assetid: 2f56e649-7a6f-4861-ae49-d0b25f5cd50c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e0072d3694c058d0951e55b09ee6a2a376cbe94a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generaten-stlclr"></a>generate_n (STL/CLR)
Weist die Werte, die von einem Funktionsobjekt generiert werden, einer angegebenen Anzahl von Elementen eines Bereichs zu und kehrt zu der Position zurück, die direkt nach dem letzten zugewiesenen Wert liegt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `generate_n`. Weitere Informationen finden Sie unter [Generate_n](../standard-library/algorithm-functions.md#generate_n).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)