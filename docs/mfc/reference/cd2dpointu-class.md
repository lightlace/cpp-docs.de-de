---
title: CD2DPointU-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58eddd2a4c8be2520baf305f5212bd055412c821
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439223"
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
