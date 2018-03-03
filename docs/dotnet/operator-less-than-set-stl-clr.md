---
title: Operator&lt; (Set) (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::set::operator<
dev_langs:
- C++
helpviewer_keywords:
- operator< member [STL/CLR]
ms.assetid: bd6b351d-3f33-4f66-97fa-b7e8f36ce9fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5ba01bbe0660286a54b0bc685a9dc85bdcd3e7b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="operatorlt-set-stlclr"></a>Operator&lt; (Set) (STL/CLR)
Liste kleiner als Vergleich.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Key>  
    bool operator<(set<Key>% left,  
        set<Key>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
## <a name="remarks"></a>Hinweise  
 Der Operator-Funktion gibt "true" zurück, wenn, für die niedrigste Position `i` für die `!(right[i] < left[i])` es ist auch, die "true" `left[i] < right[i]`. Andernfalls wird zurückgegeben `left->size() < right->size()` Sie zum Testen verwenden, ob `left` sortiert ist, bevor Sie `right` bei die beiden Sätzen verglichenen elementweise sind.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_set_operator_lt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] < [a b c] is False  
[a b c] < [a b d] is True  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Set >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Legen Sie (STL/CLR)](../dotnet/set-stl-clr.md)   
 [Operator == (Set) (STL/CLR)](../dotnet/operator-equality-set-stl-clr.md)   
 [Operator! = (Set) (STL/CLR)](../dotnet/operator-inequality-set-stl-clr.md)   
 [Operator > = (Set) (STL/CLR)](../dotnet/operator-greater-or-equal-set-stl-clr.md)   
 [Operator > (Set) (STL/CLR)](../dotnet/operator-greater-than-set-stl-clr.md)   
 [operator<= (set) (STL/CLR)](../dotnet/operator-less-or-equal-set-stl-clr.md)