---
title: "list::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size-Member [STL/CLR]"
ms.assetid: 409e39fb-4468-44bb-b179-52c90e2fa293
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt die Anzahl der Elemente.  
  
## Syntax  
  
```  
size_type size();  
```  
  
## Hinweise  
 Die Memberfunktion gesteuerten gibt die Länge der Sequenz zurück.  Sie verwenden sie, um die Anzahl der Elemente in der Sequenz gesteuerten derzeit zu bestimmen.  Wenn alle Elemente, die Sie sich interessieren, geht, ob die Reihenfolge Größe ungleich 0 \(null\) aufweist, finden Sie unter [list::empty](../dotnet/list-empty-stl-clr.md)`()`.  
  
## Beispiel  
  
```  
// cliext_list_size.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**size\(\) \= 3 beginnend mit 3**  
**size\(\) \= 0 nach dem Löschen**  
**size\(\) \= 2, wenn 2 hinzugefügt wurden**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::empty](../dotnet/list-empty-stl-clr.md)