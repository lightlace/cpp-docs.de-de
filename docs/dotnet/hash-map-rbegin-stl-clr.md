---
title: 'hash_map:: rbegin (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: e3b6c4d5-9482-471e-b5fc-70331b082a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4bec2f5ac33fcbb0f68ae799443a92b0d69695ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashmaprbegin-stlclr"></a>hash_map::rbegin (STL/CLR)
Legt den Anfang der umgekehrten kontrollierten Sequenz fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt einen umgekehrten Iterator, der das letzte Element der kontrollierten Sequenz oder nur vor dem Anfang einer leeren Sequenz zurück. Daher kennzeichnet es die `beginning` der umgekehrten Sequenz. Es mit der einen Iterator abrufen, bestimmt die `current` Anfang der kontrollierten Sequenz in umgekehrter Reihenfolge kann ändern, wenn die Länge der gesteuerten Sequenz geändert wird.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_map_rbegin.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_map::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*++rbegin() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*rbegin() = [c 3]  
*++rbegin() = [b 2]  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_map/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_map-Element (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map:: begin (STL/CLR)](../dotnet/hash-map-begin-stl-clr.md)   
 [hash_map:: End (STL/CLR)](../dotnet/hash-map-end-stl-clr.md)   
 [hash_map::rend (STL/CLR)](../dotnet/hash-map-rend-stl-clr.md)