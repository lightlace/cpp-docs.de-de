---
title: CD2DEllipse-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs:
- C++
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6acec41bcae08f5585eb521dc90ff12d082fd5ad
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418683"
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

*Rect*<br/>
Quellrechteck

*Ellipse*<br/>
Quelle ellipse

*ptCenter*<br/>
Der Mittelpunkt der Ellipse.

*sizeRadius*<br/>
Die X-Radius und die Y-Radius der Ellipse.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
