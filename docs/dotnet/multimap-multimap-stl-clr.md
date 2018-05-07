---
title: 'multimap:: multimap (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::multimap
dev_langs:
- C++
helpviewer_keywords:
- multimap member [STL/CLR]
ms.assetid: cdf9c5dc-774c-424e-aeea-7554643e401c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 84d0243ca39aae230f3cfe42d53fdf33d48b7314
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="multimapmultimap-stlclr"></a>multimap::multimap (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
multimap();  
explicit multimap(key_compare^ pred);  
multimap(multimap<Key, Mapped>% right);  
multimap(multimap<Key, Mapped>^ right);  
template<typename InIter>  
    multimapmultimap(InIter first, InIter last);  
template<typename InIter>  
    multimap(InIter first, InIter last,  
        key_compare^ pred);  
multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 pred  
 Sortierung Prädikat für die gesteuerte Sequenz.  
  
 Rechts  
 Einzufügendes Objekt bzw. einzufügender Bereich.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `multimap();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente mit der standardmäßigen Reihenfolge Prädikat `key_compare()`. Sie können damit eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `explicit multimap(key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`. Sie können damit eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `multimap(multimap<Key, Mapped>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`), mit der standardmäßigen Reihenfolge Prädikat. Verwenden sie eine gesteuerte Sequenz an, die eine Kopie der Sequenz, die von der multimap-Objekt gesteuert wird `right`, mit der standardmäßigen Reihenfolge Prädikat.  
  
 Der Konstruktor:  
  
 `multimap(multimap<Key, Mapped>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`), mit der standardmäßigen Reihenfolge Prädikat. Verwenden sie eine gesteuerte Sequenz an, die eine Kopie der Sequenz, die von der multimap-Objekt gesteuert wird `right`, mit der standardmäßigen Reihenfolge Prädikat.  
  
 Der Konstruktor:  
  
 `template<typename InIter> multimap(InIter first, InIter last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der standardmäßigen Reihenfolge Prädikat. Sie können damit der kontrollierten Sequenz eine Kopie einer anderen Sequenz mit der standardmäßigen Reihenfolge Prädikat erstellen.  
  
 Der Konstruktor:  
  
 `template<typename InIter> multimap(InIter first, InIter last, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit dem Prädikat Reihenfolge `pred`. Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Reihenfolge Prädikat erstellen.  
  
 Der Konstruktor:  
  
 `multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit der standardmäßigen Reihenfolge Prädikat. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der standardmäßigen Reihenfolge Prädikat beschrieben.  
  
 Der Konstruktor:  
  
 `multimap(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit dem Prädikat Reihenfolge `pred`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit dem angegebenen Reihenfolge Prädikat beschrieben.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cliext_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
// construct an empty container   
    Mymultimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultimap c3(c1.begin(), c1.end());   
    for each (Mymultimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymultimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymultimap::value_type>^)%c3);   
    for each (Mymultimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymultimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymultimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultimap c7(c4);   
    for each (Mymultimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymultimap c8(%c3);   
    for each (Mymultimap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 [a 1] [b 2] [c 3]  
size() = 0  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
 [c 3] [b 2] [a 1]  
 [c 3] [b 2] [a 1]  
 [a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::generic_container (STL/CLR)](../dotnet/multimap-generic-container-stl-clr.md)   
 [multimap::operator= (STL/CLR)](../dotnet/multimap-operator-assign-stl-clr.md)