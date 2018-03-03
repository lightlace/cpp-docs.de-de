---
title: 'multiset:: Insert (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multiset::insert
dev_langs:
- C++
helpviewer_keywords:
- insert member [STL/CLR]
ms.assetid: 7a3b1cc8-ec60-4ed0-ace5-46cb5872e6e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6d66f1136a9e9939b0297f1b909c21981e4718d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="multisetinsert-stlclr"></a>multiset::insert (STL/CLR)
Fügt Elemente hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Anfang des Bereichs, der eingefügt.  
  
 last  
 Das Ende des Bereichs einfügen.  
  
 Rechts  
 Die Enumeration eingefügt.  
  
 Val  
 Schlüssel-Wert einfügen.  
  
 wo  
 Die Position, im Container (nur Hinweis) einfügen.  
  
## <a name="remarks"></a>Hinweise  
 Jede der Memberfunktionen Fügt eine Sequenz, die von den verbleibenden Operanden angegeben.  
  
 Die erste Memberfunktion Fügt ein Element mit dem Wert `val`, und gibt einen Iterator, der das neu eingefügte Element festlegt. Es können Sie verwenden, um ein einzelnes Element einzufügen.  
  
 Die zweite Memberfunktion Fügt ein Element mit dem Wert `val`mit `where` als Hinweis (zur Verbesserung der Leistung), und gibt einen Iterator, der das neu eingefügte Element festlegt. Damit können sie ein einzelnes Element einfügen, das neben einem Element möglicherweise, die Sie kennen.  
  
 Die dritte Memberfunktion fügt die Sequenz [`first`, `last`). Sie verwenden ihn zum Einfügen von NULL oder mehr Elementen aus einer anderen Sequenz kopiert.  
  
 Die vierte Memberfunktion fügt die Sequenz, die vom angegebenen der `right`. Sie verwenden es, fügen Sie eine Sequenz, die durch einen Enumerator beschrieben.  
  
 Jede elementeinfügung dauert einige Zeit, die proportional zum Logarithmus der Anzahl der Elemente in der kontrollierten Sequenz. Kann in amortisierter konstanter Zeit, jedoch die Einfügung erhält einen Hinweis, der ein Element, das neben der Einfügemarke festlegt.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_multiset_insert.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    System::Console::WriteLine("insert(L'x') = {0}",   
        *c1.insert(L'x'));   
  
    System::Console::WriteLine("insert(L'b') = {0}",   
        *c1.insert(L'b'));   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymultiset c2;   
    Mymultiset::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymultiset c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(L'x') = x  
insert(L'b') = b  
 a b b c x  
insert(begin(), L'y') = y  
 a b b c x y  
 a b b c x  
 a b b c x y  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)