---
title: Operator! = (Multimap) (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::operator!=
dev_langs: C++
helpviewer_keywords: operator!= member [STL/CLR]
ms.assetid: bc98c310-4528-4285-8182-23a055b7732e
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a93061a21aba89b96c4d27dee2a0aa9693ef8ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="operator-multimap-stlclr"></a>operator!= (multimap) (STL/CLR)
Liste nicht gleich sein Vergleich aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator!=(multimap<Key, Mapped>% left,  
        multimap<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linker zu vergleichender Container.  
  
 Rechts  
 Rechter zu vergleichender Container.  
  
## <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left == right)`. Sie zum Testen verwenden, ob `left` nicht sortiert wird, ist identisch mit `right` Wenn den zwei multimap-Objekte aus verglichenen elementweise sind.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_multimap_operator_ne.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'a', 1));   
    c2.insert(Mymultimap::make_value(L'b', 2));   
    c2.insert(Mymultimap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [d 4]  
[a b c] != [a b c] is False  
[a b c] != [a b d] is True  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [Operator == (Multimap) (STL/CLR)](../dotnet/operator-equality-multimap-stl-clr.md)   
 [Operator\< (Multimap) (STL/CLR)](../dotnet/operator-less-than-multimap-stl-clr.md)   
 [Operator > = (Multimap) (STL/CLR)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)   
 [Operator > (Multimap) (STL/CLR)](../dotnet/operator-greater-than-multimap-stl-clr.md)   
 [operator<= (multimap) (STL/CLR)](../dotnet/operator-less-or-equal-multimap-stl-clr.md)