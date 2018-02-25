---
title: add_lvalue_reference-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26cbc7dc51fe6db51f47a8b60c6b209dfbc9a337
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="islvaluereference-class"></a>is_lvalue_reference-Klasse
Testet, ob es sich beim Typ um einen lvalue-Verweis handelt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_lvalue_reference;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz dieses Typprädikats ist TRUE, wenn der `Ty`-Typ ein Verweis auf ein Objekt oder eine Funktion ist; andernfalls FALSE. Beachten Sie, dass es sich beim `Ty`-Typ möglicherweise nicht um einen rvalue-Verweis handelt. Weitere Informationen zu Rvalues finden Sie unter [Rvalue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)



