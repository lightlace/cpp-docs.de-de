---
title: "hash_multimap::find (STL/CLR)"
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
  - "cliext::hash_multimap::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find-Member [STL/CLR]"
ms.assetid: ce839c5e-b8c5-434e-9cc0-e4c6ee6a6bb3
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multimap::find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht ein Element, der einem angegebenen Schlüssel entspricht.  
  
## Syntax  
  
```  
iterator find(key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Wenn mindestens ein Element in der Sequenz gesteuerten entsprechende Reihenfolge mit `key` festgelegt ist, gibt die Memberfunktion ein Iterator zurück, der eines dieser Elemente festgelegt; andernfalls gibt sie [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()` zurück.  Sie verwenden sie, um ein Element in der Sequenz gesteuerten derzeit zu suchen, die einen angegebenen Schlüssel entspricht.  
  
## Beispiel  
  
```  
// cliext_hash_multimap_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Myhash_multimap::iterator it = c1.find(L'b');   
    System::Console::WriteLine("find {0} = [{1} {2}]",   
        L'b', it->first, it->second);   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**suchen Sie A \= False**  
**Suche b \= \[b 2\]**  
**suchen Sie C \= False**   
## **Beschreibung**  
 Beachten Sie, dass `find` nicht unbedingt, das von einigen Element es findet.  
  
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::equal\_range](../dotnet/hash-multimap-equal-range-stl-clr.md)   
 [hash\_multimap::lower\_bound](../dotnet/hash-multimap-lower-bound-stl-clr.md)   
 [hash\_multimap::upper\_bound](../dotnet/hash-multimap-upper-bound-stl-clr.md)