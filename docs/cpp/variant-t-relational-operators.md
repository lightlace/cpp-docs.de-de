---
title: _variant_t-Operatoren (relational) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
- _variant_t::operator!=
- _variant_t::operator==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- relational operators, _variant_t class
- operator!=, variant
- operator!=, relational operators
- operator !=, variant
- operator ==, variant
- operator==, variant
- operator !=, relational operators
- == operator, with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d8bcf9550e3e3f8af1836aa3f6e8747089837142
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="variantt-relational-operators"></a>_variant_t-Operatoren (relational)
**Microsoft-spezifisch**  
  
 Überprüft zwei `_variant_t`-Objekte auf Gleichheit bzw. Ungleichheit.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 *varSrc*  
 Ein **VARIANT** mit verglichen werden soll die `_variant_t` Objekt.  
  
 `pSrc`  
 Zeiger auf die **VARIANT** mit verglichen werden soll die `_variant_t` Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** enthielte Vergleich **"false"** Wenn dies nicht.  
  
## <a name="remarks"></a>Hinweise  
 Vergleicht eine `_variant_t` -Objekt mit einem **VARIANT**, testet auf Gleichheit oder Ungleichheit.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)
