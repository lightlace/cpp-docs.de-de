---
title: "multiset::rend (STL/CLR)"
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
  - "cliext::multiset::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rend-Member [STL/CLR]"
ms.assetid: db84e142-efa7-4171-bad6-8132f3f5f741
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::rend (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt das Ende der umgekehrten kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
reverse_iterator rend();  
```  
  
## Hinweise  
 Die Memberfunktion gibt einem umgekehrten Iterator zurück, der nur über den Anfang der Sequenz gesteuerten hinaus zeigt.  Demzufolge wird der `end` der umgekehrten Sequenz bestimmt.  Sie können damit einen Iterator abrufen, der das `current` Ende der kontrollierten Sequenz in umgekehrter Reihenfolge bestimmt; der Zustand kann sich jedoch ändern, sobald sich die Länge der kontrollierten Sequenz ändert.  
  
## Beispiel  
  
```  
// cliext_multiset_rend.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**\*\- \-\-rend\(\) \= b**  
**\*\-\-rend\(\) \= "**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::begin](../dotnet/multiset-begin-stl-clr.md)   
 [multiset::end](../dotnet/multiset-end-stl-clr.md)   
 [multiset::rbegin](../dotnet/multiset-rbegin-stl-clr.md)