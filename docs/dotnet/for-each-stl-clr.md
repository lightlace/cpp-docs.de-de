---
title: "for_each (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::for_each"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "for_each-Funktion [STL/CLR]"
ms.assetid: 4c391ecf-cd35-499e-a3f5-35b965e0da9b
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# for_each (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wendet ein angegebenes Funktionsobjekt an jedes Element in einem Terminauftrag innerhalb eines Bereichs und gibt dem Funktionsobjekt zurück.  
  
## Syntax  
  
```  
template<class _InIt, class _Fn1> inline  
    _Fn1 for_each(_InIt _First, _InIt _Last, _Fn1 _Func);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `for_each`.  Weitere Informationen finden Sie unter [for\_each](../Topic/for_each.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)