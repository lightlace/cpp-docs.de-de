---
title: 'List:: splice (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::splice
dev_langs:
- C++
helpviewer_keywords:
- splice member [STL/CLR]
ms.assetid: ebc424b9-8341-4a88-b101-86d56324f5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e0c92faf6a4ec84e6ed65c58d02337038398d37e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135949"
---
# <a name="listsplice-stlclr"></a>list::splice (STL/CLR)
Restitch Links zwischen Knoten.  
  
## <a name="syntax"></a>Syntax  
  
```  
void splice(iterator where, list<Value>% right);  
void splice(iterator where, list<Value>% right,  
    iterator first);  
void splice(iterator where, list<Value>% right,  
    iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Der Anfang des Bereichs, die zusammengeführt werden sollen.  
  
 last  
 Das Ende des Bereichs, die zusammengeführt werden sollen.  
  
 Rechts  
 Container für die Zusammenführung.  
  
 wo  
 Die Position, im Container für die Zusammenführung vor.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion fügt die Sequenz, die vom gesteuerte `right` vor dem Element in der kontrollierten Sequenz verweist `where`. Es entfernt auch alle Elemente aus `right`. (`%right` dürfen nicht gleich sein `this`.) Sie können damit alle einer Liste in eine andere zusammengeführt werden sollen.  
  
 Die zweite Memberfunktion entfernt das Element verweist `first` in der Sequenz von gesteuert `right` und fügt das Element vor das Element in der kontrollierten Sequenz auf verweist `where`. (Wenn `where` `==` `first` `||` `where` `== ++first`, findet keine Änderung statt.) Damit können sie ein einzelnes Element einer Liste in eine andere zusammengeführt werden sollen.  
  
 Die dritte Memberfunktion fügt die durch festgelegten Unterbereich [`first`, `last`) aus der Sequenz von gesteuert `right` vor dem Element in der kontrollierten Sequenz verweist `where`. Es entfernt auch den Original-Unterbereich aus der durch `right` gespeicherten Sequenz. (If `right` `==` `this`, Bereich [`first`, `last`) das Element verweist, darf keine enthalten `where`.) Sie können damit eine teilsequenz von NULL oder mehr Elemente aus einer Liste in eine andere zusammengeführt werden sollen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_splice.cpp   
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
  
// splice to a new list   
    cliext::list<wchar_t> c2;   
    c2.splice(c2.begin(), c1);   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return one element   
    c1.splice(c1.end(), c2, c2.begin());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// return remaining elements   
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
c1.size() = 0  
 a b c  
 a  
 b c  
 b c a  
c2.size() = 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)   
 [List:: Insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)   
 [list::merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)