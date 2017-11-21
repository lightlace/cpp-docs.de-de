---
title: extent-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::extent
dev_langs: C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 185cb6108801b31c19301a0f7488352a6948f5bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="extent-class"></a>extent-Klasse
Ruft eine Arraydimension ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty, unsigned I = 0>  
struct extent;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
 `I`  
 Das an die Abfrage gebundene Array.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `Ty` ein Arraytyp mit mindestens `I` Dimensionen ist, enthält die Abfrage die Anzahl der Elemente in der durch `I` angegebener Dimension. Wenn `Ty` nicht ein Arraytyp oder sein Rang kleiner als `I` ist, oder wenn `I` 0 und `Ty` vom Datentyp „Array mit unbekannter Grenze `U`“ ist, enthält die Abfrage den Wert 0.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
extent 0 == 5  
extent 1 == 10  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_all_extents Class (remove_all_extents-Klasse)](../standard-library/remove-all-extents-class.md)   
 [remove_extent Class (remove_extent-Klasse)](../standard-library/remove-extent-class.md)
