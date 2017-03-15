---
title: "replace_copy (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::replace_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "replace_copy-Funktion [STL/CLR]"
ms.assetid: b531b49b-b16d-4b04-8f80-74f43dd496a4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# replace_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüft jedes Element in einem Quellbereich und ersetzt, sofern eines angegebenen Werts beim Kopieren des Ergebnisses in einen neuen Zielbereich entspricht.  
  
## Syntax  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
## Hinweise  
 Diese Funktion verhält sich genauso wie die STL\-Funktion `replace_copy`.  Weitere Informationen finden Sie unter [replace\_copy](../Topic/replace_copy.md).  
  
## Anforderungen  
 **Header:** \<cliext\/Algorithmus\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [algorithm](../dotnet/algorithm-stl-clr.md)