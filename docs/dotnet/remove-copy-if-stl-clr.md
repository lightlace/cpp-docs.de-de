---
title: "remove_copy_if (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::remove_copy_if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_copy_if-Funktion [STL/CLR]"
ms.assetid: 5307f5fe-b6bb-4968-8da1-fea84ab96655
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# remove_copy_if (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert Elemente aus einem Quellbereich einem Zielbereich, außer dass, ein Prädikat zufrieden stellend, werden kopiert, nicht, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und Ende eines neuen Zielbereichs zurückzugeben.  
  
## Syntax  
  
```  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `remove_copy_if`.  Weitere Informationen finden Sie unter [remove\_copy\_if](../Topic/remove_copy_if.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)