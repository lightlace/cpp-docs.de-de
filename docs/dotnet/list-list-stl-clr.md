---
title: 'List:: List (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::list
dev_langs:
- C++
helpviewer_keywords:
- list member [STL/CLR]
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cacfa4bb1d852a62d81d4496f19371072f2615f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="listlist-stlclr"></a>list::list (STL/CLR)
Erstellt ein container-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 `count`  
 Die Anzahl einzufügender Elemente.  
  
 `first`  
 Anfang des Bereichs, der eingefügt.  
  
 `last`  
 Das Ende des Bereichs einfügen.  
  
 `right`  
 Einzufügendes Objekt bzw. einzufügender Bereich.  
  
 `val`  
 Der Wert des einzufügenden Elements.  
  
## <a name="remarks"></a>Hinweise  
  
 Der Konstruktor:  
  
 `list();`  
  
 Initialisiert die gesteuerte Sequenz keine Elemente. Sie können damit Geben Sie eine leere gesteuerte Sequenz.  
  
 Der Konstruktor:  
  
 `list(list<Value>% right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right.begin()`, `right.end()`). Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch das Listenobjekt gesteuert wird `right`.  
  
 Der Konstruktor:  
  
 `list(list<Value>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`right->begin()`, `right->end()`). Sie können damit eine gesteuerte Sequenz angeben, die eine Kopie der Sequenz, die durch die List-Objekt, dessen Handle, gesteuert wird `right`.  
  
 Der Konstruktor:  
  
 `explicit list(size_type count);`  
  
 Initialisiert die gesteuerte Sequenz mit `count` jedes Elemente mit dem Wert `value_type()`. Sie verwenden es den Container mit Elementen gefüllt alle mit dem Standardwert.  
  
 Der Konstruktor:  
  
 `list(size_type count, value_type val);`  
  
 Initialisiert die gesteuerte Sequenz mit `count` jedes Elemente mit dem Wert `val`. Sie verwenden sie den Container mit Elementen gefüllt alle mit dem gleichen Wert.  
  
 Der Konstruktor:  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz [`first`, `last`). Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz erstellen.  
  
 Der Konstruktor:  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 Initialisiert die gesteuerte Sequenz durch die Sequenz, die vom Enumerator festgelegte `right`. Sie können damit der gesteuerten Sequenz eine Kopie einer anderen Sequenz beschrieben durch einen Enumerator erstellen.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0  
 x x x x x x  
 x x x x x  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [List::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator= (STL/CLR)](../dotnet/list-operator-assign-stl-clr.md)