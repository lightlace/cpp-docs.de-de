---
title: "range_adapter::range_adapter (STL/CLR)"
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
  - "cliext::range_adapter::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter-Member [STL/CLR]"
ms.assetid: b16af13f-3358-4e82-927d-d0d4986bcb18
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# range_adapter::range_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Adapterobjekt.  
  
## Syntax  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### Parameter  
 first  
 Erster Iterator einzubindende.  
  
 last  
 Zweiter Iterator einzubindende.  
  
 right  
 Objekt für die Kopie.  
  
## Hinweise  
 Der Konstruktor:  
  
 `range_adapter();`  
  
 initialisiert die gespeicherten Iteratorpaare mit Standard erstellten Iteratoren.  
  
 Der Konstruktor:  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 initialisiert die gespeicherten Iteratorpaare durch Kopieren der Paare, die in `right` gespeichert werden.  
  
 Der Konstruktor:  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 initialisiert die gespeicherten Iteratorpaare durch Kopieren der Paare, die in `*right` gespeichert werden.  
  
 Der Konstruktor:  
  
 `range_adapter(Iter^ first, last);`  
  
 initialisiert die gespeicherten Iteratorpaare mit `first` und `last`.  
  
## Beispiel  
  
```  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **ein b c**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Adapter\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)   
 [range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)