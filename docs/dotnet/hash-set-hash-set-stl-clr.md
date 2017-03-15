---
title: "hash_set::hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set-Member [STL/CLR]"
ms.assetid: 006414ed-db5a-4c08-ac81-4a8ae57d0aad
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# hash_set::hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein container\-Objekt.  
  
## Syntax  
  
```  
hash_set();  
explicit hash_set(key_compare^ pred);  
hash_set(key_compare^ pred, hasher^ hashfn);  
hash_set(hash_set<Key>% right);  
hash_set(hash_set<Key>^ right);  
template<typename InIter>  
    hash_sethash_set(InIter first, InIter last);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### Parameter  
 first  
 Anfang Einfügen des Bereichs.  
  
 hashfn  
 Hashfunktion für die Zuordnung von Schlüsseln auf die Buckets.  
  
 last  
 Ende Einfügen des Bereichs.  
  
 pred  
 Reihenfolgenprädikat für die gesteuerte Sequenz.  
  
 right  
 Objekt oder Bereich Einfüge\-.  
  
## Hinweise  
 Der Konstruktor:  
  
 `hash_set();`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Standardreihenfolgenprädikat `key_compare()` mit der Standardhashfunktion.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem Standardreihenfolgenprädikat und \-Hashfunktion anzugeben.  
  
 Der Konstruktor:  
  
 `explicit hash_set(key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Reihenfolgenprädikat `pred` mit der Standardhashfunktion.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem angegebenen Reihenfolgenprädikat und der Standardhashfunktion anzugeben.  
  
 Der Konstruktor:  
  
 `hash_set(key_compare^ pred, hasher^ hashfn);`  
  
 initialisiert die gesteuerte Sequenz ohne Elemente, mit dem Reihenfolgenprädikat `pred` mit der Hashfunktion `hashfn`.  Sie verwenden sie, um eine leere gesteuerten ursprünglichen Sequenz, mit dem angegebenen Reihenfolgenprädikat und \-Hashfunktion anzugeben.  
  
 Der Konstruktor:  
  
 `hash_set(hash_set<Key>% right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``.`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` `right``.`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`, mit dem Standardreihenfolgenprädikat und mit der Standardhashfunktion.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die vom hash\_set Objekt `right`, mit dem Standardreihenfolgenprädikat und \-Hashfunktion gesteuert wird.  
  
 Der Konstruktor:  
  
 `hash_set(hash_set<Key>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``right``->`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),` `right``->`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`, mit dem Standardreihenfolgenprädikat und mit der Standardhashfunktion.  Sie verwenden sie, um einer gesteuerten ursprünglichen Sequenz angeben, die eine Kopie dieser Folge ist, die vom hash\_set Objekt `right`, mit dem Standardreihenfolgenprädikat und \-Hashfunktion gesteuert wird.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Standardreihenfolgenprädikat und mit der Standardhashfunktion.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem Standardreihenfolgenprädikat und \-Hashfunktion zu erstellen.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Reihenfolgenprädikat `pred` mit der Standardhashfunktion.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Reihenfolgenprädikat und der Standardhashfunktion zu erstellen.  
  
 Der Konstruktor:  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 initialisiert die gesteuerte Sequenz mit der Sequenz `[``first``,` `last``)`, mit dem Reihenfolgenprädikat `pred` mit der Hashfunktion `hashfn`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Reihenfolgenprädikat und \-Hashfunktion zu erstellen.  
  
 Der Konstruktor:  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right` festgelegt wird, mit dem Standardreihenfolgenprädikat und mit der Standardhashfunktion.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit dem Standardreihenfolgenprädikat und \-Hashfunktion beschrieben wird.  
  
 Der Konstruktor:  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right` festgelegt wird, mit dem Reihenfolgenprädikat `pred` mit der Standardhashfunktion.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit der angegebenen Reihenfolgenprädikat\- und \-Standardhashfunktion beschrieben wird.  
  
 Der Konstruktor:  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 initialisiert die gesteuerte Sequenz mit der Folge, die der Enumerator `right` festgelegt wird, mit dem Reihenfolgenprädikat `pred` mit der Hashfunktion `hashfn`.  Sie verwenden sie, um die gesteuerte Sequenz eine Kopie einer anderen Sequenz erstellen, die von ein Enumerator, mit dem angegebenen Reihenfolgenprädikat und \-Hashfunktion beschrieben wird.  
  
## Beispiel  
  
```  
// cliext_hash_set_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
// construct an empty container   
    Myhash_set c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_set c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_set c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_set c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_set c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_set c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_set c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_set c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_set c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_set c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **ein b c**  
**size\(\) \= 0**  
 **ein b c**  
**size\(\) \= 0**  
 **c a b**  
 **ein b c**  
 **ein b c**  
 **c a b**  
 **ein b c**  
 **ein b c**  
 **c a b**  
 **ein b c**  
 **ein b c**   
## Anforderungen  
 **Header:** \<cliext\/hash\_set\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::generic\_container](../dotnet/hash-set-generic-container-stl-clr.md)   
 [hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)