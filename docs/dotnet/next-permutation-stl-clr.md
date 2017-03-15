---
title: "next_permutation (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::next_permutation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "next_permutation-Funktion [STL/CLR]"
ms.assetid: e36e821f-4b8d-461b-8074-69cd0175ccec
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# next_permutation (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet die Elemente in einem Bereich neu damit die ursprüngliche Reihenfolge von der lexikografisch nächsthöhere Permutation ersetzt wird, falls vorhanden, wo der Sinn möglicherweise von als Nächstes mit einem binären Prädikat angegeben wird.  
  
## Syntax  
  
```  
template<class _BidIt> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    bool next_permutation(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `next_permutation`.  Weitere Informationen finden Sie unter [next\_permutation](../Topic/next_permutation.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)