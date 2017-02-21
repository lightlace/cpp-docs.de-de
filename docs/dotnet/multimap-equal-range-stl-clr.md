---
title: "multimap::equal_range (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_range-Member [STL/CLR]"
ms.assetid: f1008d89-7442-429b-9eca-4ef7ee704766
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# multimap::equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Suchen reichen die mit einem bestimmten Schlüssel.  
  
## Syntax  
  
```  
pair_iter_iter equal_range(key_type _Keyval);  
```  
  
#### Parameter  
 `_Keyval`  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Die Methode gibt ein Paar Iteratoren `-` [multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)`(``_Keyval``),` [multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)`(``_Keyval``)` zurück.  Sie verwenden sie, um den Bereich von Elementen in der gesteuerten Sequenz nur ermitteln, die einen angegebenen Schlüssel übereinstimmen.  
  
## Beispiel  
  
```  
// cliext_multimap_equal_range.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
typedef Mymultimap::pair_iter_iter Pairii;   
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
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" [{0} {1}]",   
            pair1.first->first, pair1.first->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**  
**equal\_range \(L'x leer\) \= True**  
 **\[b 2\]**   
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::count](../dotnet/multimap-count-stl-clr.md)   
 [multimap::find](../dotnet/multimap-find-stl-clr.md)   
 [multimap::lower\_bound](../dotnet/multimap-lower-bound-stl-clr.md)   
 [multimap::upper\_bound](../dotnet/multimap-upper-bound-stl-clr.md)