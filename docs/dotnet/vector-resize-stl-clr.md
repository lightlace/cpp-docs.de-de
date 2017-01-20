---
title: "vector::resize (STL/CLR)"
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
  - "cliext::vector::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize-Member [STL/CLR]"
ms.assetid: a3556fbc-67d9-463a-9ffc-cb43ee15657f
caps.latest.revision: 17
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# vector::resize (STL/CLR)
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
 Die Memberfunktionen beide sicherstellen, dass [vector::size](../dotnet/vector-size-stl-clr.md)`()` künftig `new_size` zurückgibt.  Wenn die gesteuerte Sequenz länger machen muss, wird die erste Memberfunktion Elemente mit Wert `value_type()` an, während die zweite Memberfunktion Elemente mit Wert `val` anzufügen.  So die gesteuerte Sequenz kürzer effektiv ausführen, Zeit Löschen beiden Memberfunktionen, das das letzte Element [vector::size](../dotnet/vector-size-stl-clr.md)`() -` `new_size` bildet.  Sie verwenden sie, um, dass die gesteuerte Sequenz Größe `new_size` verfügt, entweder durch Einschränkung Innenabstand oder sicherzustellen die aktuelle gesteuerte Sequenz.  
  
## Beispiel  
  
```  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
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
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::clear](../dotnet/vector-clear-stl-clr.md)   
 [vector::erase](../dotnet/vector-erase-stl-clr.md)   
 [vector::insert](../dotnet/vector-insert-stl-clr.md)