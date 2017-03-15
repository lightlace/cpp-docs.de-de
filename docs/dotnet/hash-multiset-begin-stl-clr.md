---
title: "hash_multiset::begin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin-Member [STL/CLR]"
ms.assetid: f03fc205-cbc9-4054-ac6d-41ad526edfea
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::begin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Anfang der kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
iterator begin();  
```  
  
## Hinweise  
 Die Memberfunktion wird ein bidirektionaler Iterator, der das erste Element der Sequenz, gesteuerten festlegt oder direkt über dem Ende eine leere Sequenz hinaus zurück.  Sie können damit einen Iterator abrufen, der den `current` Anfang der kontrollierten Sequenz bestimmt; der Zustand kann sich jedoch ändern, sobald sich die Länge der kontrollierten Sequenz ändert.  
  
## Beispiel  
  
```  
// cliext_hash_multiset_begin.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Myhash_multiset::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**\*begin\(\) \= "**  
**\*\+\+begin\(\) \= b**   
## Anforderungen  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)