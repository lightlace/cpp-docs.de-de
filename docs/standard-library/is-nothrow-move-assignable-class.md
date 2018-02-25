---
title: is_nothrow_move_assignable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_move_assignable
ms.assetid: 000baa02-cbba-49de-9870-af730033348e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb1f16214dbfefb7f285f15eadf7975348531a23
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="isnothrowmoveassignable-class"></a>is_nothrow_move_assignable-Klasse
Testet, ob der Typ einen **nothrow**-Bewegungszuweisungsoperator aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_nothrow_move_assignable;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ einen nothrow-Verschiebungszuweisungsoperator aufweist; andernfalls „false“.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




