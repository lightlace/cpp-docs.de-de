---
title: is_trivially_assignable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_trivially_assignable
dev_langs: C++
helpviewer_keywords: is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 888c57de7cf83dda35f5d0cc114abed30fbb2115
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable-Klasse
Testet, ob ein Wert des `From`-Typs einem `To`-Typ trivial zugewiesen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class To, class From>  
struct is_trivially_assignable;
```  
  
#### <a name="parameters"></a>Parameter  
 Aktion  
 Der Typ des Objekts, das die Zuweisung empfängt.  
  
 Von  
 Der Typ des Objekts, das den Wert bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein, und es muss für den Compiler bekannt sein, dass er keine nicht trivialen Vorgänge benötigt. Sowohl `From` als auch `To` müssen vollständige Typen `void` sein oder Arrays mit unbekannter Grenze.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



