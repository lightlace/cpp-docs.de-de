---
title: "stack::stack (STL/CLR)"
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
  - "cliext::stack::stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "stack-Member [STL/CLR]"
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# stack::stack (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Containeradapterobjekt.  
  
## Syntax  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### Parameter  
 right  
 Objekt für die Kopie.  
  
 umbrochen  
 Eingebundener verwenden Container.  
  
## Hinweise  
 Der Konstruktor:  
  
 `stack();`  
  
 stellt einen leeren umschlossenen Container.  Sie verwenden sie, um eine leere ursprünglichen gesteuerten Sequenz angeben.  
  
 Der Konstruktor:  
  
 `stack(stack<Value, Container>% right);`  
  
 umschlossenen stellt einen Container, die eine Kopie von `right.get_container()`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die vom Stapelobjekt `right` gesteuert wird.  
  
 Der Konstruktor:  
  
 `stack(stack<Value, Container>^ right);`  
  
 umschlossenen stellt einen Container, die eine Kopie von `right->get_container()`.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die vom Stapelobjekt `*right` gesteuert wird.  
  
 Der Konstruktor:  
  
 `explicit stack(container_type% wrapped);`  
  
 verwendet den vorhandenen `wrapped` als Container der umschlossene Container.  Sie verwenden ihn, um einen Stapel von einem vorhandenen Container zu erstellen.  
  
## Beispiel  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
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
 **Header:** \<cliext\/Stapel\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Stapel](../dotnet/stack-stl-clr.md)   
 [stack::assign](../dotnet/stack-assign-stl-clr.md)   
 [stack::generic\_container](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator\=](../dotnet/stack-operator-assign-stl-clr.md)