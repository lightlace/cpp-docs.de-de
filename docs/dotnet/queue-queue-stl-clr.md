---
title: "queue::queue (STL/CLR)"
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
  - "cliext::queue::queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queue-Member [STL/CLR]"
ms.assetid: 6106c07f-d5eb-4f0b-82df-ee4e2e751047
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# queue::queue (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Containeradapterobjekt.  
  
## Syntax  
  
```  
queue();  
queue(queue<Value, Container>% right);  
queue(queue<Value, Container>^ right);  
explicit queue(container_type% wrapped);  
```  
  
#### Parameter  
 right  
 Objekt für die Kopie.  
  
 umbrochen  
 Eingebundener verwenden Container.  
  
## Hinweise  
 Der Konstruktor:  
  
 `queue();`  
  
 stellt einen leeren umschlossenen Container.  Sie verwenden sie, um eine leere ursprünglichen gesteuerten Sequenz angeben.  
  
 Der Konstruktor:  
  
 `queue(queue<Value, Container>% right);`  
  
 umschlossenen stellt einen Container, die eine Kopie von `right.get_container()`.  Sie verwenden diesen, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die von `right`\- Objekt gesteuert wird.  
  
 Der Konstruktor:  
  
 `queue(queue<Value, Container>^ right);`  
  
 umschlossenen stellt einen Container, die eine Kopie von `right->get_container()`.  Sie verwenden diesen, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die von `*right`\- Objekt gesteuert wird.  
  
 Der Konstruktor:  
  
 `explicit queue(container_type wrapped);`  
  
 verwendet den vorhandenen `wrapped` als Container der umschlossene Container.  Sie verwenden diesen, um eine Warteschlange aus einem vorhandenen Container zu erstellen.  
  
## Beispiel  
  
```  
// cliext_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/list>   
  
typedef cliext::queue<wchar_t> Myqueue;   
typedef cliext::list<wchar_t> Mylist;   
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;   
int main()   
    {   
// construct an empty container   
    Myqueue c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Mylist v2(5, L'x');   
    Myqueue_list c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myqueue_list c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Myqueue_list c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **x x x x x**  
 **x x x x x**  
 **x x x x x**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)   
 [queue::generic\_container](../dotnet/queue-generic-container-stl-clr.md)   
 [queue::operator\=](../dotnet/queue-operator-assign-stl-clr.md)