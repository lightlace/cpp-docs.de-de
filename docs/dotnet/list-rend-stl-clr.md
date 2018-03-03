---
title: 'List:: rend (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: b51030ad-1bca-42b0-b890-db47111d2921
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c69549fe4524b15f1fcac53d8a418ff346f3afb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="listrend-stlclr"></a>list::rend (STL/CLR)
Legt das Ende der umgekehrten kontrollierten Sequenz fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einem reverse-Iterator, verweist direkt hinter dem Anfang der kontrollierten Sequenz zurück. Daher kennzeichnet es die `end` der umgekehrten Sequenz. Es mit der einen Iterator abrufen, bestimmt die `current` Ende der kontrollierten Sequenz in umgekehrter Reihenfolge, aber dessen Status kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_rend.cpp   
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
  
// inspect first two items   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
  
// alter first two items and reinspect   
    *--rit = L'x';   
    *++rit = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
 y x c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)   
 [List:: End (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)