---
title: CD2DLinearGradientBrush-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: d86235893d1f238f4cba9c927fad17f29060e591
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258723"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush-Klasse

Ein Wrapper für ID2D1LinearGradientBrush.

## <a name="syntax"></a>Syntax

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Erstellt ein CD2DLinearGradientBrush-Objekt.|
|[CD2DLinearGradientBrush::~CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsels mit linearem Farbverlauf-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DLinearGradientBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DLinearGradientBrush::Create](#create)|Erstellt eine CD2DLinearGradientBrush an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DLinearGradientBrush::Destroy](#destroy)|Zerstört ein CD2DLinearGradientBrush-Objekt. (Überschreibt [CD2DGradientBrush:: Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|
|[CD2DLinearGradientBrush::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DLinearGradientBrush::Get](#get)|Gibt die ID2D1LinearGradientBrush-Schnittstelle|
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Ruft die Endkoordinaten des linearen Farbverlaufs|
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Ruft die Anfangskoordinaten des linearen Farbverlaufs|
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Legt die Endkoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels|
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Legt die Anfangskoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush*](#operator_id2d1lineargradientbrush_star)|Gibt die ID2D1LinearGradientBrush-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Die Start- und Endpunkt des Farbverlaufs entspricht.|
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Ein Zeiger auf ein ID2D1LinearGradientBrush.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dlineargradientbrush"></a>  CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush

Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsels mit linearem Farbverlauf-Objekt zerstört wird.

```
virtual ~CD2DLinearGradientBrush();
```

##  <a name="attach"></a>  CD2DLinearGradientBrush::Attach

Hängt die vorhandene Ressourcenschnittstelle für das Objekt

```
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. NULL darf nicht sein

##  <a name="cd2dlineargradientbrush"></a>  CD2DLinearGradientBrush::CD2DLinearGradientBrush

Erstellt ein CD2DLinearGradientBrush-Objekt.

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
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

*LinearGradientBrushProperties*<br/>
Die Start- und Endpunkt des Farbverlaufs entspricht.

*colorInterpolationGamma*<br/>
Der Speicherplatz in der die, den Farbe der Interpolation zwischen dem Farbverlaufsstopp ausgeführt wird.

*extendMode*<br/>
Das Verhalten der Farbverlauf außerhalb der normalisierten Bereich [0,1].

*pBrushProperties*<br/>
Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DLinearGradientBrush::Create

Erstellt eine CD2DLinearGradientBrush an.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DLinearGradientBrush::Destroy

Zerstört ein CD2DLinearGradientBrush-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DLinearGradientBrush::Detach

Resource-Schnittstelle aus dem Objekt getrennt

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="get"></a>  CD2DLinearGradientBrush::Get

Gibt die ID2D1LinearGradientBrush-Schnittstelle

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1LinearGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getendpoint"></a>  CD2DLinearGradientBrush::GetEndPoint

Ruft die Endkoordinaten des linearen Farbverlaufs

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>Rückgabewert

Die zweidimensionalen Endkoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels

##  <a name="getstartpoint"></a>  CD2DLinearGradientBrush::GetStartPoint

Ruft die Anfangskoordinaten des linearen Farbverlaufs

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>Rückgabewert

Die zweidimensionalen Anfangskoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels

##  <a name="m_lineargradientbrushproperties"></a>  CD2DLinearGradientBrush::m_LinearGradientBrushProperties

Die Start- und Endpunkt des Farbverlaufs entspricht.

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

##  <a name="m_plineargradientbrush"></a>  CD2DLinearGradientBrush::m_pLinearGradientBrush

Ein Zeiger auf ein ID2D1LinearGradientBrush.

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

##  <a name="operator_id2d1lineargradientbrush_star"></a>  CD2DLinearGradientBrush::Operator ID2D1LinearGradientBrush *

Gibt die ID2D1LinearGradientBrush-Schnittstelle

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1LinearGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="setendpoint"></a>  CD2DLinearGradientBrush::SetEndPoint

Legt die Endkoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels

```
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parameter

*point*<br/>
Die zweidimensionalen Endkoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels

##  <a name="setstartpoint"></a>  CD2DLinearGradientBrush::SetStartPoint

Legt die Anfangskoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels

```
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>Parameter

*point*<br/>
Die zweidimensionalen Anfangskoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
