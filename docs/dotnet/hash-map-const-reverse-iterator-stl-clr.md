---
title: "hash_map::const_reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::const_reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reverse_iterator-Member [STL/CLR]"
ms.assetid: 0c31131a-6eb6-4b14-bab9-ebc8ff25f414
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_map::const_reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Typ eines konstanten umgekehrten Iterators für die gesteuerte Sequenz.  
  
## Syntax  
  
```  
typedef T4 const_reverse_iterator;  
```  
  
## Hinweise  
 Der Typ beschreibt ein Objekt des angegebenen Typs nicht `T4`, das als konstanter umgekehrter Iterator für die gesteuerte Sequenz dienen kann.  
  
## Beispiel  
  
```  
// cliext_hash_map_const_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" reversed   
    Myhash_map::const_reverse_iterator crit = c1.rbegin();   
    for (; crit != c1.rend(); ++crit)   
        System::Console::Write(" [{0} {1}]", crit->first, crit->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c \[3\] \[2\] \[b1\]**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::reverse\_iterator](../dotnet/hash-map-reverse-iterator-stl-clr.md)