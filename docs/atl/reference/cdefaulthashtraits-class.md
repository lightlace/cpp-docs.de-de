---
title: CDefaultHashTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: c8896ce27afc40ad095e02a2453628ffc05900da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466143"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits-Klasse

Diese Klasse stellt eine statische Funktion zum Berechnen der Hashwerte.

## <a name="syntax"></a>Syntax

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDefaultHashTraits::Hash](#hash)|(Statisch) Rufen Sie diese Funktion zum Berechnen der eines Hashwert für ein angegebenes Element ein.|

## <a name="remarks"></a>Hinweise

Diese Klasse enthält eine einzelne statische Funktion, die einen Hashwert für ein angegebenes Element zurückgibt. Diese Klasse wird verwendet, durch die [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md).

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="hash"></a>  CDefaultHashTraits::Hash

Rufen Sie diese Funktion zum Berechnen der eines Hashwert für ein angegebenes Element ein.

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>Parameter

*Element*<br/>
Das Element.

### <a name="return-value"></a>Rückgabewert

Gibt den Hashwert zurück.

### <a name="remarks"></a>Hinweise

Die Standardhashalgorithmus ist sehr einfach: der zurückgegebene Wert ist die Element-Anzahl. Überschreiben Sie diese Funktion, wenn ein etwas komplizierter Algorithmus erforderlich ist.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
