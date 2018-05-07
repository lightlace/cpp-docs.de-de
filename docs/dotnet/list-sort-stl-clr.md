---
title: 'List:: Sort (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::sort
dev_langs:
- C++
helpviewer_keywords:
- sort member [STL/CLR]
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 670b18e5901ef264474256a1a1e57cde7a28ef01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="listsort-stlclr"></a>list::sort (STL/CLR)
Sortiert die gesteuerte Sequenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parameter  
 pred  
 Der Vergleich für Element-Paaren.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion ordnet die Elemente in der kontrollierten Sequenz, damit sie geordnet sind `operator<` --Elemente werden nicht im Wert verringern, Seiten der Sequenz. Sie verwenden diese Memberfunktion auf, um die Sequenz in aufsteigender Reihenfolge zu sortieren.  
  
 Die zweite Memberfunktion verhält sich wie die erste, mit dem Unterschied, dass die Reihenfolge nach sortiert ist `pred`  --  `pred(X, Y)` lautet "false" für ein bestimmtes Element `X` , die Element folgt `Y` in der resultierenden Sequenz. Sie können damit um die Sequenz in einer Reihenfolge zu sortieren, die Sie, indem Sie eine Prädikatfunktion oder der Delegat angeben.  
  
 Sowohl Funktionen führen eine stabile Sortierung – keine Elementpaare in die ursprüngliche gesteuerte Sequenz wird in der resultierenden gesteuerte Sequenz nicht rückgängig gemacht.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_sort.cpp   
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
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
c b a  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)   
 [List:: Reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)   
 [List:: splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)   
 [list::unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)