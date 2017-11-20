---
title: "remove_copy (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::remove_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_copy-Funktion [STL/CLR]"
ms.assetid: 602fd8e3-26f7-491f-bf2c-cddf269f9807
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# remove_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert Elemente aus einem Quellbereich einem Zielbereich, dass Elemente eines angegebenen Werts werden kopiert, nicht, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und Ende eines neuen Zielbereichs zurückzugeben.  
  
## Syntax  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `remove_copy`.  Weitere Informationen finden Sie unter [remove\_copy](../Topic/remove_copy.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)