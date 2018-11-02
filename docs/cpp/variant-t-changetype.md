---
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: 319c4fde808932e86021ee59b051261c43ca2edd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471239"
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

*VarType*<br/>
Die `VARTYPE` für diesen `_variant_t` Objekt.

*pSrc*<br/>
Ein Zeiger auf das `_variant_t`-Objekt, das umgewandelt werden soll. Wenn dieser Wert NULL ist, erfolgt die Konvertierung vorhanden.

## <a name="remarks"></a>Hinweise

Diese Memberfunktion konvertiert ein `_variant_t` Objekt in das angegebene `VARTYPE`. Wenn *pSrc* NULL ist, die Konvertierung erfolgt in vorhanden, andernfalls diese `_variant_t` Objekt wird aus kopiert *pSrc* und anschließend konvertiert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)