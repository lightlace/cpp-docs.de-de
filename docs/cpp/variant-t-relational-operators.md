---
title: _variant_t-Operatoren (relational) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32f9a45fcfaaff02cfb7cf765857957f20c41ba1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463040"
---
# <a name="variantt-relational-operators"></a>_variant_t-Operatoren (relational)
**Microsoft-spezifisch**  
  
 Überprüft zwei `_variant_t`-Objekte auf Gleichheit bzw. Ungleichheit.  
  
## <a name="syntax"></a>Syntax  
  
```  
bool operator==(  
   const VARIANT& varSrc) const;  
bool operator==(  
   const VARIANT* pSrc) const;  
bool operator!=(  
   const VARIANT& varSrc) const;  
bool operator!=(  
   const VARIANT* pSrc) const;  
```  
  
#### <a name="parameters"></a>Parameter  
 *varSrc*  
 Ein `VARIANT` mit verglichen werden soll die `_variant_t` Objekt.  
  
 *pSrc*  
 Zeiger auf die `VARIANT` mit verglichen werden soll die `_variant_t` Objekt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** enthielte Vergleich **"false"** Wenn nicht.  
  
## <a name="remarks"></a>Hinweise  
 Vergleicht einen `_variant_t` Objekt mit einem `VARIANT`, testet auf Gleichheit oder Ungleichheit.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)