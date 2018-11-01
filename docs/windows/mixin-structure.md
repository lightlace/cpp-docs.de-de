---
title: MixIn-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: e6c4fb2abd6c27f8feec4357e17ef71b385cb7a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464931"
---
# <a name="mixin-structure"></a>MixIn-Struktur

Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.

## <a name="syntax"></a>Syntax

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>Parameter

*Abgeleitete*<br/>
Ein abgeleiteter Typ von der [implementiert](../windows/implements-structure.md) Struktur.

*MixInType*<br/>
Ein Basistyp.

*hasImplements*<br/>
**"true"** Wenn *MixInType* ist abgeleitet von der aktuellen Implementierung Basistyp **"false"** andernfalls.

## <a name="remarks"></a>Hinweise

Wenn eine Klasse von Windows-Runtime und COM-Klassenschnittstellen abgeleitet ist, Liste der Deklaration muss zunächst alle Windows-Runtime-Schnittstellen aufgelistet, und klicken Sie dann alle klassischen COM-Schnittstellen. **MixIn** wird sichergestellt, dass die Schnittstellen in der richtigen Reihenfolge angegeben werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`MixIn`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)