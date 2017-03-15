---
title: "collection_adapter::collection_adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter"
  - "cliext::collection_adapter::collection_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection_adapter-Member [STL/CLR]"
ms.assetid: 7e2bb75b-d735-4135-9523-719683e06fe9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# collection_adapter::collection_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Adapterobjekt.  
  
## Syntax  
  
```  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### Parameter  
 Auflistung  
 BCL\-Handle einzubindende.  
  
 right  
 Objekt für die Kopie.  
  
## Hinweise  
 Der Konstruktor:  
  
 `collection_adapter();`  
  
 initialisiert das gespeicherte Handle mit `nullptr`.  
  
 Der Konstruktor:  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 initialisiert das gespeicherte Handle mit `right``.`[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Der Konstruktor:  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 initialisiert das gespeicherte Handle mit `right``->`[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Der Konstruktor:  
  
 `collection_adapter(Coll^ collection);`  
  
 initialisiert das gespeicherte Handle mit `collection`.  
  
## Beispiel  
  
```  
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **base\(\) NULL \= True**  
 **x x x x x x**  
 **x x x x x x**  
 **x x x x x x**   
## Anforderungen  
 **Header:** \<cliext\/Adapter\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)   
 [collection\_adapter::operator\=](../dotnet/collection-adapter-operator-assign-stl-clr.md)