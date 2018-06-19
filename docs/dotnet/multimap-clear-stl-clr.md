---
title: 'multimap:: Clear (STL/CLR) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multimap::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 2c4aae4b-0aac-42ba-abf4-eaf2d5734817
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b177134cedc14cbd384308449f98134db81073ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136746"
---
# <a name="multimapclear-stlclr"></a>multimap::clear (STL/CLR)
Entfernt alle Elemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft tatsächlich [multimap:: Erase (STL/CLR)](../dotnet/multimap-erase-stl-clr.md) `(` [multimap:: begin (STL/CLR)](../dotnet/multimap-begin-stl-clr.md) `(),` [multimap:: End (STL/CLR)](../dotnet/multimap-end-stl-clr.md) `())`. Sie verwenden es, um sicherzustellen, dass die kontrollierte Sequenz leer ist.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_multimap_clear.cpp   
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
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
  
// display contents " [a 1] [b 2]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0  
 [a 1] [b 2]  
size() = 0  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext/Map >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::erase (STL/CLR)](../dotnet/multimap-erase-stl-clr.md)