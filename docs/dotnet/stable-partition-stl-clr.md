---
title: "stable_partition (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stable_partition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stable_partition-Funktion [STL/CLR]"
ms.assetid: b82c194c-ae38-4afb-b255-a95a4c2b3101
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# stable_partition (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassifiziert Elemente in einem Bereich in disjunkte zwei Sätze, wenn diese Elemente kein unäres Prädikat erfüllen, das die direkt vorausgeht, die es nicht erfüllen können und behält die relative Position von entsprechenden Arbeitsaufgaben beibehalten.  
  
## Syntax  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `stable_partition`.  Weitere Informationen finden Sie unter [stable\_partition](../Topic/stable_partition.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)