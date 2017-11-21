---
title: 'List:: Insert (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::insert
dev_langs: C++
helpviewer_keywords: insert member [STL/CLR]
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2a0fd1aad6b32de4f9232cbb7f7874255d1ecba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="listinsert-stlclr"></a>list::insert (STL/CLR)
Fügt Elemente an einer angegebenen Position hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 count  
 Die Anzahl einzufügender Elemente.  
  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Die Enumeration eingefügt.  
  
 Val  
 Der Wert des einzufügenden Elements.  
  
 wo  
 Die Position, im Container vor dem Einfügen.  
  
## <a name="remarks"></a>Hinweise  
 Jede der memberfunktionseinfügungen, vor dem Element verweist `where` in der gesteuerten Sequenz eine Sequenz von den verbleibenden Operanden angegeben.  
  
 Die erste Memberfunktion Fügt ein Element mit dem Wert `val` und gibt einen Iterator, der das neu eingefügte Element festlegt. Sie verwenden es um ein einzelnes Element vor einem Ort, ein Iterator bezeichnete einzufügen.  
  
 Die zweite Memberfunktion fügt eine Wiederholung der `count`-Elemente des Werts `val` ein. Sie verwenden ihn zum Einfügen von NULL oder mehr aufeinander folgende Elementen sind alle Kopien den gleichen Wert.  
  
 Wenn `InIt` ein Ganzzahltyp ist, verhält sich die dritte Memberfunktion genau wie `insert(where, (size_type)first, (value_type)last)`. Andernfalls fügt die Sequenz [`first`, `last`). Sie verwenden ihn zum Einfügen von NULL oder mehr zusammenhängender Elementen, die aus einer anderen Sequenz kopiert.  
  
 Die vierte Memberfunktion fügt die Sequenz, die vom angegebenen der `right`. Sie verwenden es, fügen Sie eine Sequenz, die durch einen Enumerator beschrieben.  
  
 Wenn Sie ein einzelnes Element einfügen, ist die Anzahl von Elementkopien linear zur Anzahl der Elemente zwischen der Einfügemarke und näher am Ende der Sequenz. (Wenn ein oder mehrere Elemente an einem Ende der Sequenz eingefügt wurden, erfolgen keine Elementkopien.) Wenn `InIt` ein input-Iterator, ist die dritte Memberfunktion führt eine einzelne Einfügung effektiv für jedes Element in der Sequenz. Andernfalls, beim Einfügen von `N` Elemente, die die Anzahl der Elementkopien ist linear `N` plus die Anzahl der Elemente zwischen der Einfügemarke und näher am Ende der Sequenz.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_insert.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)