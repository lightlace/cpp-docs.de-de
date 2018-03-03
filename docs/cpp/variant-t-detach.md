---
title: _variant_t::Detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 577b4874dd6d89c0c6c60b1a7981e74944e77ba8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft-spezifisch**  
  
 Trennt das gekapselte **VARIANT** -Objekt von diesem `_variant_t` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Das gekapselte **VARIANT**.  
  
## <a name="remarks"></a>Hinweise  
 Extrahiert und gibt den gekapselten **VARIANT**, löscht Sie dies `_variant_t` Objekt, ohne Sie zu zerstören. Diese Memberfunktion entfernt die **VARIANT** aus der Kapselung und legt die **VARTYPE** dieses `_variant_t` -Objekt `VT_EMPTY`. Es liegt bei Ihnen das Freigeben der zurückgegebenen **VARIANT** durch Aufrufen der [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) Funktion.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)