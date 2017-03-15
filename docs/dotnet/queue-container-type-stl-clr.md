---
title: "queue::container_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::container_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "container_type-Member [STL/CLR]"
ms.assetid: 118168f9-e5ed-47e2-a4f5-26b0b56e41e1
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# queue::container_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Typ des zugrunde liegenden Containers.  
  
## Syntax  
  
```  
typedef Container value_type;  
```  
  
## Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter `Container`.  
  
## Beispiel  
  
```  
// cliext_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Myqueue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::get\_container](../dotnet/queue-get-container-stl-clr.md)