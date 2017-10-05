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
- VARIANT object, detatch
- Detach method
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
caps.latest.revision: 7
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
ms.openlocfilehash: 402d8bfeb6aea45460124bdeaaa8b3ee485df622
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
