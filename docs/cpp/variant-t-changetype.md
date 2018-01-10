---
title: _variant_t::ChangeType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs: C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fb59090ebc4c6ff9120e813ae12a9defbe618b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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