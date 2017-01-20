---
title: "map::find (STL/CLR)"
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
  - "cliext::map::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find-Member [STL/CLR]"
ms.assetid: 779dcbee-d584-4fbd-b788-481e094ece9d
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# map::find (STL/CLR)
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
 Wenn mindestens ein Element in der Sequenz gesteuerten entsprechende Reihenfolge mit `key` festgelegt ist, gibt die Memberfunktion ein Iterator zurück, der eines dieser Elemente festgelegt; andernfalls gibt sie [map::end](../dotnet/map-end-stl-clr.md)`()` zurück.  Sie verwenden sie, um ein Element in der Sequenz gesteuerten derzeit zu suchen, die einen angegebenen Schlüssel entspricht.  
  
## Beispiel  
  
```  
// cliext_map_find.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
  
    Mymap::iterator it = c1.find(L'b');   
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
 [map](../dotnet/map-stl-clr.md)   
 [map::equal\_range](../dotnet/map-equal-range-stl-clr.md)   
 [map::lower\_bound](../dotnet/map-lower-bound-stl-clr.md)   
 [map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)