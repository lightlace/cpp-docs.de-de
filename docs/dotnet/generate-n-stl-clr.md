---
title: Generate_n (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::generate_n
dev_langs: C++
helpviewer_keywords: generate_n function [STL/CLR]
ms.assetid: 2f56e649-7a6f-4861-ae49-d0b25f5cd50c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 15a6d68913bd64d8f5022efa4344c1e3749451f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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