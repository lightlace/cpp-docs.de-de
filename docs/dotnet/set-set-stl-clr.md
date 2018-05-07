---
title: 'Set:: Set (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::set
dev_langs:
- C++
helpviewer_keywords:
- set member [STL/CLR]
ms.assetid: 0cce8501-92ed-431c-b711-14e0b7be7375
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6de8bb2616cd403e150ace02210e57ed5a019445
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="setset-stlclr"></a>set::set (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
set();  
explicit set(key_compare^ pred);  
set(set<Key>% right);  
set(set<Key>^ right);  
template<typename InIter>  
    setset(InIter first, InIter last);  
template<typename InIter>  
    set(InIter first, InIter last,  
        key_compare^ pred);  
set(System::Collections::Generic::IEnumerable<GValue>^ right);  
set(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `set();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente mit der standardmäßigen Reihenfolge Prädikat `key_compare()`. Sie können damit eine leere gesteuerte Sequenz, mit der standardmäßigen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `explicit set(key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente, mit dem Prädikat Reihenfolge `pred`. Sie können damit eine leere gesteuerte Sequenz, mit der angegebenen Reihenfolge Prädikat angeben.  
  
 Der Konstruktor:  
  
 `set(set<Key>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`), mit der standardmäßigen Reihenfolge Prädikat. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das satzobjekt gesteuert wird `right`, mit der standardmäßigen Reihenfolge Prädikat.  
  
 Der Konstruktor:  
  
 `set(set<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`), mit der standardmäßigen Reihenfolge Prädikat. Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das satzobjekt gesteuert wird `right`, mit der standardmäßigen Reihenfolge Prädikat.  
  
 Der Konstruktor:  
  
 `template<typename InIter> set(InIter first, InIter last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit der standardmäßigen Reihenfolge Prädikat. Sie können damit der kontrollierten Sequenz eine Kopie einer anderen Sequenz mit der standardmäßigen Reihenfolge Prädikat erstellen.  
  
 Der Konstruktor:  
  
 `template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`), mit dem Prädikat Reihenfolge `pred`. Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz, mit dem angegebenen Reihenfolge Prädikat erstellen.  
  
 Der Konstruktor:  
  
 `set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit der standardmäßigen Reihenfolge Prädikat. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit der standardmäßigen Reihenfolge Prädikat beschrieben.  
  
 Der Konstruktor:  
  
 `set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`, mit dem Prädikat Reihenfolge `pred`. Sie mit ihrer Hilfe der gesteuerten Sequenz eine Kopie einer anderen Sequenz, die durch ein Enumerator, mit dem angegebenen Reihenfolge Prädikat beschrieben.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cliext_set_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
// construct an empty container   
    Myset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myset c8(%c3);   
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
 c b a  
 a b c  
 c b a  
 a b c  
 c b a  
 c b a  
 a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Set::generic_container (STL/CLR)](../dotnet/set-generic-container-stl-clr.md)   
 [set::operator= (STL/CLR)](../dotnet/set-operator-assign-stl-clr.md)