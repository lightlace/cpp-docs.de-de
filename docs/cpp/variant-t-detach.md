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
ms.openlocfilehash: 719852c4556291747b612d54c44d4bf82caa9188
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519005"
---
# <a name="varianttdetach"></a>_variant_t::Detach

**Microsoft-spezifisch**

Trennt das gekapselte `VARIANT` -Objekt aus diesem `_variant_t` Objekt.

## <a name="syntax"></a>Syntax

```
VARIANT Detach( );
```

## <a name="return-value"></a>Rückgabewert

Das gekapselte `VARIANT`.

## <a name="remarks"></a>Hinweise

Extrahiert und gibt den gekapselten `VARIANT`, löscht Sie dann dieses `_variant_t` Objekt ohne Sie zu zerstören. Diese Memberfunktion entfernt die `VARIANT` aus der Kapselung und legt die `VARTYPE` dieses `_variant_t` Objekt auf VT_EMPTY. Sie entscheiden, ob Sie das zurückgegebene Version ist `VARIANT` durch Aufrufen der [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear) Funktion.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)