---
title: CElementTraitsBase-Klasse
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: 769fa5abff223ad570847b8bf68378ce85df664e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509016"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase-Klasse

Diese Klasse bietet standardmäßige kopieren und verschieben die Methoden, damit eine Auflistungsklasse.

## <a name="syntax"></a>Syntax

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|Rufen Sie diese Methode zum Kopieren von Elementen in einem Auflistungsobjekt-Klasse gespeichert.|
|[CElementTraitsBase::RelocateElements](#relocateelements)|Rufen Sie diese Methode, um in einem Objekt der Klasse Auflistung gespeicherten Elemente zu verschieben.|

## <a name="remarks"></a>Hinweise

Diese Basisklasse definiert Methoden zum Kopieren und Verschieben von Elementen in eine Auflistungsklasse. Es wird verwendet, durch die Klassen [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="copyelements"></a>  CElementTraitsBase::CopyElements

Rufen Sie diese Methode zum Kopieren von Elementen in einem Auflistungsobjekt-Klasse gespeichert.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parameter

*pDest*<br/>
Zeiger auf das erste Element, das die kopierten Daten erhält.

*pSrc*<br/>
Zeiger auf das erste Element zu kopieren.

*nElements*<br/>
Die Anzahl der zu kopierenden Elemente.

### <a name="remarks"></a>Hinweise

Die Quelle und Ziel-Elemente sollten sich nicht überschneiden.

##  <a name="inargtype"></a>  CElementTraitsBase::INARGTYPE

Der Datentyp für Elemente der Auflistung hinzugefügt werden soll.

```
typedef const T& INARGTYPE;
```

##  <a name="outargtype"></a>  CElementTraitsBase::OUTARGTYPE

Der Datentyp, zum Abrufen von Elementen aus der Auflistung verwendet werden soll.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CElementTraitsBase::RelocateElements

Rufen Sie diese Methode, um in einem Objekt der Klasse Auflistung gespeicherten Elemente zu verschieben.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parameter

*pDest*<br/>
Zeiger auf das erste Element, das die verschobenen Daten erhält.

*pSrc*<br/>
Zeiger auf das erste Element, zu verschieben.

*nElements*<br/>
Die Anzahl der Elemente zu verschieben.

### <a name="remarks"></a>Hinweise

Diese Methode ruft [Memmove](../../c-runtime-library/reference/memmove-wmemmove.md), dies ist ausreichend für die meisten Datentypen. Wenn die Objekte, die verschoben werden Zeiger auf ihre eigenen Member enthalten, müssen diese Methode außer Kraft gesetzt werden.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
