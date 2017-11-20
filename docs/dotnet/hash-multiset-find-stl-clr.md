---
title: 'hash_multiset:: Find (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::find
dev_langs: C++
helpviewer_keywords: find member [STL/CLR]
ms.assetid: fbedeb37-242e-4c2a-b1f8-234bcfd9cd25
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d36ec741b4350ed37ea666482cd49cb95bc25dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultisetfind-stlclr"></a>hash_multiset::find (STL/CLR)
Sucht ein Element, das einem angegebenen Schlüssel entspricht.  
  
## <a name="syntax"></a>Syntax  
  
```  
iterator find(key_type key);  
```  
  
#### <a name="parameters"></a>Parameter  
 Key  
 Der zu suchende Schlüsselwert.  
  
## <a name="remarks"></a>Hinweise  
 Verfügt über mindestens ein Element in der kontrollierten Sequenz entsprechende Sortierung mit `key`, die Memberfunktion gibt einen Iterator Festlegen eines dieser Elemente zurück, andernfalls es [hash_multiset:: End (STL/CLR)](../dotnet/hash-multiset-end-stl-clr.md) `()`. Damit können sie ein Element aktuell in der kontrollierten Sequenz gesucht werden soll, die einem angegebenen Schlüssel entspricht.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_multiset_find.cpp   
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
 [hash_multiset-Element (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: equal_range (STL/CLR)](../dotnet/hash-multiset-equal-range-stl-clr.md)   
 [hash_multiset:: lower_bound (STL/CLR)](../dotnet/hash-multiset-lower-bound-stl-clr.md)   
 [hash_multiset::upper_bound (STL/CLR)](../dotnet/hash-multiset-upper-bound-stl-clr.md)