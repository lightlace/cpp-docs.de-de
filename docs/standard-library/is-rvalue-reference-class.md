---
title: is_rvalue_reference-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_rvalue_reference
dev_langs: C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 673ca6b633a18879bb9f23c29e9fc14c0d273978
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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



