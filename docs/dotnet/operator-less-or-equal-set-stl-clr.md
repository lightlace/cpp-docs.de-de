---
title: "operator&lt;= (set) (STL/CLR)"
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
  - "cliext::set::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator<=-Member [STL/CLR]"
ms.assetid: acb5997b-cdc1-44d6-80c1-e20b01b4db02
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt;= (set) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Liste kleiner als oder gleicher Vergleich.  
  
## Syntax  
  
```  
template<typename Key>  
    bool operator<=(set<Key>% left,  
        set<Key>% right);  
```  
  
#### Parameter  
 left  
 Linker Container zu vergleichen.  
  
 right  
 Rechter Container zu vergleichen.  
  
## Hinweise  
 Die Operatorfunktion gibt `!(``right` `<` `left``)` zurück.  Sie verwenden sie, um zu testen, ob `left` nicht nach `right` sortiert wird, wenn die beiden Sätze verglichenes Element durch Element sind.  
  
## Beispiel  
  
```  
// cliext_set_operator_le.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
  **ein b c**  
 **ein b d**  
**\[ein b c\] \<\= \[ein b c\] gilt**  
**\[ein b d\] \<\= \[ein b c\] ist falsch**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [set](../dotnet/set-stl-clr.md)   
 [operator\=\= \(set\)](../dotnet/operator-equality-set-stl-clr.md)   
 [operator\!\= \(set\)](../dotnet/operator-inequality-set-stl-clr.md)   
 [operator\< \(set\)](../dotnet/operator-less-than-set-stl-clr.md)   
 [operator\>\= \(set\)](../dotnet/operator-greater-or-equal-set-stl-clr.md)   
 [operator\> \(set\)](../dotnet/operator-greater-than-set-stl-clr.md)