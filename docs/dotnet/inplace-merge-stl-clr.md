---
title: "inplace_merge (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::inplace_merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inplace_merge-Funktion [STL/CLR]"
ms.assetid: e6948c03-8c5b-4a7c-915c-0a531946a321
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# inplace_merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kombiniert die Elemente von zwei aufeinander sortierten Bereichen in einen einzelnen sortierten Bereich, in dem das Sortierkriterium möglicherweise durch ein binäres Prädikat angegeben wird.  
  
## Syntax  
  
```  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso, wie die STL\-Funktion `inplace_merge` weitere Informationen, [inplace\_merge](../Topic/inplace_merge.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)