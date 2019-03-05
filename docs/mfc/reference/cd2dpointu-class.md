---
title: CD2DPointU-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: d66793abbb83015891df348eef8384e5c97baf2c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57281121"
---
# <a name="cd2dpointu-class"></a>CD2DPointU-Klasse

Ein Wrapper für `D2D1_POINT_2U`.

## <a name="syntax"></a>Syntax

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Überladen. Erstellt eine `CD2DPointU` aus Objekt `D2D1_POINT_2U` Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DPointU::operator CPoint](#operator_cpoint)|Konvertiert `CD2DPointU` zu `CPoint` Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU

Erstellt ein Objekt CD2DPointU aus CPoint-Objekt.

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
  CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Quellpunkt

*uX*<br/>
X-Quelle

*uY*<br/>
Quelle Y

##  <a name="operator_cpoint"></a>  CD2DPointU::Operator CPoint

CD2DPointU konvertiert in CPoint-Objekt.

```
operator CPoint();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert des D2D an.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
