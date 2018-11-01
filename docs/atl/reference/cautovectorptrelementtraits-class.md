---
title: CAutoVectorPtrElementTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: b71ac4163c1c34fbbe686cdff05319347db521cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459006"
---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits-Klasse

Diese Klasse stellt die Methoden, statische Funktionen und Typdefinitionen hilfreich beim Erstellen von Sammlungen von intelligenten Zeigern, die mit der neuen Vektor und "delete".

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Zeigertyp.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt die Methoden, statische Funktionen und Typedefs für dadurch die Erstellung von Auflistungsobjekten-Klasse, die intelligente Zeiger. Im Gegensatz zu [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md), diese Klasse verwendet vector-new und delete-Operator.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="inargtype"></a>  CAutoVectorPtrElementTraits::INARGTYPE

Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoVectorPtrElementTraits::OUTARGTYPE

Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>Siehe auch

[CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CAutoVectorPtr-Klasse](../../atl/reference/cautovectorptr-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
