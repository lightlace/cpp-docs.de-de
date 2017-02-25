---
title: "queue::empty (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "empty-Member [STL/CLR]"
ms.assetid: 318ccff9-23eb-4045-8c12-d3ea89159e87
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# queue::empty (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, dass keine Elemente vorhanden sind.  
  
## Syntax  
  
```  
bool empty();  
```  
  
## Hinweise  
 Die Memberfunktionsrückgaben true für eine leere gesteuerte Sequenz.  Sie besteht darin [queue::size](../dotnet/queue-size-stl-clr.md)`() == 0`.  Sie verwenden sie, um zu testen, ob die Warteschlange leer ist.  
  
## Beispiel  
  
```  
// cliext_queue_empty.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**size\(\) \= 3**  
**empty\(\) \= False**  
**size\(\) \= 0**  
**empty\(\) \= True**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::size](../dotnet/queue-size-stl-clr.md)