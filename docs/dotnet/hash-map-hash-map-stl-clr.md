---
title: 'hash_map:: hash_map (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_map::hash_map
dev_langs: C++
helpviewer_keywords: hash_map member [STL/CLR]
ms.assetid: d65eb3fa-4bf9-4186-95f8-5517c90ef1fa
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e53d52a2d057854bdaf4b5471b548ce39fc86f66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hashmaphashmap-stlclr"></a>hash_map::hash_map (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
hash_map();  
explicit hash_map(key_compare^ pred);  
hash_map(key_compare^ pred, hasher^ hashfn);  
hash_map(hash_map<Key, Mapped>% right);  
hash_map(hash_map<Key, Mapped>^ right);  
template<typename InIter>  
    hash_maphash_map(InIter first, InIter last);  
template<typename InIter>  
    hash_map(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_map(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_map(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 hashfn  
 Hash-Funktion für die Zuordnung von Schlüsseln zu Buckets.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 pred  
 Sortierung Prädikat für die gesteuerte Sequenz.  
  
 Rechts  
 Einzufügendes Objekt bzw. einzufügender Bereich.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `hash_map();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente mit der standardmäßigen Reihenfolge Prädikat `key_compare()`, und klicken Sie mit der Standard-Hashfunktion. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `explicit hash_map(key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat und die Standard-Hashfunktion.  
  
 Der Konstruktor:  
  
 `hash_map(key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`, und bei der Hashfunktion `hashfn`. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_map(hash_map<Key, Mapped>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Hash_map-Objekt gesteuert wird `right`, mit der Sortierung standardprädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_map(hash_map<Key, Mapped>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Hash_map-Objekt gesteuert wird `right`, mit der Sortierung standardprädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_map(InIter first, InIter last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_map(InIter first, InIter last, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der angegebenen Reihenfolge Prädikat und die Standard-Hashfunktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_map(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat `pred`, und bei der Hashfunktion `hashfn`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_map(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion beschrieben.  
  
 Der Konstruktor:  
  
 `hash_map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegt `right`, mit der Sortierung Prädikat `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der angegebenen Reihenfolge Prädikat und Standard-Hashfunktion beschrieben.  
  
 Der Konstruktor:  
  
 `hash_map(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit der Sortierung Prädikat `pred`, und bei der Hashfunktion `hashfn`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion beschrieben.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_map_construct.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
// construct an empty container   
    Myhash_map c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_map c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Myhash_map::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_map c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_map::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (Myhash_map::value_type elem in c2h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_map c3(c1.begin(), c1.end());   
    for each (Myhash_map::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_map c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Myhash_map::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_map c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_map::hasher(&myfun));   
    for each (Myhash_map::value_type elem in c4h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_map c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_map::value_type>^)%c3);   
    for each (Myhash_map::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_map c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_map::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Myhash_map::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_map c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_map::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_map::hasher(&myfun));   
    for each (Myhash_map::value_type elem in c6h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_map c7(c4);   
    for each (Myhash_map::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Myhash_map c8(%c3);   
    for each (Myhash_map::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_map/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::generic_container (STL/CLR)](../dotnet/hash-map-generic-container-stl-clr.md)   
 [hash_map::operator= (STL/CLR)](../dotnet/hash-map-operator-assign-stl-clr.md)