---
title: _variant_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs: C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 893cf8c10fce70645fa42373f08e6b4636e41d11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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