---
title: "adjacent_find (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::adjacent_find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adjacent_find-Funktion"
ms.assetid: 48bf57ea-b128-4d16-97c5-01d8a378369f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# adjacent_find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht zwei benachbarten Elemente, die entweder gleich sind oder eine angegebene Bedingung erfüllen.  
  
## Syntax  
  
```  
template<class _FwdIt> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt adjacent_find(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `adjacent_find`.  Weitere Informationen finden Sie unter [adjacent\_find](../Topic/adjacent_find.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)