---
title: 'List:: Erase (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::list::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 78705058-1e83-441d-b267-d4fb56451c0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 080cfbca2a69db9e277e080f5c34206b08e89c69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133687"
---
# <a name="listerase-stlclr"></a>list::erase (STL/CLR)
Entfernt Elemente an den angegebenen Positionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>Parameter  
 first  
 Anfang des Bereichs, der gelöscht.  
  
 last  
 Das Ende des Bereichs zu löschen.  
  
 wo  
 Element löschen.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion entfernt das Element der kontrollierten Sequenz verweist `where`. Es können Sie verwenden, um ein einzelnes Element zu entfernen.  
  
 Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich [`first`, `last`). Sie verwenden es, NULL oder mehr aufeinander folgende Elemente entfernt.  
  
 Beide Memberfunktionen geben einen Iterator, der das erste Element, das über alle Elemente entfernt wurden, oder [List:: End (STL/CLR)](../dotnet/list-end-stl-clr.md) `()` Wenn kein solches Element vorhanden ist.  
  
 Wenn Elemente zu löschen, ist die Anzahl von Elementkopien linear zur Anzahl von Elementen zwischen dem Ende des Löschens und näher am Ende der Sequenz. (Wenn ein oder mehrere Elemente an einem Ende der Sequenz zu löschen, erfolgen keine Elementkopien.)  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)