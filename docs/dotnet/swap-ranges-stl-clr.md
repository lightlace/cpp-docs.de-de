---
title: "swap_ranges (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::swap_ranges"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap_ranges-Funktion [STL/CLR]"
ms.assetid: 3fb39a84-b088-48f1-8bb7-2bbe68b048a9
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# swap_ranges (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vertauscht die Elemente eines Bereichs mit den Elementen von anderen, \- groß Bereich gleicher aus.  
  
## Syntax  
  
```  
template<class _FwdIt1, class _FwdIt2> inline  
    _FwdIt2 swap_ranges(_FwdIt1 _First1, _FwdIt1 _Last1,  
        _FwdIt2 _First2);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `swap_ranges`.  Weitere Informationen finden Sie unter [swap\_ranges](../Topic/swap_ranges.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)