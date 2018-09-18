---
title: CSimpleArrayEqualHelper-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2613a885dd5399c3655ecb853f3977be71928526
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021056"
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
