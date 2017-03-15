---
title: "equal (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::equal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal-Funktion [STL/CLR]"
ms.assetid: 7f271666-2198-4e33-8e03-8b73b376c724
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# equal (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vergleicht das Element mit zwei Bereichen durch Element entweder für die Gleichheit oder Äquivalenz auf eine Weise, die von ein binäres Prädikat angegeben werden.  
  
## Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Pr _Pred);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `equal`.  Weitere Informationen finden Sie unter [equal](../Topic/equal.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)