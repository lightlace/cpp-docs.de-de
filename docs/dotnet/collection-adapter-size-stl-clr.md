---
title: "collection_adapter::size (STL/CLR)"
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
  - "cliext::collection_adapter::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size-Member [STL/CLR]"
ms.assetid: 71866719-9e29-4572-bfb9-60321f2937c5
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermittelt die Anzahl der Elemente.  
  
## Syntax  
  
```  
size_type size();  
```  
  
## Hinweise  
 Die Memberfunktion gesteuerten gibt die Länge der Sequenz zurück.  Sie wird nicht in der Spezialisierung für `IEnumerable` bzw. `IEnumerable<Value>` definiert.  
  
## Beispiel  
  
```  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **x x x x x x**  
**size\(\) \= 6**   
## Anforderungen  
 **Header:** \<cliext\/Adapter\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)