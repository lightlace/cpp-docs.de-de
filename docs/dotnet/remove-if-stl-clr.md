---
title: "remove_if (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::remove_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_if-Funktion [STL/CLR]"
ms.assetid: de501d3f-965b-4a99-b833-f6fa303fbcdc
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# remove_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eliminiert Elemente, die ein Prädikat aus einem angegebenen Bereich erfüllen, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und Ende eines neuen Bereichs zurückzugeben, der aus dem angegebenen Wert frei ist.  
  
## Syntax  
  
```  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `remove_if`.  Weitere Informationen finden Sie unter [remove\_if](../Topic/remove_if.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)