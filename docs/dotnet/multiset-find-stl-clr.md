---
title: "multiset::find (STL/CLR)"
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
  - "cliext::multiset::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find-Member [STL/CLR]"
ms.assetid: 162c9002-fb34-44f9-8e42-6bacecd0ebbc
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sucht ein Element, der einem angegebenen Schlüssel entspricht.  
  
## Syntax  
  
```  
iterator find(key_type key);  
```  
  
#### Parameter  
 Schlüssel  
 Für zu suchen Schlüsselwert.  
  
## Hinweise  
 Wenn mindestens ein Element in der Sequenz gesteuerten entsprechende Reihenfolge mit `key` festgelegt ist, gibt die Memberfunktion ein Iterator zurück, der eines dieser Elemente festgelegt; andernfalls gibt sie [multiset::end](../dotnet/multiset-end-stl-clr.md)`()` zurück.  Sie verwenden sie, um ein Element in der Sequenz gesteuerten derzeit zu suchen, die einen angegebenen Schlüssel entspricht.  
  
## Beispiel  
  
```  
// cliext_multiset_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **ein b c**  
**suchen Sie A \= False**  
**suchen Sie b \= b**  
**suchen Sie C \= False**   
## **Beschreibung**  
 Beachten Sie, dass `find` nicht unbedingt, das von einigen Element es findet.  
  
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::equal\_range](../dotnet/multiset-equal-range-stl-clr.md)   
 [multiset::lower\_bound](../dotnet/multiset-lower-bound-stl-clr.md)   
 [multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)