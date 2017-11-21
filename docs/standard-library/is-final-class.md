---
title: is_final-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_final
dev_langs: C++
helpviewer_keywords: is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9f1ab7e0eb9a49e1ed73c2bc33d78b480f8ef907
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="isfinal-class"></a>is_final-Klasse
Testet, ob der Typ ein als `final` markierter Klassentyp ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
struct is_final;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` ein als `final` markierter Klassentyp ist; andernfalls ist sie FALSE. Wenn `T` ein Klassentyp ist, muss es ein vollständiger Typ sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [final-Bezeichner](../cpp/final-specifier.md)



