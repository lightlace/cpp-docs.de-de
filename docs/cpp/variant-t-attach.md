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
ms.openlocfilehash: 33e21d3bea71c80b8b60df222682fda560fbce9c
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
