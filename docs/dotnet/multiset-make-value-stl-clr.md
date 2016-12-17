---
title: "multiset::make_value (STL/CLR)"
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
  - "cliext::multiset::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value-Member [STL/CLR]"
ms.assetid: 385ded5b-65bf-4806-8c3d-a4129a05f612
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::make_value (STL/CLR)
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
// cliext_multiset_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(Mymultiset::make_value(L'a'));   
    c1.insert(Mymultiset::make_value(L'b'));   
    c1.insert(Mymultiset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)   
 [multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)