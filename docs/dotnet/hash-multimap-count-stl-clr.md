---
title: "hash_multimap::count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::Count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count-Member [STL/CLR]"
ms.assetid: a4bc5b19-e025-4063-9797-304ab4ba08aa
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# hash_multimap::count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht die Anzahl von Elementen, die einen angegebenen Schlüssel übereinstimmen.  
  
## Syntax  
  
```  
size_type count(key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Die Memberfunktion wird die Anzahl der Elemente in der Sequenz zurück gesteuerten, die entsprechende Reihenfolge mit `key` haben.  Damit können Sie die Anzahl der Elemente in der kontrollierten Sequenz ermitteln, die derzeit einem angegebenen Schlüssel entsprechen.  
  
## Beispiel  
  
```  
// cliext_hash_multimap_count.cpp   
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
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**Anzahl \(L'A\) \= 0**  
**Anzahl \(L'b\) \= 1**  
**Anzahl \(L'C\) \= 0**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::equal\_range](../dotnet/hash-multimap-equal-range-stl-clr.md)