---
title: "list::end (STL/CLR)"
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
  - "cliext::list::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "end-Member [STL/CLR]"
ms.assetid: c3444164-2c6e-4cbd-8765-1ce7d30fc43e
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# list::end (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt das Ende der kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
iterator end();  
```  
  
## Hinweise  
 Die Memberfunktion gibt ein Iterator mit wahlfreier Zugriff zurück, der nur über das Ende der Sequenz gesteuerten hinaus zeigt.  Sie verwenden sie, um ein Iterator abzurufen, der das Ende der Sequenz gesteuerten festgelegt; sein Status nicht nicht ändert, wenn die Länge der Sequenz gesteuerten ändert.  
  
## Beispiel  
  
```  
// cliext_list_end.cpp   
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
  
// inspect last two items   
    cliext::list<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
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
**\*\- \-\-end\(\) \= b**  
**\*\-\-end\(\) \= c**  
 **ein x\-y**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::back](../dotnet/list-back-stl-clr.md)   
 [list::back\_item](../dotnet/list-back-item-stl-clr.md)   
 [list::begin](../dotnet/list-begin-stl-clr.md)