---
title: "multimap::make_value (STL/CLR)"
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
  - "cliext::multimap::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value-Member [STL/CLR]"
ms.assetid: 9ae5ace0-e529-4247-8cd6-4e96c0611a75
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Wertobjekt.  
  
## Syntax  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### Parameter  
 Schlüssel  
 So verwenden Schlüsselwert.  
  
 zugeordnet  
 Zugeordneter Wert zu suchen.  
  
## Hinweise  
 Die Memberfunktion `value_type` gibt ein Objekt zurück, dessen Schlüssel `key` und dessen zugehörige Wert `mapped` ist.  Sie verwenden sie, um ein Objekt zu erstellen, das zur Verwendung mit verschiedenen anderen Memberfunktionen geeignet ist.  
  
## Beispiel  
  
```  
// cliext_multimap_make_value.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**   
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)   
 [multimap::mapped\_type](../dotnet/multimap-mapped-type-stl-clr.md)   
 [multimap::value\_type](../dotnet/multimap-value-type-stl-clr.md)