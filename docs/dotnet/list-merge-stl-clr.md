---
title: 'List:: Merge (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::merge
dev_langs:
- C++
helpviewer_keywords:
- merge member [STL/CLR]
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0fdf7ee26bdb465e8a86109a4450353c4dc642a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="listmerge-stlclr"></a>list::merge (STL/CLR)
Verbindet zwei kontrollierte Sequenzen sortiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parameter  
 pred  
 Der Vergleich für Element-Paaren.  
  
 Rechts  
 Container in zusammengeführt.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt alle Elemente aus der Sequenz von gesteuert `right` und fügen Sie sie in der kontrollierten Sequenz. Beide Sequenzen müssen zuvor geordnet `operator<` --Elemente müssen nicht im Wert verringern, Seiten entweder Sequenz. Die resultierende Sequenz auch geordnet `operator<`. Verwenden Sie diese Memberfunktion zum Zusammenführen von zwei Sequenzen, die in den Wert in einer Sequenz zu erhöhen, die auch im Wert erhöht.  
  
 Die zweite Memberfunktion verhält sich wie die erste, mit dem Unterschied, dass die Sequenzen geordnet sind `pred`  --  `pred(X, Y)` muss "false" für ein bestimmtes Element `X` , die Element folgt `Y` in der Sequenz. Sie verwenden ihn zum Zusammenführen von zwei Sequenzen sortiert nach einer Prädikatfunktion oder der Delegat, den Sie angeben.  
  
 Sowohl Funktionen führt einen stabilen Mergevorgang – keine Elementpaare in entweder den ursprünglichen kontrollierten Sequenzen wird in der resultierenden gesteuerte Sequenz nicht rückgängig gemacht. Auch wenn ein Paar von Elementen `X` und `Y` in der resultierenden kontrollierten Sequenz verfügt über entsprechende Reihenfolge-- `!(X < Y) && !(X < Y)` – ein Element aus die ursprüngliche gesteuerte Sequenz wird vor einem Element aus der Sequenz von gesteuert`right`.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a c e  
 b d f  
 a b c d e f  
c2.size() = 0  
 e c a  
 f e d c b a  
 f e e d c c b a a  
c1.size() = 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)   
 [list::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)