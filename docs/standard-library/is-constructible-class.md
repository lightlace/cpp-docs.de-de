---
title: is_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
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
ms.openlocfilehash: b89f074cdb81024a847da3c7c77389e6a73f80d8
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="isconstructible-class"></a>is_constructible-Klasse
Testet, ob ein Typ konstruierbar ist, wenn die angegebenen Argumenttypen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, class... Args>  
struct is_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
 `Args`  
 Die Argumenttypen, mit denen eine Übereinstimmung im Konstruktor von `T` gefunden werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` durch die Verwendung der Argumenttypen von `Args` konstruierbar ist; andernfalls ist sie FALSE. Typ `T` ist konstruierbar, wenn die Variablendefinition `T t(std::declval<Args>()...);` wohlgeformt ist. Sowohl `T` als auch alle Typen in `Args` müssen vollständige Typen `void` sein oder Arrays mit unbekannter Grenze.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




