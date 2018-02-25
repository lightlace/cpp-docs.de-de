---
title: is_rvalue_reference-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 950f36fc4240e76d464bfcd1eaff4bb46783311c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference-Klasse
Testet, ob es sich beim Typ um einen „rvalue“-Verweis handelt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct is_rvalue_reference;
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz dieses Typprädikats ist TRUE, wenn der Typ `Ty` ein [rvalue-Verweis](../cpp/rvalue-reference-declarator-amp-amp.md) ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)



