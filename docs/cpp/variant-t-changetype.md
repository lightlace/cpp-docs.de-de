---
title: _variant_t::ChangeType | Microsoft-Dokumentation
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
ms.openlocfilehash: 5f3790f4cb357ed830ba2c61b3c2906356dc64da
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465587"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Microsoft-spezifisch**  
  
 Ändert den Typ des der `_variant_t` -Objekts in den angegebenen `VARTYPE`.  
  
## <a name="syntax"></a>Syntax  
  
```  
void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *VarType*  
 Die `VARTYPE` für diesen `_variant_t` Objekt.  
  
 *pSrc*  
 Ein Zeiger auf das `_variant_t`-Objekt, das umgewandelt werden soll. Wenn dieser Wert NULL ist, erfolgt die Konvertierung vorhanden.  
  
## <a name="remarks"></a>Hinweise  
 Diese Memberfunktion konvertiert ein `_variant_t` Objekt in das angegebene `VARTYPE`. Wenn *pSrc* NULL ist, die Konvertierung erfolgt in vorhanden, andernfalls diese `_variant_t` Objekt wird aus kopiert *pSrc* und anschließend konvertiert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_variant_t-Klasse](../cpp/variant-t-class.md)