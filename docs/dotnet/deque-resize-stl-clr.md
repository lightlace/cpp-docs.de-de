---
title: "deque::resize (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize-Member [STL/CLR]"
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# deque::resize (STL/CLR)
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
 Die Memberfunktionen beide sicherstellen, dass [deque::size](../dotnet/deque-size-stl-clr.md)`()` künftig `new_size` zurückgibt.  Wenn die gesteuerte Sequenz länger machen muss, wird die erste Memberfunktion Elemente mit Wert `value_type()` an, während die zweite Memberfunktion Elemente mit Wert `val` anzufügen.  So die gesteuerte Sequenz kürzer effektiv ausführen, Zeit Löschen beiden Memberfunktionen, das das letzte Element [deque::size](../dotnet/deque-size-stl-clr.md)`() -` `new_size` bildet.  Sie verwenden sie, um, dass die gesteuerte Sequenz Größe `new_size` verfügt, entweder durch Einschränkung Innenabstand oder sicherzustellen die aktuelle gesteuerte Sequenz.  
  
## Beispiel  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
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
 **Header:** \<cliext\/Doppelschlange\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::clear](../dotnet/deque-clear-stl-clr.md)   
 [deque::erase](../dotnet/deque-erase-stl-clr.md)   
 [deque::insert](../dotnet/deque-insert-stl-clr.md)