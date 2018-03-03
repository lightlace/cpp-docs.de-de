---
title: 'hash_set:: Size (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_set::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: e006590e-8710-4294-b3a3-dcded0668a24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 761bbc7c67fa7cbe832aa4ef5de22d44fce0f3ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hashsetsize-stlclr"></a>hash_set::size (STL/CLR)
Ermittelt die Anzahl von Elementen.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Länge der gesteuerten Sequenz zurück. Sie können erkennen, die Anzahl der Elemente, die derzeit in der kontrollierten Sequenz. Wenn Sie von Interesse ist, ob die Sequenz ungleich Größe finden Sie unter hat, [hash_set:: Empty (STL/CLR)](../dotnet/hash-set-empty-stl-clr.md)`()`.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_set_size.cpp   
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
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 0 after clearing  
size() = 2 after adding 2  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::empty (STL/CLR)](../dotnet/hash-set-empty-stl-clr.md)