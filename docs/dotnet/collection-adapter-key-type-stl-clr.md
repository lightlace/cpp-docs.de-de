---
title: "collection_adapter::key_type (STL/CLR)"
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
  - "cliext::collection_adapter::key_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_type-Member [STL/CLR]"
ms.assetid: 71ed32b0-af5b-4bac-ae09-2f5d08f0a79b
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter::key_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Typ einer Wörterbuch\-Schlüssel.  
  
## Syntax  
  
```  
typedef Key key_type;  
```  
  
## Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter `Key`, in einer Spezialisierung für `IDictionary` oder `IDictionary<Value>`; Andernfalls wird sie nicht definiert.  
  
## Beispiel  
  
```  
// cliext_collection_adapter_key_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef cliext::collection_adapter<   
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;   
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;   
int main()   
    {   
    Mymap d1;   
    d1.insert(Mymap::make_value(L'a', 1));   
    d1.insert(Mymap::make_value(L'b', 2));   
    d1.insert(Mymap::make_value(L'c', 3));   
    Mycoll c1(%d1);   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mypair elem in c1)   
        {   
        Mycoll::key_type key = elem.Key;   
        Mycoll::mapped_type value = elem.Value;   
        System::Console::Write(" [{0} {1}]", key, value);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[2\] \[bc 3\]**   
## Anforderungen  
 **Header:** \<cliext\/Adapter\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)   
 [collection\_adapter::mapped\_type](../dotnet/collection-adapter-mapped-type-stl-clr.md)