---
title: 'Set:: Find (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::find
dev_langs: C++
helpviewer_keywords: find member [STL/CLR]
ms.assetid: 916e581c-2815-4c07-a51a-6c5ddfa730c1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82296d6da1a2b995026d75a2e2973335cd00ef5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setfind-stlclr"></a>set::find (STL/CLR)
Sucht ein Element, das einem angegebenen Schlüssel entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Verfügt über mindestens ein Element in der kontrollierten Sequenz entsprechende Sortierung mit `key`, die Memberfunktion gibt einen Iterator Festlegen eines dieser Elemente zurück, andernfalls es [Set:: End (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`. Damit können sie ein Element aktuell in der kontrollierten Sequenz gesucht werden soll, die einem angegebenen Schlüssel entspricht.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_set_find.cpp   
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
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
find A = False  
find b = b  
find C = False  
```  
  
## <a name="description"></a>Beschreibung  
 Beachten Sie, dass `find` garantiert nicht die mehrere gefundenen Elements.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Set:: equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)   
 [Set:: lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)   
 [set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)