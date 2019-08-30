---
title: CD2DSizeF-Klasse
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: df895c278003e2c71f37a00af6bf14912756701a
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177202"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF-Klasse

Ein Wrapper für D2D1_SIZE_F.

## <a name="syntax"></a>Syntax

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSizeF::CD2DSizeF](#cd2dsizef)|Überladen. Erstellt ein `CD2DSizeF` -Objekt `D2D1_SIZE_F` aus dem-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSizeF::IsNull](#isnull)|Gibt einen **booleschen** Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten (null) enthält.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSizeF:: Operator CSize](#operator_csize)|Konvertiert `CD2DSizeF` in`CSize` ein-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget. h

##  <a name="cd2dsizef"></a>CD2DSizeF:: CD2DSizeF

Erstellt ein CD2DSizeF-Objekt aus dem CSize-Objekt.

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Quellgröße

*verschoben*<br/>
Quell Breite

*CY*<br/>
Quell Höhe

##  <a name="isnull"></a>CD2DSizeF:: IsNull

Gibt einen booleschen Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten (null) enthält.

```
BOOL IsNull() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn Breite und Höhe leer sind. andernfalls false.

##  <a name="operator_csize"></a>CD2DSizeF:: Operator CSize

Konvertiert CD2DSizeF in CSize-Objekt.

```
operator CSize();
```

### <a name="return-value"></a>Rückgabewert

Aktueller Wert der D2D Size.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
