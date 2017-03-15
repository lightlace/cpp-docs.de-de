---
title: is_literal_type-Klasse | Microsoft-Dokumentation
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
- is_literal_type
- std.is_literal_type
- std::is_literal_type
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 5a89b32e85cc7756f4d420f8eea55b2088a44320
ms.lasthandoff: 02/24/2017

---
# <a name="isliteraltype-class"></a>is_literal_type-Klasse
Testet, ob ein Typ als eine `constexpr`-Variable verwendet werden kann, oder von `constexpr`-Funktionen erstellt, verwendet oder zurückgegeben werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
struct is_literal_type;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` ein *Literaltyp* ist; andernfalls ist sie FALSE. Ein Literaltyp ist entweder `void`, ein skalarer Typ, ein Verweistyp, ein Array von Literaltypen oder ein Literalklassentyp. Ein Literalklassentyp ist ein Klassentyp, der einen trivialen Destruktor aufweist, entweder ein aggregierter Typ ist oder mindestens über einen non-move, non-copy `constexpr`-Konstruktor verfügt. Alle seine Basisklassen und nichtstatischen Datenmember sind nicht volatile Literaltypen. Während der Typ eines Literals immer ein literal-Typ ist, enthält das Konzept eines literal-Typ alles, was der Compiler zur Kompilierzeit als ein `constexpr` auswerten kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




