---
title: "equal_range (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_range-Funktion [STL/CLR]"
ms.assetid: 1b2e76c3-6b52-486d-9785-2639b54277fd
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht ein Paar Positionen in einem Bereich, Rang im ersten kleiner als oder der Entsprechung zur Position eines bestimmten Elements und der zweiten größeren als die Position des Elements, der Sinn möglicherweise die Übereinstimmung oder der Reihenfolge, die verwendet werden, um die Positionen in der Sequenz zu erstellen, durch ein binäres Prädikat angegeben wird.  
  
## Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `equal_range`.  Weitere Informationen finden Sie unter [equal\_range](../Topic/equal_range.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)