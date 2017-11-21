---
title: _variant_t::SetString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _variant_t::SetString
dev_langs: C++
helpviewer_keywords: SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc0fd027bbb4a1049e46351a8a544dac8c5a47aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft-spezifisch**  
  
 Weist diesem `_variant_t`-Objekt eine Zeichenfolge zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void SetString(  
   const char* pSrc   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pSrc`  
 Zeiger auf die Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Konvertiert eine Zeichenfolge mit ANSI-Zeichen in eine Unicode-`BSTR`-Zeichenfolge und weist sie diesem `_variant_t`-Objekt zu.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)