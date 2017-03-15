---
title: "includes (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::includes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includes-Funktion [STL/CLR]"
ms.assetid: 566307f4-92e0-4acc-ba49-caa48f3ec744
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# includes (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Bereich sortierter ganzen enthaltenden Elemente sofort sortierten Bereich enthält, in dem die Reihenfolge oder Äquivalenzkriterium Kleinschreibung zwischen Elementen durch ein binäres Prädikat angegeben wird.  
  
## Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool includes(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `includes`.  Weitere Informationen finden Sie unter [includes](../Topic/includes.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)