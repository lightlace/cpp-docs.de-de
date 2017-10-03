---
title: is_move_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
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
ms.openlocfilehash: 9498029f431b287312583f78effc5197fc097fd6
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ismoveconstructible-class"></a>is_move_constructible-Klasse
Testet, ob der Typ einen Bewegungskonstruktor aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
struct is_move_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 T  
 Der auszuwertende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Ein Typprädikat, das TRUE ausgewertet wird, wenn der Typ `T` mithilfe eines Verschiebevorgangs konstruiert werden kann. Das Prädikat entspricht `is_constructible<T, T&&>`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




