---
title: 'hash_set:: Clear (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 9f38b72a-5db8-485a-b41a-7d47ac57f4a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d1280dd73c5175f670003d8f06d520bcb0657eb9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127369"
---
# <a name="hashsetclear-stlclr"></a>hash_set::clear (STL/CLR)
Entfernt alle Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft tatsächlich [hash_set:: Erase (STL/CLR)](../dotnet/hash-set-erase-stl-clr.md) `(` [hash_set:: begin (STL/CLR)](../dotnet/hash-set-begin-stl-clr.md) `(),` [hash_set:: End (STL/CLR)](../dotnet/hash-set-end-stl-clr.md) `())`. Sie verwenden es, um sicherzustellen, dass die kontrollierte Sequenz leer ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_set_clear.cpp   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::erase (STL/CLR)](../dotnet/hash-set-erase-stl-clr.md)