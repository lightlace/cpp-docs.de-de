---
title: is_trivially_default_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_default_constructible
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: dd41fbdcc33250bc60a0b919b17dd52862549a77
ms.lasthandoff: 02/24/2017

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




