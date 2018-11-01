---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: d07e995be0ecd99974356a7516e7c4deee677637
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628240"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Microsoft-spezifisch**

Weist diesem `_variant_t`-Objekt eine Zeichenfolge zu.

## <a name="syntax"></a>Syntax

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>Parameter

*pSrc*<br/>
Zeiger auf die Zeichenfolge.

## <a name="remarks"></a>Hinweise

Konvertiert eine Zeichenfolge mit ANSI-Zeichen in eine Unicode-`BSTR`-Zeichenfolge und weist sie diesem `_variant_t`-Objekt zu.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)