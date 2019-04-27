---
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: 510267c7ab00fe22a93dc01342def5fc262ddb04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166217"
---
# <a name="varianttattach"></a>_variant_t::Attach

**Microsoft-spezifisch**

Fügt eine `VARIANT` -Objekt in der **_variant_t** Objekt.

## <a name="syntax"></a>Syntax

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>Parameter

*varSrc*<br/>
Ein `VARIANT` Objekt, das an diese angefügt werden **_variant_t** Objekt.

## <a name="remarks"></a>Hinweise

Übernimmt den Besitz der `VARIANT` durch Kapselung. Diese Memberfunktion gibt jedes vorhandene gekapselte `VARIANT`, kopiert dann das angegebene `VARIANT`, und legt seine `VARTYPE` auf VT_EMPTY, um sicherzustellen, die Ressourcen nur freigegeben werden können, indem die **_variant_t** Destruktor.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)