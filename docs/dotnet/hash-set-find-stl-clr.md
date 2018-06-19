---
title: 'hash_set:: Find (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::find
dev_langs:
- C++
helpviewer_keywords:
- find member [STL/CLR]
ms.assetid: 758b7438-ef15-4af0-8001-a1126d5e9a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 63a8be1bc59d6c2b9cc2128295a9e39dea14cf84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33126912"
---
# <a name="hashsetfind-stlclr"></a>hash_set::find (STL/CLR)
Sucht ein Element, das einem angegebenen Schlüssel entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Verfügt über mindestens ein Element in der kontrollierten Sequenz entsprechende Sortierung mit `key`, die Memberfunktion gibt einen Iterator Festlegen eines dieser Elemente zurück, andernfalls es [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md) `()`. Damit können sie ein Element aktuell in der kontrollierten Sequenz gesucht werden soll, die einem angegebenen Schlüssel entspricht.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_set_find.cpp   
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
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set:: equal_range (STL/CLR)](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash_set:: lower_bound (STL/CLR)](../dotnet/hash-set-lower-bound-stl-clr.md)   
 [hash_set::upper_bound (STL/CLR)](../dotnet/hash-set-upper-bound-stl-clr.md)