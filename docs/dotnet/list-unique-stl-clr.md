---
title: 'List:: Unique (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::unique
dev_langs:
- C++
helpviewer_keywords:
- unique member [STL/CLR]
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 056f15dc0e7808a7f0ada7267a60e13d4c75d83b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="listunique-stlclr"></a>list::unique (STL/CLR)
Entfernt benachbarte Elemente, die einen angegebenen Test bestehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### <a name="parameters"></a>Parameter  
 pred  
 Der Vergleich für Element-Paaren.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt wird, aus der kontrollierten Sequenz (löscht) jedes Element, das verglichen mit dem vorherigen Element--gleich, wenn Element `X` vorausgeht Element `Y` und `X == Y`, die Memberfunktion entfernt `Y`. Sie können damit alle bis auf eine Kopie jeder Untersequenz der benachbarten Elemente entfernen, Vergleich auf Gleichheit. Beachten Sie, dass bei die kontrollierte Sequenz sortiert wurde, z. B. wie durch den Aufruf [List:: Sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)`()`, die Memberfunktion lässt nur Elemente mit eindeutigen Werten. (Sie beenden – englisch: to terminate – die Abfrage, daher der Name.)  
  
 Die zweite Memberfunktion verhält sich wie die erste, mit dem Unterschied, dass jedes Element entfernt `Y` nach einem Element `X` für die `pred(X, Y)`. Sie können damit alle bis auf eine Kopie jeder Untersequenz der benachbarten Elemente entfernen, die erfüllt eine Prädikatfunktion oder Delegaten, die Sie angeben. Beachten Sie, dass bei die kontrollierte Sequenz sortiert wurde, z. B. wie durch den Aufruf `sort(pred)`, die Member-Funktion bewirkt, dass nur Elemente, die keine entsprechende Sortierung mit anderen Elemente.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a a b c  
a b c  
a a  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: Remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)   
 [List:: remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)