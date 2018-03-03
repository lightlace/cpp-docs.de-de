---
title: _variant_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: effeaaaf3f8df9eb100d5e92e760eb439a865552
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft-spezifisch**  
  
 Fügt eine **VARIANT** -Objekt in der `_variant_t` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *varSrc*  
 Ein **VARIANT** Objekt an diese angefügt werden `_variant_t` Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Übernimmt den Besitz der **VARIANT** durch Kapselung. Diese Memberfunktion gibt jedes vorhandene gekapselte **VARIANT**, kopiert dann das angegebene **VARIANT**, und legt seine **VARTYPE** zu `VT_EMPTY` um sicherzustellen, seine Ressourcen können nur freigegeben werden, indem die `_variant_t` Destruktor.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)