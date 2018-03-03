---
title: multimap::Operator = (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multimap::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: 9bef7dc5-591d-443b-88b1-e68286422fe6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8e80266953adcda93039fd0ad8a993890946b25f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="multimapoperator-stlclr"></a>multimap::operator= (STL/CLR)
Ersetzt die kontrollierte Sequenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
multimap<Key, Mapped>% operator=(multimap<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Der zu kopierende Container.  
  
## <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien `right` klicken Sie dann auf das Objekt gibt `*this`. Sie können ihn verwenden, um die kontrollierte Sequenz durch eine Kopie der kontrollierten Sequenz in `right` zu ersetzen.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_multimap_operator_as.cpp   
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
    c2 = c1;   
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)