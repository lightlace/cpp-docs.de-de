---
title: "partial_sum (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::partial_sum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial_sum-Funktion [STL/CLR]"
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# partial_sum (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Berechnet Reihe Summen in einem Eingabebereich beim ersten Element von `i` das Element und speichert das Ergebnis jeder solchen Summe in `i` des Elements eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Summenvorgang durch eine weitere angegebene binäre Operation ersetzt wird.  
  
## Syntax  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die numerische Funktion STL\- `partial_sum`.  Weitere Informationen finden Sie unter [partial\_sum](../Topic/partial_sum.md).  
  
## Anforderungen  
 **Header:** \<cliext\/numerisches\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [numeric](../dotnet/numeric-stl-clr.md)