---
title: 'hash_multimap:: hash_multimap (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::hash_multimap
dev_langs:
- C++
helpviewer_keywords:
- hash_multimap member [STL/CLR]
ms.assetid: a1d576a7-5dc7-4ad9-abef-ee7a13caaec3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 295b9f07911b672f0192d5f3db23ec4570e88982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimaphashmultimap-stlclr"></a>hash_multimap::hash_multimap (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
hash_multimap();  
explicit hash_multimap(key_compare^ pred);  
hash_multimap(key_compare^ pred, hasher^ hashfn);  
hash_multimap(hash_multimap<Key, Mapped>% right);  
hash_multimap(hash_multimap<Key, Mapped>^ right);  
template<typename InIter>  
    hash_multimaphash_multimap(InIter first, InIter last);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multimap(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `hash_multimap();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente mit der standardmäßigen Reihenfolge Prädikat `key_compare()`, und klicken Sie mit der Standard-Hashfunktion. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `explicit hash_multimap(key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat und die Standard-Hashfunktion.  
  
 Der Konstruktor:  
  
 `hash_multimap(key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`, und bei der Hashfunktion `hashfn`. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_multimap(hash_multimap<Key, Mapped>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Hash_multimap-Objekt gesteuert wird `right`, mit der Sortierung standardprädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_multimap(hash_multimap<Key, Mapped>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Hash_multimap-Objekt gesteuert wird `right`, mit der Sortierung standardprädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der angegebenen Reihenfolge Prädikat und die Standard-Hashfunktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_multimap(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat `pred`, und bei der Hashfunktion `hashfn`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion beschrieben.  
  
 Der Konstruktor:  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegt `right`, mit der Sortierung Prädikat `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der angegebenen Reihenfolge Prädikat und Standard-Hashfunktion beschrieben.  
  
 Der Konstruktor:  
  
 `hash_multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit der Sortierung Prädikat `pred`, und bei der Hashfunktion `hashfn`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion beschrieben.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
// construct an empty container   
    Myhash_multimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multimap c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c2h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multimap c3(c1.begin(), c1.end());   
    for each (Myhash_multimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multimap c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c4h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3);   
    for each (Myhash_multimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Myhash_multimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multimap c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Myhash_multimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multimap::hasher(&myfun));   
    for each (Myhash_multimap::value_type elem in c6h)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multimap c7(c4);   
    for each (Myhash_multimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Myhash_multimap c8(%c3);   
    for each (Myhash_multimap::value_type elem in c8)   
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
 [hash_multimap-Element (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::generic_container (STL/CLR)](../dotnet/hash-multimap-generic-container-stl-clr.md)   
 [hash_multimap::operator= (STL/CLR)](../dotnet/hash-multimap-operator-assign-stl-clr.md)