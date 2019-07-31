---
title: CD2DRectF-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
ms.openlocfilehash: 9b91cfaec3827a61152c4116b56e817a436606be
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682405"
---
# <a name="cd2drectf-class"></a>CD2DRectF-Klasse

Ein Wrapper für `D2D1_RECT_F`.

## <a name="syntax"></a>Syntax

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|Überladen. Erstellt ein `CD2DRectF` -Objekt `D2D1_RECT_F` aus dem-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectF::IsNull](#isnull)|Gibt einen **booleschen** Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten (null) enthält.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRectF:: Operator CRect](#operator_crect)|Konvertiert `CD2DRectF` in`CRect` ein-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget. h

##  <a name="cd2drectf"></a>CD2DRectF:: CD2DRectF

Erstellt ein CD2DRectF-Objekt aus dem CRect-Objekt.

```
CD2DRectF(const CRect& rect);
CD2DRectF(const D2D1_RECT_F& rect);
CD2DRectF(const D2D1_RECT_F* rect);

CD2DRectF(
    FLOAT fLeft = 0.,
    FLOAT fTop = 0.,
    FLOAT fRight = 0.,
    FLOAT fBottom = 0.);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Quell Rechteck

*fLeft*<br/>
Quell linke Koordinate

*fTop*<br/>
obere Koordinate der Quelle

*fRight*<br/>
Quell rechte Koordinate

*fBottom*<br/>
Quelle unten-Koordinate

##  <a name="isnull"></a>CD2DRectF:: IsNull

Gibt einen booleschen Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten (null) enthält.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Werte oben, Links, unten und rechts des Rechtecks gleich 0 sind. andernfalls false.

##  <a name="operator_crect"></a>CD2DRectF:: Operator CRect

Konvertiert CD2DRectF in CRect-Objekt.

```
operator CRect();
```

### <a name="return-value"></a>Rückgabewert

Aktueller Wert des D2D-Rechtecks.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
