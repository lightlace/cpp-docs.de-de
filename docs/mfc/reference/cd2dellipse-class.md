---
title: CD2DEllipse-Klasse
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 21087682d40dac521cc949a39ef4b1aab23e7d71
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177211"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse-Klasse

Ein Wrapper für `D2D1_ELLIPSE`.

## <a name="syntax"></a>Syntax

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DEllipse:: CD2DEllipse](#cd2dellipse)|Überladen. Erstellt ein `CD2DEllipse` -Objekt `D2D1_ELLIPSE` aus dem-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget. h

##  <a name="cd2dellipse"></a>CD2DEllipse:: CD2DEllipse

Erstellt ein CD2DEllipse-Objekt aus dem CD2DRectF-Objekt.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Quell Rechteck

*ellipse*<br/>
quellellipse

*ptCenter*<br/>
Der Mittelpunkt der Ellipse.

*sizeRadius*<br/>
Der X-RADIUS-und Y-Radius der Ellipse.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
