---
title: "accumulate (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::accumulate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accumulate-Funktion [STL/CLR]"
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# accumulate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet die Summe aller Elemente in einem angegebenen Gültigkeitsbereich einschließlich einige Anfangswert, indem das Ableiten von aufeinander folgenden partiellen Summen oder berechnet das Ergebnis aufeinander folgender partiellen Ergebnisse, die ähnlich mit einer angegebenen binäre Operation als die Summe erreicht werden.  
  
## Syntax  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die numerische Funktion STL\- `accumulate`.  Weitere Informationen finden Sie unter [accumulate](../Topic/accumulate.md).  
  
## Anforderungen  
 **Header:** \<cliext\/numerisches\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [numeric](../dotnet/numeric-stl-clr.md)