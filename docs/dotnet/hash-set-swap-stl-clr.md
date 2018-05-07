---
title: 'hash_set:: Swap (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_set::swap
dev_langs:
- C++
helpviewer_keywords:
- swap member [STL/CLR]
ms.assetid: 6476e48f-4744-486d-b028-cf0a048acd4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c95c924244fe090e0ccd0ea4cfcbb8a15337e979
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hashsetswap-stlclr"></a>hash_set::swap (STL/CLR)
Vertauscht den Inhalt von zwei Containern.  
  
## <a name="syntax"></a>Syntax  
  
```  
void swap(hash_set<Key>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Container für den Tausch von Inhalten.  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `this` und `right`aus. Dies erfolgt in konstanter Zeit, und es löst keine Ausnahmen. Sie verwenden es als eine schnelle Möglichkeit zum Austauschen von den Inhalt von zwei Containern.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_hash_set_swap.cpp   
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
  
// construct another container with repetition of values   
    Myhash_set c2;   
    c2.insert(L'd');   
    c2.insert(L'e');   
    c2.insert(L'f');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
d e f  
d e f  
a b c  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext Hash_set/>  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::operator= (STL/CLR)](../dotnet/hash-set-operator-assign-stl-clr.md)