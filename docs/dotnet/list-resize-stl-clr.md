---
title: "list::resize (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize-Member [STL/CLR]"
ms.assetid: c4b8d41f-a62b-4dbc-8568-0e0a9da24016
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::resize (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ändert die Anzahl der Elemente.  
  
## Syntax  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### Parameter  
 new\_size  
 Neue Größe der gesteuerten Sequenz.  
  
 val  
 Wert des Auffüllungselements.  
  
## Hinweise  
 Die Memberfunktionen beide sicherstellen, dass [list::size](../dotnet/list-size-stl-clr.md)`()` künftig `new_size` zurückgibt.  Wenn die gesteuerte Sequenz länger machen muss, wird die erste Memberfunktion Elemente mit Wert `value_type()` an, während die zweite Memberfunktion Elemente mit Wert `val` anzufügen.  So die gesteuerte Sequenz kürzer effektiv ausführen, Zeit Löschen beiden Memberfunktionen, das das letzte Element [list::size](../dotnet/list-size-stl-clr.md)`() -` `new_size` bildet.  Sie verwenden sie, um, dass die gesteuerte Sequenz Größe `new_size` verfügt, entweder durch Einschränkung Innenabstand oder sicherzustellen die aktuelle gesteuerte Sequenz.  
  
## Beispiel  
  
```  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0 0**  
**size\(\) \= 0**  
 **x x x x x**   
## Anforderungen  
 **Header:** \<cliext\/Liste\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [list](../dotnet/list-stl-clr.md)   
 [list::clear](../dotnet/list-clear-stl-clr.md)   
 [list::erase](../dotnet/list-erase-stl-clr.md)   
 [list::insert](../dotnet/list-insert-stl-clr.md)