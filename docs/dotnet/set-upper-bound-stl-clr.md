---
title: 'Set:: upper_bound (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::set::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: 874d258a-990f-486f-ac7b-757a2f7c150a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da9f1ce48d77d3168dbfcb61d6ff23415d4f4c5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="setupperbound-stlclr"></a>set::upper_bound (STL/CLR)
Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion bestimmt das letzte Element `X` in der kontrollierten Sequenz, die Sortierung `key`. Wenn kein solches Element vorhanden ist, oder wenn `X` ist das letzte Element in der kontrollierten Sequenz gibt [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`; andernfalls wird einen Iterator, der das erste Element nach `X`. Sie können damit derzeit suchen das Ende einer Sequenz von Elementen in der kontrollierten Sequenz, die einen angegebenen Schlüssel entsprechen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_set_upper_bound.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
upper_bound(L'x')==end() = True  
*upper_bound(L'a') = b  
*upper_bound(L'b') = c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Set:: Count (STL/CLR)](../dotnet/set-count-stl-clr.md)   
 [Set:: equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)   
 [Set:: Find (STL/CLR)](../dotnet/set-find-stl-clr.md)   
 [set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)