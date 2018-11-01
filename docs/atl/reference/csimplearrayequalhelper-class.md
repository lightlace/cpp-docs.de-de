---
title: CSimpleArrayEqualHelper-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e677a5d12918649597db9614b965118f8d6b7da6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656222"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper-Klasse

Diese Klasse ist eine Hilfsklasse für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.

## <a name="syntax"></a>Syntax

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statisch) Prüft zwei `CSimpleArray` Objektelemente hinsichtlich ihrer Gleichheit.|

## <a name="remarks"></a>Hinweise

Diese "traits"-Klasse dient zur Ergänzung der `CSimpleArray` Klasse. Es stellt eine Methode bereit, für die im Vergleich von zwei Elementen gespeichert werden. eine `CSimpleArray` Objekt. Standardmäßig werden die Elemente verglichen, mit **operator=()**, aber wenn das Array von komplexen Datentypen, die ihre eigenen Equality-Operator hat enthält, müssen Sie diese Klasse überschreiben.

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual

Prüft zwei `CSimpleArray` Objektelemente hinsichtlich ihrer Gleichheit.

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>Parameter

*T1*<br/>
Ein Objekt vom Typ "t".

*T2*<br/>
Ein Objekt vom Typ "t".

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.

## <a name="see-also"></a>Siehe auch

[CSimpleArray-Klasse](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse-Klasse](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
