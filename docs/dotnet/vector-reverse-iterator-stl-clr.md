---
title: "vector::reverse_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator-Member [STL/CLR]"
ms.assetid: 0a90c5ee-a95f-4f71-a027-f1668000ccd4
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# vector::reverse_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Typ eines umgekehrten Iterators für die gesteuerte Sequenz.  
  
## Syntax  
  
```  
typedef T3 reverse_iterator;  
```  
  
## Hinweise  
 Der Typ beschreibt ein Objekt des angegebenen Typs nicht `T3`, das als umgekehrter Iterator für die gesteuerte Sequenz dienen kann.  
  
## Beispiel  
  
```  
// cliext_vector_reverse_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" reversed   
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
  
// alter first element and redisplay   
    rit = c1.rbegin();   
    *rit = L'x';   
    for (; rit != c1.rend(); ++rit)   
        System::Console::Write(" {0}", *rit);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **c a b**  
 **x a b**   
## Anforderungen  
 **Header:** \<cliext\/Vektor\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [Vektor](../dotnet/vector-stl-clr.md)   
 [vector::const\_iterator](../dotnet/vector-const-iterator-stl-clr.md)   
 [vector::const\_reverse\_iterator](../dotnet/vector-const-reverse-iterator-stl-clr.md)   
 [vector::iterator](../dotnet/vector-iterator-stl-clr.md)