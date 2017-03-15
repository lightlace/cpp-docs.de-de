---
title: "transform (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::transform"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Transformationsfunktion [STL/CLR]"
ms.assetid: 08940969-6d10-40e4-a35b-68dd801b3949
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# transform (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wendet ein angegebenes Funktionsobjekt an jedes Element in einem Quellbereich oder einem Paar Elemente von zwei Quellbereichen und kopiert die Rückgabewerte des Funktionsobjekts in einen Zielbereich.  
  
## Syntax  
  
```  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `transform`.  Weitere Informationen finden Sie unter [transform](../Topic/transform.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)