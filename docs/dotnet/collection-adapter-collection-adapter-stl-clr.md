---
title: collection_adapter::collection_adapter (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::collection_adapter
- cliext::collection_adapter::collection_adapter
dev_langs: C++
helpviewer_keywords: collection_adapter member [STL/CLR]
ms.assetid: 7e2bb75b-d735-4135-9523-719683e06fe9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b7f913ffb323bcfdb61d9d181f71297ec119e1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="collectionadaptercollectionadapter-stlclr"></a>collection_adapter::collection_adapter (STL/CLR)
Erstellt ein Adapterobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### <a name="parameters"></a>Parameter  
 Auflistung  
 BCL-Handle zu umschließen.  
  
 Rechts  
 Zu kopierende Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `collection_adapter();`  
  
 Initialisiert den gespeicherten Handle mit `nullptr`.  
  
 Der Konstruktor:  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 Initialisiert den gespeicherten Handle mit `right.` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Der Konstruktor:  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 Initialisiert den gespeicherten Handle mit `right->` [collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)`()`.  
  
 Der Konstruktor:  
  
 `collection_adapter(Coll^ collection);`  
  
 Initialisiert den gespeicherten Handle mit mit `collection`.  
  
## <a name="example"></a>Beispiel  
  
```  
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
base() null = True  
 x x x x x x  
 x x x x x x  
 x x x x x x  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Adapter >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::operator= (STL/CLR)](../dotnet/collection-adapter-operator-assign-stl-clr.md)