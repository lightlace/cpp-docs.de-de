---
title: 'List:: rbegin (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::rbegin
dev_langs: C++
helpviewer_keywords: rbegin member [STL/CLR]
ms.assetid: 99637376-8ac3-4e39-844a-b4f324a7c6ba
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a826f4dc891a24a6e0e45c1a03de3e1fd77cafd4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="listrbegin-stlclr"></a>list::rbegin (STL/CLR)
Legt den Anfang der umgekehrten kontrollierten Sequenz fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen umgekehrten Iterator, der das letzte Element der kontrollierten Sequenz oder nur vor dem Anfang einer leeren Sequenz zurück. Daher kennzeichnet es die `beginning` der umgekehrten Sequenz. Es mit der einen Iterator abrufen, bestimmt die `current` Anfang der kontrollierten Sequenz in umgekehrter Reihenfolge kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_list_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
  
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
*rbegin() = c  
*++rbegin() = b  
 a y x  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/List >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [List:: begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)   
 [List:: End (STL/CLR)](../dotnet/list-end-stl-clr.md)   
 [list::rend (STL/CLR)](../dotnet/list-rend-stl-clr.md)