---
title: "hash_map::end (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end-Member [STL/CLR]"
ms.assetid: bda12a48-cc2b-426f-a4e8-992c88f61736
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::end (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt das Ende der kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
iterator end();  
```  
  
## Hinweise  
 Die Memberfunktion wird ein bidirektionaler Iterator zurück, der nur über das Ende der Sequenz gesteuerten hinaus zeigt.  Sie verwenden sie, um ein Iterator abzurufen, der das Ende der Sequenz gesteuerten festgelegt; sein Status nicht nicht ändert, wenn die Länge der Sequenz gesteuerten ändert.  
  
## Beispiel  
  
```  
// cliext_hash_map_end.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect last two items   
    Myhash_map::iterator it = c1.end();   
    --it;   
    --it;   
    System::Console::WriteLine("*-- --end() = [{0} {1}]",   
        it->first, it->second);   
    ++it;   
    System::Console::WriteLine("*--end() = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**\*\- \-\-end\(\) \= \[b 2\]**  
**\*\-\-end\(\) \= \[c 3\]**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::begin](../dotnet/hash-map-begin-stl-clr.md)