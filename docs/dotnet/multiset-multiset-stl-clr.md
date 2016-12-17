---
title: "multiset::multiset (STL/CLR)"
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
  - "cliext::multiset::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiset-Member [STL/CLR]"
ms.assetid: a6ddb2df-d7cd-4b12-aee7-81da1f67f57f
caps.latest.revision: 16
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein container\-Objekt.  
  
## Syntax  
  
```  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### Parameter  
 first  
 Anfang Einfügen des Bereichs.  
  
 last  
 Ende Einfügen des Bereichs.  
  
 pred  
 Reihenfolgenprädikat für die gesteuerte Sequenz.  
  
 right  
 Objekt oder Bereich Einfüge\-.  
  
## Hinweise  
 Der Konstruktor:  
  
 `multiset();`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Standardreihenfolgenprädikat `key_compare()`.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `explicit multiset(key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Reihenfolgenprädikat `pred`.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem angegebenen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `multiset(multiset<Key>% right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``.`[multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),` `right``.`[multiset::end](../dotnet/multiset-end-stl-clr.md)`())`, mit dem Standardreihenfolgenprädikat.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz, die eine Kopie der Sequenz, die erfolgen durch das multiset\-Objekt `right` gesteuert wird, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `multiset(multiset<Key>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``->`[multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),` `right``->`[multiset::end](../dotnet/multiset-end-stl-clr.md)`())`, mit dem Standardreihenfolgenprädikat.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz, die eine Kopie der Sequenz, die erfolgen durch das multiset\-Objekt `right` gesteuert wird, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `multiset(InIter first, InIter last);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Standardreihenfolgenprädikat.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem Standardreihenfolgenprädikat zu erstellen.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `multiset(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Reihenfolgenprädikat `pred`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Reihenfolgenprädikat zu erstellen.  
  
 Der Konstruktor:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right`, mit dem Standardreihenfolgenprädikat festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit dem Standardreihenfolgenprädikat beschrieben wird.  
  
 Der Konstruktor:  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right`, mit dem Reihenfolgenprädikat `pred` festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit dem angegebenen Reihenfolgenprädikat beschrieben wird.  
  
## Beispiel  
  
```  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **ein b c**  
**size\(\) \= 0**  
 **c a b**  
 **ein b c**  
 **c a b**  
 **ein b c**  
 **c a b**  
 **c a b**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/Satz\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)