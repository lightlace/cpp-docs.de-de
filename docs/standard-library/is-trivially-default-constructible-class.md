---
title: is_trivially_default_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 9ad38fb23b5ac205a283969ea50041c1bfba2806
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible-Klasse
Testet, ob der Typ einen trivialen Standardkonstruktor aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_trivially_default_constructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty` Typ eine Klasse ist, die einen trivialen Konstruktor aufweist; andernfalls „false“.  
  
 Einen Standardkonstruktor für eine Klasse `Ty` ist trivial, wenn:  
  
-   es ist eine implizit deklarierte Standardkonstruktor  
  
-   die Klasse `Ty` hat keine virtuellen Funktionen  
  
-   die Klasse `Ty` hat keine virtuellen Basen  
  
-   alle direkten Basisklassen der Klasse `Ty` weisen triviale Konstruktoren auf  
  
-   die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Konstruktoren  
  
-   die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Konstruktoren  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




