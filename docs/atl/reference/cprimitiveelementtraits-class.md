---
title: CPrimitiveElementTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: 53d039b15c9f4a79956bd86fbb93600854f90e5f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263051"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits-Klasse

Diese Klasse stellt die Standardmethoden und -Funktionen für eine Auflistungsklasse bestehend aus primitiven Datentypen.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in das Klassenobjekt Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.|
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.|

## <a name="remarks"></a>Hinweise

Diese Klasse bietet standardmäßig statische Funktionen und Methoden zum Verschieben, kopieren, vergleichen und hashing primitiven Typ Datenelemente in einem Auflistungsobjekt-Klasse gespeichert.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="inargtype"></a>  CPrimitiveElementTraits::INARGTYPE

Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.

```
typedef T INARGTYPE;
```

##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE

Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Siehe auch

[CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
