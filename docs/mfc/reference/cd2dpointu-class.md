---
title: CD2DPointU-Klasse
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 6289d33aa0672d1ee423d91b11527dccfc868da7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177178"
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
|[CD2DPointU::CD2DPointU](#cd2dpointu)|Überladen. Erstellt eine `CD2DPointU` aus einem `D2D1_POINT_2U` Objekt Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DPointU:: Operator-CPoint](#operator_cpoint)|Konvertiert `CD2DPointU` in`CPoint` ein-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget. h

##  <a name="cd2dpointu"></a>CD2DPointU:: CD2DPointU

Erstellt ein CD2DPointU-Objekt aus dem CPoint-Objekt.

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
Quelle X

*uY*<br/>
Quelle Y

##  <a name="operator_cpoint"></a>CD2DPointU:: Operator-CPoint

Konvertiert CD2DPointU in ein CPoint-Objekt.

```
operator CPoint();
```

### <a name="return-value"></a>Rückgabewert

Aktueller Wert von D2D Point.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
