---
title: "hash_multiset::operator= (STL/CLR)"
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
  - "cliext::hash_multiset::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator= Member [STL/CLR]"
ms.assetid: 1b4d5b0a-f10f-42f8-b67b-76af51c66baf
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# hash_multiset::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ersetzt die gesteuerte Sequenz.  
  
## Syntax  
  
```  
hash_multiset<Key>% operator=(hash_multiset<Key>% right);  
```  
  
#### Parameter  
 right  
 Container zu kopieren.  
  
## Hinweise  
 Der Member, den Operator `right` zum Objekt kopiert, dann, `*this` zurückgibt.  Sie verwenden sie, um die gesteuerte Sequenz durch eine Kopie der gesteuerten Sequenz in `right` zu ersetzen.  
  
## Beispiel  
  
```  
// cliext_hash_multiset_operator_as.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (Myhash_multiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myhash_multiset c2;   
    c2 = c1;   
// display contents " a b c"   
    for each (Myhash_multiset::value_type elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)