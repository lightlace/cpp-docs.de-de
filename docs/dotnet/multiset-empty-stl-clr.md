---
title: "multiset::empty (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "empty-Member [STL/CLR]"
ms.assetid: 59ec9cc4-cc72-4082-9ab2-49b49980e681
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# multiset::empty (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, dass keine Elemente vorhanden sind.  
  
## Syntax  
  
```  
bool empty();  
```  
  
## Hinweise  
 Die Memberfunktionsrückgaben true für eine leere gesteuerte Sequenz.  Es ist zu [multiset::size](../dotnet/multiset-size-stl-clr.md)`() == 0`.  Sie verwenden sie, um zu testen, ob das Multiset leer ist.  
  
## Beispiel  
  
```  
// cliext_multiset_empty.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**size\(\) \= 3**  
**empty\(\) \= False**  
**size\(\) \= 0**  
**empty\(\) \= True**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::size](../dotnet/multiset-size-stl-clr.md)