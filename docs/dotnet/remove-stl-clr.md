---
title: "remove (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::remove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove-Funktion [STL/CLR]"
ms.assetid: 85a11883-3e25-49aa-b4a0-b2cffd6dc110
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# remove (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eliminiert einen angegebenen Wert von einem angegebenen Bereich, ohne die Reihenfolge der restlichen Elemente zu beeinträchtigen und Ende eines neuen Bereichs zurückzugeben, der aus dem angegebenen Wert frei ist.  
  
## Syntax  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt remove(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `remove`.  Weitere Informationen finden Sie unter [Entfernen](../Topic/remove.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)