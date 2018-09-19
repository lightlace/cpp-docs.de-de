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
ms.openlocfilehash: e680f4f42881ea89510048f43d657d1579686527
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109261"
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