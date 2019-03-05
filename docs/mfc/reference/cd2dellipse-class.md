---
title: CD2DEllipse-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 3abf0736884840be7bdcfcd55cb18a0bc8e69195
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270823"
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
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Überladen. Erstellt eine `CD2DEllipse` -Sitzungsobjekts `D2D1_ELLIPSE` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="cd2dellipse"></a>  CD2DEllipse::CD2DEllipse

Erstellt ein Objekt CD2DEllipse CD2DRectF-Objekts.

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
Quellrechteck

*ellipse*<br/>
Quelle ellipse

*ptCenter*<br/>
Der Mittelpunkt der Ellipse.

*sizeRadius*<br/>
Die X-Radius und die Y-Radius der Ellipse.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
