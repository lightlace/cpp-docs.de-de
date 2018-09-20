---
title: CD2DRadialGradientBrush-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36a5c33f8dd9ce4ecef1c2900a13100683fe2889
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405137"
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush-Klasse

Ein Wrapper für ID2D1RadialGradientBrush.

## <a name="syntax"></a>Syntax

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Erstellt ein CD2DLinearGradientBrush-Objekt.|
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsel mit strahlenförmigem Farbverlauf-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRadialGradientBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DRadialGradientBrush::Create](#create)|Erstellt eine CD2DRadialGradientBrush an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DRadialGradientBrush::Destroy](#destroy)|Zerstört ein CD2DRadialGradientBrush-Objekt. (Überschreibt [CD2DGradientBrush:: Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DRadialGradientBrush::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DRadialGradientBrush::Get](#get)|Gibt die ID2D1RadialGradientBrush-Schnittstelle|
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Ruft den Mittelpunkt der Ellipse Farbverlauf|
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Ruft den Offset des Farbverlaufsursprung relativ zu den Farbverlauf der Ellipse center|
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Ruft den X-Radius der Ellipse Farbverlauf|
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Ruft den y-Radius der Ellipse Farbverlauf|
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Gibt an der Mitte des Farbverlaufs Ellipse im Koordinatenraum des Pinsels|
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Gibt den Offset des Farbverlaufsursprung relativ zu den Farbverlauf der Ellipse center|
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Gibt den X-Radius der Ellipse Farbverlauf im Koordinatenraum des Pinsels|
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Gibt den y-Radius der Ellipse Farbverlauf im Koordinatenraum des Pinsels|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DRadialGradientBrush::Operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|Gibt die ID2D1RadialGradientBrush-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|Ein Zeiger auf ein ID2D1RadialGradientBrush.|
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Das Center, die Farbverlaufsursprungsoffset und die X-Radius und die y-Radius des Pinsels Farbverlauf des.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dradialgradientbrush"></a>  CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush

Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsel mit strahlenförmigem Farbverlauf-Objekt zerstört wird.

```
virtual ~CD2DRadialGradientBrush();
```

##  <a name="attach"></a>  CD2DRadialGradientBrush::Attach

Hängt die vorhandene Ressourcenschnittstelle für das Objekt

```
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. NULL darf nicht sein

##  <a name="cd2dradialgradientbrush"></a>  CD2DRadialGradientBrush::CD2DRadialGradientBrush

Erstellt ein CD2DLinearGradientBrush-Objekt.

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*gradientStops*<br/>
Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.

*gradientStopsCount*<br/>
Ein Wert größer als oder gleich 1, der die Anzahl der Farbverlaufsstopps in GradientStops-Array angibt.

*RadialGradientBrushProperties*<br/>
Das Center, die Farbverlaufsursprungsoffset und die X-Radius und die y-Radius des Pinsels Farbverlauf des.

*colorInterpolationGamma*<br/>
Der Speicherplatz in der die, den Farbe der Interpolation zwischen dem Farbverlaufsstopp ausgeführt wird.

*extendMode*<br/>
Das Verhalten der Farbverlauf außerhalb der normalisierten Bereich [0,1].

*pBrushProperties*<br/>
Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DRadialGradientBrush::Create

Erstellt eine CD2DRadialGradientBrush an.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DRadialGradientBrush::Destroy

Zerstört ein CD2DRadialGradientBrush-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DRadialGradientBrush::Detach

Resource-Schnittstelle aus dem Objekt getrennt

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="get"></a>  CD2DRadialGradientBrush::Get

Gibt die ID2D1RadialGradientBrush-Schnittstelle

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1RadialGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getcenter"></a>  CD2DRadialGradientBrush::GetCenter

Ruft den Mittelpunkt der Ellipse Farbverlauf

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>Rückgabewert

Die Mitte des Farbverlaufs Ellipse. Dieser Wert wird im Koordinatenraum des Pinsels angegeben.

##  <a name="getgradientoriginoffset"></a>  CD2DRadialGradientBrush::GetGradientOriginOffset

Ruft den Offset des Farbverlaufsursprung relativ zu den Farbverlauf der Ellipse center

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>Rückgabewert

Der Offset des Farbverlaufsursprung aus der Mitte des Farbverlaufs Ellipse. Dieser Wert wird im Koordinatenraum des Pinsels angegeben.

##  <a name="getradiusx"></a>  CD2DRadialGradientBrush::GetRadiusX

Ruft den X-Radius der Ellipse Farbverlauf

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>Rückgabewert

Der X-Radius der Ellipse Farbverlauf. Dieser Wert wird im Koordinatenraum des Pinsels angegeben.

##  <a name="getradiusy"></a>  CD2DRadialGradientBrush::GetRadiusY

Ruft den y-Radius der Ellipse Farbverlauf

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>Rückgabewert

Der y-Radius der Ellipse Farbverlauf. Dieser Wert wird im Koordinatenraum des Pinsels angegeben.

##  <a name="m_pradialgradientbrush"></a>  CD2DRadialGradientBrush::m_pRadialGradientBrush

Ein Zeiger auf ein ID2D1RadialGradientBrush.

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

##  <a name="m_radialgradientbrushproperties"></a>  CD2DRadialGradientBrush::m_RadialGradientBrushProperties

Das Center, die Farbverlaufsursprungsoffset und die X-Radius und die y-Radius des Pinsels Farbverlauf des.

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

##  <a name="operator_id2d1radialgradientbrush_star"></a>  CD2DRadialGradientBrush::Operator ID2D1RadialGradientBrush *

Gibt die ID2D1RadialGradientBrush-Schnittstelle

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1RadialGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="setcenter"></a>  CD2DRadialGradientBrush::SetCenter

Gibt an der Mitte des Farbverlaufs Ellipse im Koordinatenraum des Pinsels

```
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
Die Mitte des Farbverlaufs Ellipse im Koordinatenraum des Pinsels

##  <a name="setgradientoriginoffset"></a>  CD2DRadialGradientBrush::SetGradientOriginOffset

Gibt den Offset des Farbverlaufsursprung relativ zu den Farbverlauf der Ellipse center

```
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>Parameter

*gradientOriginOffset*<br/>
Der Offset des Farbverlaufsursprung aus der Mitte des Farbverlaufs ellipse

##  <a name="setradiusx"></a>  CD2DRadialGradientBrush::SetRadiusX

Gibt den X-Radius der Ellipse Farbverlauf im Koordinatenraum des Pinsels

```
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>Parameter

*radiusX*<br/>
Der X-Radius der Ellipse Farbverlauf. Dieser Wert wird im Koordinatenraum des Pinsels

##  <a name="setradiusy"></a>  CD2DRadialGradientBrush::SetRadiusY

Gibt den y-Radius der Ellipse Farbverlauf im Koordinatenraum des Pinsels

```
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>Parameter

*radiusY*<br/>
Der y-Radius der Ellipse Farbverlauf. Dieser Wert wird im Koordinatenraum des Pinsels

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
