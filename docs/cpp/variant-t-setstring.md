---
title: _variant_t::SetString | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 090fd7ed027738ebe7bc9276e3b3f124b9212c4a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463466"
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft-spezifisch**  
  
 Weist diesem `_variant_t`-Objekt eine Zeichenfolge zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
void SetString(const char* pSrc);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pSrc*  
 Zeiger auf die Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Konvertiert eine Zeichenfolge mit ANSI-Zeichen in eine Unicode-`BSTR`-Zeichenfolge und weist sie diesem `_variant_t`-Objekt zu.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)