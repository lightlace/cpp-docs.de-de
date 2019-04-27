---
title: CSimpleArrayEqualHelperFalse Class
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
ms.openlocfilehash: 35207fdcbffc0e0367d86682b5f731eef617d761
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277954"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse Class

Diese Klasse ist eine Hilfsklasse für die [CSimpleArray](../../atl/reference/csimplearray-class.md) Klasse.

## <a name="syntax"></a>Syntax

```
template <class T>
class CSimpleArrayEqualHelperFalse
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Eine abgeleitete Klasse.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statisch) Gibt "false".|

## <a name="remarks"></a>Hinweise

Diese "traits"-Klasse ist eine Ergänzung der `CSimpleArray` Klasse. IT immer gibt "false", und darüber hinaus ruft `ATLASSERT` mit einem Argument von "false", wenn sie jemals verwiesen wird. In Situationen, in dem der Gleichheitstest auf ist nicht ausreichend definiert, kann diese Klasse ein Array mit Elementen, um für die meisten Methoden ordnungsgemäß, jedoch nicht in einer klar definierten Weise für Methoden, die zu vergleichen, z.B. modellkompatibilitätsgrad [CSimpleArray:: Suchen](../../atl/reference/csimplearray-class.md#find).

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelperFalse::IsEqual

Gibt false zurück.

```
static bool IsEqual(const T&, const T&);
```

### <a name="return-value"></a>Rückgabewert

Gibt false zurück.

### <a name="remarks"></a>Hinweise

Diese Methode immer "false" zurück und ruft `ATLASSERT` mit einem Argument von "false", wenn auf die verwiesen wird. Der Zweck der `CSimpleArrayEqualHelperFalse::IsEqual` besteht darin, erzwingen die Methoden, die mit, dass Vergleiche in einer klar definierten Weise fehl, wenn Gleichheitstests nicht ordnungsgemäß definiert wurden.

## <a name="see-also"></a>Siehe auch

[CSimpleArrayEqualHelper-Klasse](../../atl/reference/csimplearrayequalhelper-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
