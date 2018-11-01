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
ms.openlocfilehash: 138916efe781d8bef69a1c4eb61a73c5a405be67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551852"
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
|[CD2DPointU::Operator CPoint](#operator_cpoint)|Konvertiert `CD2DPointU` zu `CPoint` Objekt.|

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
