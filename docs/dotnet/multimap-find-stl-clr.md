---
title: "multimap::find (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find-Member [STL/CLR]"
ms.assetid: 94b42497-3be4-448c-8de9-0a072ae14fbf
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::find (STL/CLR)
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
 Wenn mindestens ein Element in der Sequenz gesteuerten entsprechende Reihenfolge mit `key` festgelegt ist, gibt die Memberfunktion ein Iterator zurück, der eines dieser Elemente festgelegt; andernfalls gibt sie [multimap::end](../dotnet/multimap-end-stl-clr.md)`()` zurück.  Sie verwenden sie, um ein Element in der Sequenz gesteuerten derzeit zu suchen, die einen angegebenen Schlüssel entspricht.  
  
## Beispiel  
  
```  
// cliext_multimap_find.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Mymultimap::iterator it = c1.find(L'b');   
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
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::equal\_range](../dotnet/multimap-equal-range-stl-clr.md)   
 [multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)   
 [multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)