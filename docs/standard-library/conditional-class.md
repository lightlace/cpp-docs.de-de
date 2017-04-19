---
title: conditional-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- conditional
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
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
ms.openlocfilehash: b7e187e8ddbb4a9457b5fe9eddda152464d7518d
ms.lasthandoff: 02/24/2017

---
# <a name="conditional-class"></a>conditional-Klasse
Wählt einen von zwei Typen, abhängig von der angegebenen Bedingung.  
  
## <a name="syntax"></a>Syntax  
  
```
template <bool B, class T1, class T2>  
struct conditional;

template <bool _Test, class _T1, class _T2>  
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```  
  
#### <a name="parameters"></a>Parameter  
 `B`  
 Der Wert, der den ausgewählten Typ bestimmt.  
  
 `T1`  
 Das Typergebnis, wenn B „true“ ist.  
  
 `T2`  
 Das Typergebnis, wenn B „false“ ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenmember-Typdefinition (typedef) `conditional<B, T1, T2>::type` wird mit `T1` ausgewertet, wenn `B` mit `true`ausgewertet wird, und wird mit `T2` ausgewertet, wenn `B` mit `false`ausgewertet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




