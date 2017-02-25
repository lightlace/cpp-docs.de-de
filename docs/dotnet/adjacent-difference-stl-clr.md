---
title: "adjacent_difference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::adjacent_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adjacent_difference-Funktion"
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# adjacent_difference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Unterschiedvorgang ersetzt wird von anderen, angegebenen binäre Operation.  
  
## Syntax  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die numerische Funktion STL\- `adjacent_difference`.  Weitere Informationen finden Sie unter [adjacent\_difference](../Topic/adjacent_difference.md).  
  
## Anforderungen  
 **Header:** \<cliext\/numerisches\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [numeric](../dotnet/numeric-stl-clr.md)