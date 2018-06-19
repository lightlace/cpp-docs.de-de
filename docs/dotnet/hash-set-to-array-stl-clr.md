---
title: hash_set::to_array (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::to_array
dev_langs:
- C++
helpviewer_keywords:
- to_array member [STL/CLR]
ms.assetid: 2aa61f13-85b8-4aa4-91b4-69ddcc5064dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 540f4342dbff725a58b23c3c071c0f215dba1d7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127356"
---
# <a name="hashsettoarray-stlclr"></a>hash_set::to_array (STL/CLR)
Kopiert die gesteuerte Sequenz in ein neues Array.  
  
## <a name="syntax"></a>Syntax  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Array mit der kontrollierten Sequenz zurück. Sie können sie eine Kopie der gesteuerten Sequenz im Arrayform abrufen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_set_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)