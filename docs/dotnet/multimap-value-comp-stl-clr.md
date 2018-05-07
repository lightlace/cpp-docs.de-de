---
title: 'multimap:: value_comp (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::value_comp
dev_langs:
- C++
helpviewer_keywords:
- value_comp member [STL/CLR]
ms.assetid: 4d142014-ab39-4da3-8aa9-ad0ab0cfddf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0ae463f60da8b797df19bc611b18523620a2ae04
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="multimapvaluecomp-stlclr"></a>multimap::value_comp (STL/CLR)
Der Delegat für zwei Elementwerte wird kopiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
value_compare^ value_comp();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt der Delegat zum Sortieren der kontrollierten Sequenz zurück. Sie können sie um zwei Elementwerte zu vergleichen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_multimap_value_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    Mymultimap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Mymultimap::make_value(L'a', 1),   
            Mymultimap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Mymultimap::make_value(L'a', 1),   
            Mymultimap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Mymultimap::make_value(L'b', 2),   
            Mymultimap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
compare([L'a', 1], [L'a', 1]) = False  
compare([L'a', 1], [L'b', 2]) = True  
compare([L'b', 2], [L'a', 1]) = False  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::value_compare (STL/CLR)](../dotnet/multimap-value-compare-stl-clr.md)   
 [multimap::value_type (STL/CLR)](../dotnet/multimap-value-type-stl-clr.md)