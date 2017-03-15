---
title: "hash_multimap::rbegin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin-Member [STL/CLR]"
ms.assetid: f5ce0614-3c73-4cec-9fa2-efadf0fd36c7
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_multimap::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Anfang der umgekehrten kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
reverse_iterator rbegin();  
```  
  
## Hinweise  
 Die Memberfunktion gibt einem umgekehrten Iterator, der das letzte Element der gesteuerten Reihenfolge festgelegt wird, oder direkt über dem Anfang eine leere Sequenz hinaus zurück.  Demzufolge wird der `beginning` der umgekehrten Sequenz bestimmt.  Sie können damit einen Iterator abrufen, der den `current` Anfang der kontrollierten Sequenz in umgekehrter Reihenfolge bestimmt; der Zustand kann sich jedoch ändern, sobald sich die Länge der kontrollierten Sequenz ändert.  
  
## Beispiel  
  
```  
// cliext_hash_multimap_rbegin.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_multimap::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**\*rbegin\(\) \= \[c 3\]**  
**\*\+\+rbegin\(\) \= \[b 2\]**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::begin](../dotnet/hash-multimap-begin-stl-clr.md)   
 [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)   
 [hash\_multimap::rend](../dotnet/hash-multimap-rend-stl-clr.md)