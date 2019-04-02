---
title: MixIn-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: d0306f4c497dd26e782b1ef2c012cb7d348db07f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785735"
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
Ein abgeleiteter Typ von der [implementiert](implements-structure.md) Struktur.

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

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)