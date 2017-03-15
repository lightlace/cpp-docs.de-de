---
title: "list::begin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin-Member [STL/CLR]"
ms.assetid: 3431467b-951a-498a-af8d-50f631da1646
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# list::begin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Anfang der kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
iterator begin();  
```  
  
## Hinweise  
 Die Memberfunktion gibt ein Iterator mit wahlfreier Zugriff, der das erste Element der Sequenz, gesteuerten festlegt oder direkt über dem Ende eine leere Sequenz hinaus zurück.  Sie können damit einen Iterator abrufen, der den `current` Anfang der kontrollierten Sequenz bestimmt; der Zustand kann sich jedoch ändern, sobald sich die Länge der kontrollierten Sequenz ändert.  
  
## Beispiel  
  
```  
// cliext_list_begin.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**\*begin\(\) \= "**  
**\*\+\+begin\(\) \= b**  
 **x\-yc**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::end](../dotnet/list-end-stl-clr.md)   
 [list::front](../dotnet/list-front-stl-clr.md)   
 [list::front\_item](../dotnet/list-front-item-stl-clr.md)