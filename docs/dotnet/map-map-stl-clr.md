---
title: "map::map (STL/CLR)"
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
  - "cliext::map::map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map-Member [STL/CLR]"
ms.assetid: c91f699a-4742-4859-b2b3-c2a01a750bea
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# map::map (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein container\-Objekt.  
  
## Syntax  
  
```  
map();  
explicit map(key_compare^ pred);  
map(map<Key, Mapped>% right);  
map(map<Key, Mapped>^ right);  
template<typename InIter>  
    mapmap(InIter first, InIter last);  
template<typename InIter>  
    map(InIter first, InIter last,  
        key_compare^ pred);  
map(System::Collections::Generic::IEnumerable<GValue>^ right);  
map(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `map();`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Standardreihenfolgenprädikat `key_compare()`.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `explicit map(key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Reihenfolgenprädikat `pred`.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem angegebenen Reihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `map(map<Key, Mapped>% right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``.`[map::begin](../dotnet/map-begin-stl-clr.md)`(),` `right``.`[map::end](../dotnet/map-end-stl-clr.md)`())`, mit dem Standardreihenfolgenprädikat.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz, die eine Kopie der Sequenz, die erfolgen durch das Zuordnungsobjekt `right` gesteuert wird, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `map(map<Key, Mapped>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``->`[map::begin](../dotnet/map-begin-stl-clr.md)`(),` `right``->`[map::end](../dotnet/map-end-stl-clr.md)`())`, mit dem Standardreihenfolgenprädikat.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz, die eine Kopie der Sequenz, die erfolgen durch das Zuordnungsobjekt `right` gesteuert wird, mit dem Standardreihenfolgenprädikat anzugeben.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `map(InIter first, InIter last);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Standardreihenfolgenprädikat.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem Standardreihenfolgenprädikat zu erstellen.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `map(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Reihenfolgenprädikat `pred`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Reihenfolgenprädikat zu erstellen.  
  
 Der Konstruktor:  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right`, mit dem Standardreihenfolgenprädikat festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit dem Standardreihenfolgenprädikat beschrieben wird.  
  
 Der Konstruktor:  
  
 `map(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right`, mit dem Reihenfolgenprädikat `pred` festgelegt wird.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit dem angegebenen Reihenfolgenprädikat beschrieben wird.  
  
## Beispiel  
  
```  
// cliext_map_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
// construct an empty container   
    Mymap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymap c3(c1.begin(), c1.end());   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3);   
    for each (Mymap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymap c7(c4);   
    for each (Mymap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymap c8(%c3);   
    for each (Mymap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **\[1\] \[2\] \[bc 3\]**  
**size\(\) \= 0**  
 **c \[3\] \[2\] \[b1\]**  
 **\[1\] \[2\] \[bc 3\]**  
 **c \[3\] \[2\] \[b1\]**  
 **\[1\] \[2\] \[bc 3\]**  
 **c \[3\] \[2\] \[b1\]**  
 **c \[3\] \[2\] \[b1\]**  
 **\[1\] \[2\] \[bc 3\]**   
## Anforderungen  
 **Header:** \<cliext\/Zuordnung\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [map](../dotnet/map-stl-clr.md)   
 [map::generic\_container](../dotnet/map-generic-container-stl-clr.md)   
 [map::operator\=](../dotnet/map-operator-assign-stl-clr.md)