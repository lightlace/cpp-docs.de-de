---
title: "stack::get_container (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::get_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_container-Member [STL/CLR]"
ms.assetid: ba6fc541-fc18-4d1c-8e3f-6baaed427cbb
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# stack::get_container (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Greift auf den zugrunde liegenden Container zu.  
  
## Syntax  
  
```  
container_type^ get_container();  
```  
  
## Hinweise  
 Die Memberfunktion gibt ein Handle für den zugrunde liegenden Container zurück.  Sie verwenden sie, um die Einschränkungen umgehen, die durch den Containerwrapper entstehen.  
  
## Beispiel  
  
```  
// cliext_stack_get_container.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mystack::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Stapel\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Stapel](../dotnet/stack-stl-clr.md)   
 [stack::container\_type](../dotnet/stack-container-type-stl-clr.md)