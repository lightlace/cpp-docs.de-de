---
title: "hash_multiset::make_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value-Member [STL/CLR]"
ms.assetid: 33a4df1c-5451-44f2-af2e-a8419f9be3b9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# hash_multiset::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein Wertobjekt.  
  
## Syntax  
  
```  
static value_type make_value(key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 So verwenden Schlüsselwert.  
  
## Hinweise  
 Die Memberfunktion `value_type` gibt ein Objekt zurück, dessen Schlüssel `key` ist.  Sie verwenden sie, um ein Objekt zu erstellen, das zur Verwendung mit verschiedenen anderen Memberfunktionen geeignet ist.  
  
## Beispiel  
  
```  
// cliext_hash_multiset_make_value.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(Myhash_multiset::make_value(L'a'));   
    c1.insert(Myhash_multiset::make_value(L'b'));   
    c1.insert(Myhash_multiset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Myhash_multiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::key\_type](../dotnet/hash-multiset-key-type-stl-clr.md)   
 [hash\_multiset::value\_type](../dotnet/hash-multiset-value-type-stl-clr.md)