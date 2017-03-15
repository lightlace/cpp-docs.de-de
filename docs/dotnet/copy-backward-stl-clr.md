---
title: "copy_backward (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::copy_backward"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "copy_backward-Funktion [STL/CLR]"
ms.assetid: 649db3fd-5a79-44b6-bea9-ecbcbeba1f32
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# copy_backward (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist die Werte von Elementen aus einem Quellbereich einem Zielbereich zu, durchläuft die Quellelementsequenz und weist ihnen rückwärts neue Positionen zu.  
  
## Syntax  
  
```  
template<class _BidIt1, class _BidIt2> inline  
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,  
        _BidIt2 _Dest);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `copy_backward`.  Weitere Informationen finden Sie unter [copy\_backward](../Topic/copy_backward.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)