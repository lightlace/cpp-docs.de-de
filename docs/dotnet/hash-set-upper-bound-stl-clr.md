---
title: 'hash_set:: upper_bound (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound member [STL/CLR]
ms.assetid: dc8815f1-8b45-4f3d-a51f-54050d434d8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6a5f496ccf82f4a0f0f9f770e3ddbfbf3af23672
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashsetupperbound-stlclr"></a>hash_set::upper_bound (STL/CLR)
Sucht nach Ende des Bereichs, die einem angegebenen Schlüssel entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion bestimmt das letzte Element `X` in der kontrollierten Sequenz, die mit dem gleichen Bucket als hashes `key` und Sortierung `key`. Wenn kein solches Element vorhanden ist, oder wenn `X` ist das letzte Element in der kontrollierten Sequenz gibt [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)`()`; andernfalls wird einen Iterator, der das erste Element nach zurückgegeben`X`. Sie können damit derzeit suchen das Ende einer Sequenz von Elementen in der kontrollierten Sequenz, die einen angegebenen Schlüssel entsprechen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_set_upper_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
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
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: Count (STL/CLR)](../dotnet/hash-set-count-stl-clr.md)   
 [hash_set:: equal_range (STL/CLR)](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash_set:: Find (STL/CLR)](../dotnet/hash-set-find-stl-clr.md)   
 [hash_set::lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)