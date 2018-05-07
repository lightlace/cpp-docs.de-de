---
title: 'hash_multiset:: End (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::end
dev_langs:
- C++
helpviewer_keywords:
- end member [STL/CLR]
ms.assetid: 6f4b222c-2f82-445e-80e5-6e2afd233d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ee532acbb163242477fcfd00c74f48651a9c759
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisetend-stlclr"></a>hash_multiset::end (STL/CLR)
Legt das Ende der kontrollierten Sequenz fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einem bidirektionalen Iterator, der direkt hinter das Ende der kontrollierten Sequenz verweist. Sie können damit einen Iterator abrufen, der das Ende der kontrollierten Sequenz bestimmt; der Status ist nicht nicht geändert werden, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_multiset_end.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
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
  
// inspect last two items   
    Myhash_multiset::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md)