---
title: CSimpleMapEqualHelperFalse-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bfa615af00535d899533f21abf933f35bcd5bbf
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767994"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse-Klasse

Diese Klasse ist eine Hilfsklasse für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.

## <a name="syntax"></a>Syntax

```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statisch) Testet zwei Schlüsseln auf Gleichheit.|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statisch) Gibt "false".|

## <a name="remarks"></a>Hinweise

Diese "traits"-Klasse dient zur Ergänzung der `CSimpleMap` Klasse. Es bietet eine Methode zum Vergleichen von zwei Elementen in der `CSimpleMap` Objekts, insbesondere zwei Elemente mit dem Wert oder zwei Hauptelemente.

Der Wertevergleich immer "false" zurück, und darüber hinaus ruft `ATLASSERT` mit einem Argument von "false", wenn sie jemals verwiesen wird. In Situationen, in dem der Gleichheitstest auf ist nicht ausreichend definiert, mit dieser Klasse können Sie eine Karte mit Schlüssel-Wert-Paare, um für die meisten Methoden ordnungsgemäß, jedoch nicht in einer klar definierten Weise für Methoden, die zu vergleichen, z.B. modellkompatibilitätsgrad [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpcoll.h

##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey

Testet zwei Schlüsseln auf Gleichheit.

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>Parameter

*k1*  
Der erste Schlüssel.

*k2*  
Der zweite Schlüssel.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Schlüssel gleich "false", andernfalls sind.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).

##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue

Gibt false zurück.

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>Rückgabewert

Gibt false zurück.

### <a name="remarks"></a>Hinweise

Diese Methode immer "false" zurück und ruft `ATLASSERT` mit einem Argument von "false", wenn sie jemals verwiesen wird. Der Zweck der `CSimpleMapEqualHelperFalse::IsEqualValue` besteht darin, erzwingen die Methoden, die mit, dass Vergleiche in einer klar definierten Weise fehl, wenn Gleichheitstests nicht ordnungsgemäß definiert wurden.

## <a name="see-also"></a>Siehe auch

[CSimpleMapEqualHelper-Klasse](../../atl/reference/csimplemapequalhelper-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
