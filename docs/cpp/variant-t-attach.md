---
title: _variant_t::Attach | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 567a3387e79244443b784549d6223a14f78103ce
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464679"
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft-spezifisch**  
  
 Fügt eine `VARIANT` -Objekt in der **_variant_t** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
void Attach(VARIANT& varSrc);  
```  
  
#### <a name="parameters"></a>Parameter  
 *varSrc*  
 Ein `VARIANT` Objekt, das an diese angefügt werden **_variant_t** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Übernimmt den Besitz der `VARIANT` durch Kapselung. Diese Memberfunktion gibt jedes vorhandene gekapselte `VARIANT`, kopiert dann das angegebene `VARIANT`, und legt seine `VARTYPE` auf VT_EMPTY, um sicherzustellen, die Ressourcen nur freigegeben werden können, indem die **_variant_t** Destruktor.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)