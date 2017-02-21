---
title: "multiset::rbegin (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin-Member [STL/CLR]"
ms.assetid: beec0024-9565-4809-86f9-8b2c4e533923
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# multiset::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Anfang der umgekehrten kontrollierten Sequenz fest.  
  
## Syntax  
  
```  
reverse_iterator rbegin();  
```  
  
## Hinweise  
 Die Memberfunktion gibt einem umgekehrten Iterator, der das letzte Element der gesteuerten Reihenfolge festgelegt wird, oder direkt über dem Anfang eine leere Sequenz hinaus zurück.  Demzufolge wird der `beginning` der umgekehrten Sequenz bestimmt.  Sie können damit einen Iterator abrufen, der den `current` Anfang der kontrollierten Sequenz in umgekehrter Reihenfolge bestimmt; der Zustand kann sich jedoch ändern, sobald sich die Länge der kontrollierten Sequenz ändert.  
  
## Beispiel  
  
```  
// cliext_multiset_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**\*rbegin\(\) \= c**  
**\*\+\+rbegin\(\) \= b**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::begin](../dotnet/multiset-begin-stl-clr.md)   
 [multiset::end](../dotnet/multiset-end-stl-clr.md)   
 [multiset::rend](../dotnet/multiset-rend-stl-clr.md)