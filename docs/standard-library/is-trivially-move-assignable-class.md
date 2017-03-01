---
title: is_trivially_move_assignable-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_move_assignable
- std.is_trivially_move_assignable
- std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
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
ms.openlocfilehash: b9d94304c6fbbd925ac3b670dc7665402b521dfd
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable-Klasse
Testet, ob der Typ einen trivialen Verschiebezuweisungsoperator aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_trivially_move_assignable;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ eine Klasse ist, die einen Verschiebungszuweisungsoperator aufweist; andernfalls „false“.  
  
 Ein Verschiebungszuweisungsoperator für eine `Ty`-Klasse ist in den folgenden Fällen trivial:  
  
 Er wird impliziert bereitgestellt  
  
 Die `Ty`-Klasse hat keine virtuellen Funktionen  
  
 Die `Ty`-Klasse hat keine virtuellen Basen  
  
 Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Verschiebungszuweisungsoperatoren  
  
 Die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Verschiebungszuweisungsoperatoren  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




