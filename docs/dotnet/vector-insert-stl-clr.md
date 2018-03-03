---
title: 'Vector:: Insert (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::vector::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: f240cabf-f9d1-40c1-9cfb-975a90955546
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b330a9e0b8a11f41ceab4f604b73b93e8f1d735a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="vectorinsert-stlclr"></a>vector::insert (STL/CLR)
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
// cliext_vector_insert.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::vector<wchar_t> c2;   
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
 **Header:** \<Cliext/Vektor >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Vektor (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)