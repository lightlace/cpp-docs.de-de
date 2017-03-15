---
title: "hash_multimap::to_array (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array-Member [STL/CLR]"
ms.assetid: a7fe11ba-5a0b-4152-b24d-8b142450863c
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multimap::to_array (STL/CLR)
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
// cliext_hash_multimap_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Myhash_multimap::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Myhash_multimap::make_value(L'd', 4));   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Myhash_multimap::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\[1\] \[b 2\] \[3\] \[cd 4\]**  
 **\[1\] \[2\] \[bc 3\]**   
## Anforderungen  
 **Header:** \<cliext\/hash\_map\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)