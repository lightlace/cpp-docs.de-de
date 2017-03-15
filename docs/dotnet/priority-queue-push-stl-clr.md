---
title: "priority_queue::push (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::push"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push-Member [STL/CLR]"
ms.assetid: 317d3feb-0688-4658-866b-a26cae060354
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# priority_queue::push (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt ein neues Element hinzu.  
  
## Syntax  
  
```  
void push(value_type val);  
```  
  
## Hinweise  
 Die Memberfunktion wird ein Element mit dem Wert `val` in die gesteuerte Sequenz ein und positioniert die gesteuerte Reihenfolge neu, um die Heapdisziplin zu verarbeiten.  Sie verwenden sie, um ein anderes Element der Warteschlange hinzuzufügen.  
  
## Beispiel  
  
```  
// cliext_priority_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c ein b**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::pop](../dotnet/priority-queue-pop-stl-clr.md)