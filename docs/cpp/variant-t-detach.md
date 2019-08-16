---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 8426c80af04b2c0906af150ea3e91304335e9f69
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500563"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft-spezifisch**

Trennt das gekapselte `VARIANT` - `_variant_t` Objekt von diesem-Objekt.

## <a name="syntax"></a>Syntax

```
VARIANT Detach( );
```

## <a name="return-value"></a>Rückgabewert

Der gekapselten `VARIANT`.

## <a name="remarks"></a>Hinweise

Extrahiert und gibt das gekapselte `VARIANT`zurück und löscht dann dieses `_variant_t` Objekt, ohne es zu zerstören. Diese Member-Funktion entfernt `VARIANT` den aus der Kapselung `VARTYPE` und legt `_variant_t` den dieses Objekts auf VT_EMPTY fest. Sie müssen den zurückgegebenen `VARIANT` freigeben, indem Sie die [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) -Funktion aufrufen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)