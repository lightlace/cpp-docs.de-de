---
title: "queue::get_container (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::get_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_container-Member [STL/CLR]"
ms.assetid: d87e7433-a352-4bea-8041-1ffc03287436
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# queue::get_container (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Greift auf den zugrunde liegenden Container zu.  
  
## Syntax  
  
```  
container_type^ get_container();  
```  
  
## Hinweise  
 Die Memberfunktion wird der zugrunde liegenden Container zurück.  Sie verwenden sie, um die Einschränkungen umgehen, die durch den Containerwrapper entstehen.  
  
## Beispiel  
  
```  
// cliext_queue_get_container.cpp   
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
    return (0);   
    }  
  
```  
  
  **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Warteschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [queue](../dotnet/queue-stl-clr.md)   
 [queue::container\_type](../dotnet/queue-container-type-stl-clr.md)