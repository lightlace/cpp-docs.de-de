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
ms.openlocfilehash: 68ef72cfd256a2676c73223723f37374c50cb56f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943562"
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