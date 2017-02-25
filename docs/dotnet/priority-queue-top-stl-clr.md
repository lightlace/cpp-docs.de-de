---
title: "priority_queue::top (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::top"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "top-Member [STL/CLR]"
ms.assetid: e45211d5-e6df-4c03-97fd-57afb87af58c
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# priority_queue::top (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Greift auf das höchste Element zu.  
  
## Syntax  
  
```  
reference top();  
```  
  
## Hinweise  
 Die Memberfunktion wird ein Verweis auf den obersten \(höchsten\) gesteuerten Element der Sequenz zurück, die nicht leer sein muss.  Sie verwenden sie, um auf das höchste Element zugreifen, wenn Sie wissen, dass es vorhanden ist.  
  
## Beispiel  
  
```  
// cliext_priority_queue_top.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c ein b**  
**top\(\) \= c**  
 **x b ein**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::top\_item](../dotnet/priority-queue-top-item-stl-clr.md)