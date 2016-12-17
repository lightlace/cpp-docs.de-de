---
title: "priority_queue::size (STL/CLR)"
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
  - "cliext::priority_queue::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size-Member [STL/CLR]"
ms.assetid: 37ef4be3-daac-4b5a-9a00-085863f694e0
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt die Anzahl der Elemente.  
  
## Syntax  
  
```  
size_type size();  
```  
  
## Hinweise  
 Die Memberfunktion gesteuerten gibt die Länge der Sequenz zurück.  Sie verwenden sie, um die Anzahl der Elemente in der Sequenz gesteuerten derzeit zu bestimmen.  Wenn alle Elemente, die Sie sich interessieren, geht, ob die Reihenfolge Größe ungleich 0 \(null\) aufweist, finden Sie unter [priority\_queue::empty](../dotnet/priority-queue-empty-stl-clr.md)`()`.  
  
## Beispiel  
  
```  
// cliext_priority_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **c ein b**  
**size\(\) \= 3 beginnend mit 3**  
**size\(\) \= 2 nach Bringen**  
**size\(\) \= 4, wenn 2 hinzugefügt wurden**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::empty](../dotnet/priority-queue-empty-stl-clr.md)