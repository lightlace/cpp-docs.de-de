---
title: CSimpleArrayEqualHelperFalse-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6cc489850ea8e8d2704c92d1c2a671557a4db67a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084327"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse-Klasse

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
