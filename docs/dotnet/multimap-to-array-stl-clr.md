---
title: "multimap::to_array (STL/CLR)"
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
  - "cliext::multimap::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array-Member [STL/CLR]"
ms.assetid: eb4872dd-5e32-4a82-8ad4-37b533eb6814
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::to_array (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert die gesteuerte Sequenz zu einem neuen Array.  
  
## Syntax  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## Hinweise  
 Die Memberfunktion gibt ein Array zurück, das die gesteuerte Sequenz enthält.  Sie verwenden sie, um eine Kopie der gesteuerten Sequenz in der Arrayform zu erhalten.  
  
## Beispiel  
  
```  
// cliext_multimap_to_array.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Mymultimap::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Mymultimap::make_value(L'd', 4));   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Mymultimap::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[b 2\] \[3\] \[cd 4\]**  
 **\[1\] \[2\] \[bc 3\]**   
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multimap](../dotnet/multimap-stl-clr.md)