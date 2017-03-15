---
title: "priority_queue::operator= (STL/CLR)"
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
  - "cliext::priority_queue::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator= Member [STL/CLR]"
ms.assetid: 796b4ad2-3e40-49e8-8462-87460d086fe4
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ersetzt die gesteuerte Sequenz.  
  
## Syntax  
  
```  
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);  
```  
  
#### Parameter  
 right  
 Containeradapter zu kopieren.  
  
## Hinweise  
 Der Member, den Operator `right` zum Objekt kopiert, dann, `*this` zurückgibt.  Sie verwenden sie, um die gesteuerte Sequenz durch eine Kopie der gesteuerten Sequenz in `right` zu ersetzen.  
  
## Beispiel  
  
```  
// cliext_priority_queue_operator_as.cpp   
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
  
// assign to a new container   
    Mypriority_queue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c ein b**  
 **c ein b**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [priority\_queue](../dotnet/priority-queue-stl-clr.md)   
 [priority\_queue::assign](../dotnet/priority-queue-assign-stl-clr.md)