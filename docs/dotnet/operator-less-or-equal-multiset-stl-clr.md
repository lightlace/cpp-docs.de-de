---
title: "operator&lt;= (multiset) (STL/CLR)"
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
  - "cliext::multiset::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator<=-Member [STL/CLR]"
ms.assetid: 58eb92fd-eac2-462d-b5e9-582bf95b501b
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt;= (multiset) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Liste kleiner als oder gleicher Vergleich.  
  
## Syntax  
  
```  
template<typename Key>  
    bool operator<=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### Parameter  
 left  
 Linker Container zu vergleichen.  
  
 right  
 Rechter Container zu vergleichen.  
  
## Hinweise  
 Die Operatorfunktion gibt `!(``right` `<` `left``)` zurück.  Sie verwenden sie, um zu testen, ob `left` nicht nach `right` sortiert wird, wenn die beiden Multisets verglichenes Element durch Element sind.  
  
## Beispiel  
  
```  
// cliext_multiset_operator_le.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
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
 [multiset](../dotnet/multiset-stl-clr.md)   
 [operator\=\= \(multiset\)](../dotnet/operator-equality-multiset-stl-clr.md)   
 [operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)   
 [operator\< \(multiset\)](../dotnet/operator-less-than-multiset-stl-clr.md)   
 [operator\>\= \(multiset\)](../dotnet/operator-greater-or-equal-multiset-stl-clr.md)   
 [operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)