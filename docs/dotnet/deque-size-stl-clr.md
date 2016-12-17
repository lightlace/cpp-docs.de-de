---
title: "deque::size (STL/CLR)"
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
  - "cliext::deque::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size-Member [STL/CLR]"
ms.assetid: 81db82c1-7fe7-4eb4-8785-6d36197e4681
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# deque::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt die Anzahl der Elemente.  
  
## Syntax  
  
```  
size_type size();  
```  
  
## Hinweise  
 Die Memberfunktion gesteuerten gibt die Länge der Sequenz zurück.  Sie verwenden sie, um die Anzahl der Elemente in der Sequenz gesteuerten derzeit zu bestimmen.  Wenn alle Elemente, die Sie sich interessieren, geht, ob die Reihenfolge Größe ungleich 0 \(null\) aufweist, finden Sie unter [deque::empty](../dotnet/deque-empty-stl-clr.md)`()`.  
  
## Beispiel  
  
```  
// cliext_deque_size.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
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
 **Header:** \<cliext\/Doppelschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::empty](../dotnet/deque-empty-stl-clr.md)