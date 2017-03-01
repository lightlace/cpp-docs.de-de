---
title: is_trivially_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- is_trivially_constructible
- std.is_trivially_constructible
- std::is_trivially_constructible
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4acc8f686d918391966949134a5c2b3c1a0a41a5
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallyconstructible-class"></a>Is_trivially_constructible-Klasse
Testet, ob ein Typ trivial konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class... Args>  
struct is_trivially_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
 `Args`  
 Die Argumenttypen, mit denen eine Übereinstimmung im Konstruktor von `T` gefunden werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` durch die Verwendung der Argumenttypen von `Args` trivial konstruierbar ist; andernfalls ist sie FALSE. Typ `T` ist trivial konstruierbar, wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist, und keine nicht trivialen Operationen aufruft. Sowohl `T` als auch alle Typen in `Args` müssen vollständige Typen `void` sein oder Arrays mit unbekannter Grenze.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




