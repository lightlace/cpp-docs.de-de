---
title: "set::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size-Member [STL/CLR]"
ms.assetid: f231c515-b07e-4e18-90fd-535b13c2db70
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# set::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt die Anzahl der Elemente.  
  
## Syntax  
  
```  
size_type size();  
```  
  
## Hinweise  
 Die Memberfunktion gesteuerten gibt die Länge der Sequenz zurück.  Sie verwenden sie, um die Anzahl der Elemente in der Sequenz gesteuerten derzeit zu bestimmen.  Wenn alle Elemente, die Sie sich interessieren, geht, ob die Reihenfolge Größe ungleich 0 \(null\) aufweist, finden Sie unter [set::empty](../dotnet/set-empty-stl-clr.md)`()`.  
  
## Beispiel  
  
```  
// cliext_set_size.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**size\(\) \= 3 beginnend mit 3**  
**size\(\) \= 0 nach dem Löschen**  
**size\(\) \= 2, wenn 2 hinzugefügt wurden**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)   
 [set::empty](../dotnet/set-empty-stl-clr.md)