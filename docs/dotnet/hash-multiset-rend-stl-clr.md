---
title: 'hash_multiset:: rend (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::rend
dev_langs:
- C++
helpviewer_keywords:
- rend member [STL/CLR]
ms.assetid: 6d007ac9-18cc-4b51-8384-a4ff65d23e97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d75d8fc85a6a1cde37e8c9cf7edc93acd55a5c69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultisetrend-stlclr"></a>hash_multiset::rend (STL/CLR)
Legt das Ende der umgekehrten kontrollierten Sequenz fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
reverse_iterator rend();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einem reverse-Iterator, verweist direkt hinter dem Anfang der kontrollierten Sequenz zurück. Daher kennzeichnet es die `end` der umgekehrten Sequenz. Es mit der einen Iterator abrufen, bestimmt die `current` Ende der kontrollierten Sequenz in umgekehrter Reihenfolge, aber dessen Status kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_multiset_rend.cpp   
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
  
// inspect first two items   
    Myhash_multiset::reverse_iterator rit = c1.rend();   
    --rit;   
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);   
    System::Console::WriteLine("*--rend() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --rend() = b  
*--rend() = a  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: begin (STL/CLR)](../dotnet/hash-multiset-begin-stl-clr.md)   
 [hash_multiset:: End (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md)   
 [hash_multiset::rbegin (STL/CLR)](../dotnet/hash-multiset-rbegin-stl-clr.md)