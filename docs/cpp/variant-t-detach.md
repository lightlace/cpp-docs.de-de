---
title: _variant_t::Detach | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab1e4f83025dcc3e4bc65274746e0617cf31b5b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065022"
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

Extrahiert und gibt den gekapselten `VARIANT`, löscht Sie dann dieses `_variant_t` Objekt ohne Sie zu zerstören. Diese Memberfunktion entfernt die `VARIANT` aus der Kapselung und legt die `VARTYPE` dieses `_variant_t` Objekt auf VT_EMPTY. Sie entscheiden, ob Sie das zurückgegebene Version ist `VARIANT` durch Aufrufen der [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) Funktion.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)