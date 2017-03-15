---
title: "pop_heap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pop_heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pop_heap-Funktion [STL/CLR]"
ms.assetid: d9bde0ed-2122-4d83-b4b3-f47f6fb3729a
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# pop_heap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Entfernt das größte Element der Vorderseite eines Heaps dem folgenden im \- ZuLAST\-Position Bereich und bildet dann einen neuen Heap von den übrigen Elemente.  
  
## Syntax  
  
```  
template<class _RanIt> inline  
    void pop_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `pop_heap`.  Weitere Informationen finden Sie unter [pop\_heap](../Topic/pop_heap.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)