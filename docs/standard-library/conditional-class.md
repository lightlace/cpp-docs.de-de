---
title: conditional-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c0c6deb6a7167852101efba30a978aee78f96f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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



