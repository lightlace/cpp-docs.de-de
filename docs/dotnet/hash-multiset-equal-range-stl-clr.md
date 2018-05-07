---
title: 'hash_multiset:: equal_range (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range member [STL/CLR]
ms.assetid: a4141d7e-4964-4c78-8989-ae1d1258b50a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8eaacdf74fb9906dd6fc9b88878c4814185bc341
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisetequalrange-stlclr"></a>hash_multiset::equal_range (STL/CLR)
Sucht den Bereich, der einem angegebenen Schlüssel entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Paar von Iteratoren `cliext::pair<iterator, iterator>(` [hash_multiset:: lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md) `(key),` [hash_multiset:: upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)`(key))`. Sie können damit um des Bereichs von Elementen, die derzeit in der gesteuerten Sequenz zu ermitteln, die einen angegebenen Schlüssel entsprechen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_multiset_equal_range.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
typedef Myhash_multiset::pair_iter_iter Pairii;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: Count (STL/CLR)](../dotnet/hash-multiset-count-stl-clr.md)   
 [hash_multiset:: Find (STL/CLR)](../dotnet/hash-multiset-find-stl-clr.md)   
 [hash_multiset:: lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)   
 [hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)