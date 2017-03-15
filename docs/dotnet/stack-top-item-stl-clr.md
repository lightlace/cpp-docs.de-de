---
title: "stack::top_item (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::top_item"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "top_item-Member [STL/CLR]"
ms.assetid: 01571acf-4880-44c4-80c4-bd91408a032d
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# stack::top_item (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Greift auf das letzte Element zu.  
  
## Syntax  
  
```  
property value_type top_item;  
```  
  
## Hinweise  
 Die Eigenschaft wird auf das letzte Element der gesteuerten Sequenz zu, die nicht leer sein muss.  Sie verwenden sie, um zu lesen, oder, das letzte Element zu schreiben, wenn Sie es wissen, vorhanden ist.  
  
## Beispiel  
  
```  
// cliext_stack_top_item.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**top\_item \= c**  
 **ein b x**   
## Anforderungen  
 **Header:** \<cliext\/Stapel\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Stapel](../dotnet/stack-stl-clr.md)   
 [stack::top](../dotnet/stack-top-stl-clr.md)