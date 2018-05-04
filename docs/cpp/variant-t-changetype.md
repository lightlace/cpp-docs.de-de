---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53fd73fc9606053dda6f8c143618373ad9bb7e4e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Microsoft-spezifisch**  
  
 Ändert den Typ des der `_variant_t` Objekt für das angezeigte **VARTYPE**.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `vartype`  
 Die **VARTYPE** dafür `_variant_t` Objekt.  
  
 `pSrc`  
 Ein Zeiger auf das `_variant_t`-Objekt, das umgewandelt werden soll. Wenn dieser Wert ist **NULL**, Konvertierung direkt ausgeführt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Memberfunktion konvertiert ein `_variant_t` in das angegebene Objekt **VARTYPE**. Wenn `pSrc` ist **NULL**, die Konvertierung erfolgt eingerichtet ist, andernfalls das `_variant_t` Objekt wird von kopiert `pSrc` und anschließend konvertiert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)