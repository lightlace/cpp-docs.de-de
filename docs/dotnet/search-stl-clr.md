---
title: "search (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::search"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Suchfunktion [STL/CLR]"
ms.assetid: 3317c7f4-9f47-44b8-a7c7-73948a2f83e1
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# search (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht das erste Vorkommen einer Sequenz in eines Zielbereichs, dessen Elemente gleich der in einer bestimmten Sequenz von Elementen sind, und dessen Elemente auf eine Weise angegeben durch ein binäres Prädikat an Elemente in der angegebenen Sequenz entsprechendes sind.  
  
## Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2);  
template<class _FwdIt1, class _FwdIt2, class _Pr> inline  
    _FwdIt1 search(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2, _FwdIt2 _Last2, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `search`.  Weitere Informationen finden Sie unter [search](../Topic/search.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)