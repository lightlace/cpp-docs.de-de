---
title: 'hash_multiset:: hash_multiset (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::hash_multiset
dev_langs:
- C++
helpviewer_keywords:
- hash_multiset member [STL/CLR]
ms.assetid: 1b224c60-b714-4ed5-9234-79b61b92a953
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 81006e74b98e3bce7a001489723e480f289b6a0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136320"
---
# <a name="hashmultisethashmultiset-stlclr"></a>hash_multiset::hash_multiset (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
hash_multiset();  
explicit hash_multiset(key_compare^ pred);  
hash_multiset(key_compare^ pred, hasher^ hashfn);  
hash_multiset(hash_multiset<Key>% right);  
hash_multiset(hash_multiset<Key>^ right);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_multiset(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `hash_multiset();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente mit der standardmäßigen Reihenfolge Prädikat `key_compare()`, und klicken Sie mit der Standard-Hashfunktion. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `explicit hash_multiset(key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat und die Standard-Hashfunktion.  
  
 Der Konstruktor:  
  
 `hash_multiset(key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`, und bei der Hashfunktion `hashfn`. Sie können damit Geben Sie eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_multiset(hash_multiset<Key>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die von der Hash_multiset-Objekt gesteuert wird `right`, mit der Sortierung standardprädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_multiset(hash_multiset<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die von der Hash_multiset-Objekt gesteuert wird `right`, mit der Sortierung standardprädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_multiset(InIter first, InIter last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der angegebenen Reihenfolge Prädikat und die Standard-Hashfunktion.  
  
 Der Konstruktor:  
  
 `template<typename InIter> hash_multiset(InIter first, InIter last, key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der Sortierung Prädikat `pred`, und bei der Hashfunktion `hashfn`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion.  
  
 Der Konstruktor:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit dem Prädikat Reihenfolge und mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der standardmäßigen Reihenfolge Prädikat und Hash-Funktion beschrieben.  
  
 Der Konstruktor:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegt `right`, mit der Sortierung Prädikat `pred`, und klicken Sie mit der Standard-Hashfunktion. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der angegebenen Reihenfolge Prädikat und Standard-Hashfunktion beschrieben.  
  
 Der Konstruktor:  
  
 `hash_multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred, hasher^ hashfn);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit der Sortierung Prädikat `pred`, und bei der Hashfunktion `hashfn`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der angegebenen Reihenfolge Prädikat und Hash-Funktion beschrieben.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cliext_hash_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
// construct an empty container   
    Myhash_multiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_multiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_multiset c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_multiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_multiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_multiset c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_multiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_multiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_multiset c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_multiset::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_multiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_multiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 a b c  
size() = 0  
 a b c  
size() = 0  
 c b a  
  
 a b c  
 a b c  
 c b a  
  
 a b c  
 a b c  
 c b a  
  
 a b c  
 a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::generic_container (STL/CLR)](../dotnet/hash-multiset-generic-container-stl-clr.md)   
 [hash_multiset::operator= (STL/CLR)](../dotnet/hash-multiset-operator-assign-stl-clr.md)