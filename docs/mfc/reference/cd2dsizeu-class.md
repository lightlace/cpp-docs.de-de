---
title: CD2DSizeU-Klasse
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: 45625331d0c1be8ca7c663d12c53516dc7bd77c7
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177188"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU-Klasse

Ein Wrapper für D2D1_SIZE_U.

## <a name="syntax"></a>Syntax

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Überladen. Erstellt ein `CD2DSizeU` -Objekt `D2D1_SIZE_U` aus dem-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSizeU::IsNull](#isnull)|Gibt einen **booleschen** Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten (null) enthält.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSizeU:: Operator CSize](#operator_csize)|Konvertiert `CD2DSizeU` in`CSize` ein-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget. h

##  <a name="cd2dsizeu"></a>CD2DSizeU:: CD2DSizeU

Erstellt ein CD2DSizeU-Objekt aus dem CSize-Objekt.

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Quellgröße

*verschoben*<br/>
Quell Breite

*CY*<br/>
Quell Höhe

##  <a name="isnull"></a>CD2DSizeU:: IsNull

Gibt einen booleschen Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten (null) enthält.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Breite und Höhe leer sind. andernfalls false.

##  <a name="operator_csize"></a>CD2DSizeU:: Operator CSize

Konvertiert CD2DSizeU in CSize-Objekt.

```
operator CSize();
```

### <a name="return-value"></a>Rückgabewert

Aktueller Wert der D2D Size.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
