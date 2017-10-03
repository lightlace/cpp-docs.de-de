---
title: is_nothrow_constructible-Klasse | Microsoft-Dokumentation
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
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 2ff20de3656cde44d79936c6bf1374134eb95068
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowconstructible-class"></a>Is_nothrow_constructible-Klasse
Testet, ob ein Typ konstruierbar ist, und nicht ausgelöst wird, wenn angegebene Argumenttypen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class... Args>  
struct is_nothrow_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
 `Args`  
 Die Argumenttypen, mit denen eine Übereinstimmung im Konstruktor von `T` gefunden werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` durch die Verwendung der Argumenttypen von `Args` konstruierbar ist, und wenn der Konstruktor nicht durch den Compiler ausgelöst wird; andernfalls ist sie FALSE. Typ `T` ist konstruierbar, wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist. Sowohl `T` als auch alle Typen in `Args` müssen vollständige Typen `void` sein oder Arrays mit unbekannter Grenze.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




