---
title: CD2DSolidColorBrush-Klasse
ms.date: 03/27/2019
f1_keywords:
- CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::CD2DSolidColorBrush
- AFXRENDERTARGET/CD2DSolidColorBrush::Attach
- AFXRENDERTARGET/CD2DSolidColorBrush::Create
- AFXRENDERTARGET/CD2DSolidColorBrush::Destroy
- AFXRENDERTARGET/CD2DSolidColorBrush::Detach
- AFXRENDERTARGET/CD2DSolidColorBrush::Get
- AFXRENDERTARGET/CD2DSolidColorBrush::GetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::SetColor
- AFXRENDERTARGET/CD2DSolidColorBrush::m_colorSolid
- AFXRENDERTARGET/CD2DSolidColorBrush::m_pSolidColorBrush
helpviewer_keywords:
- CD2DSolidColorBrush [MFC], CD2DSolidColorBrush
- CD2DSolidColorBrush [MFC], Attach
- CD2DSolidColorBrush [MFC], Create
- CD2DSolidColorBrush [MFC], Destroy
- CD2DSolidColorBrush [MFC], Detach
- CD2DSolidColorBrush [MFC], Get
- CD2DSolidColorBrush [MFC], GetColor
- CD2DSolidColorBrush [MFC], SetColor
- CD2DSolidColorBrush [MFC], m_colorSolid
- CD2DSolidColorBrush [MFC], m_pSolidColorBrush
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
ms.openlocfilehash: f225198193443c11d0294010a5fb71858514c81e
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565411"
---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush-Klasse

Ein Wrapper für ID2D1SolidColorBrush.

## <a name="syntax"></a>Syntax

```
class CD2DSolidColorBrush : public CD2DBrush;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|Überladen. Erstellt ein CD2DSolidColorBrush-Objekt.|
|[CD2DSolidColorBrush::~CD2DSolidColorBrush](#_dtorcd2dsolidcolorbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsels in Volltonfarbe-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSolidColorBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DSolidColorBrush::Create](#create)|Erstellt eine CD2DSolidColorBrush an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DSolidColorBrush::Destroy](#destroy)|Zerstört ein CD2DSolidColorBrush-Objekt. (Überschreibt [CD2DBrush:: Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|
|[CD2DSolidColorBrush::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DSolidColorBrush::Get](#get)|Gibt die ID2D1SolidColorBrush-Schnittstelle|
|[CD2DSolidColorBrush::GetColor](#getcolor)|Ruft die Farbe der Pinsel mit Volltonfarbe|
|[CD2DSolidColorBrush::SetColor](#setcolor)|Gibt die Farbe des dieser Pinsel mit Volltonfarbe|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush*](#operator_id2d1solidcolorbrush_star)|Gibt die ID2D1SolidColorBrush-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|Solid Pinselfarbe.|
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|Speichert einen Zeiger auf ein ID2D1SolidColorBrush-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dsolidcolorbrush"></a>  CD2DSolidColorBrush:: ~ CD2DSolidColorBrush

Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsels in Volltonfarbe-Objekt zerstört wird.

```
virtual ~CD2DSolidColorBrush();
```

##  <a name="attach"></a>  CD2DSolidColorBrush::Attach

Hängt die vorhandene Ressourcenschnittstelle für das Objekt

```
void Attach(ID2D1SolidColorBrush* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. NULL darf nicht sein

##  <a name="cd2dsolidcolorbrush"></a>  CD2DSolidColorBrush::CD2DSolidColorBrush

Erstellt ein CD2DSolidColorBrush-Objekt.

```
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    D2D1_COLOR_F color,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,
    COLORREF color,
    int nAlpha = 255,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*color*<br/>
Die roten, grünen, blauen und alpha-Werte der Farbe des Pinsels.

*pBrushProperties*<br/>
Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

*nAlpha*<br/>
Die Deckkraft der Farbe des Pinsels.

##  <a name="create"></a>  CD2DSolidColorBrush::Create

Erstellt eine CD2DSolidColorBrush an.

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>Parameter

*pRenderTarget*<br/>
Ein Zeiger auf das Renderziel.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DSolidColorBrush::Destroy

Zerstört ein CD2DSolidColorBrush-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DSolidColorBrush::Detach

Resource-Schnittstelle aus dem Objekt getrennt

```
ID2D1SolidColorBrush* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="get"></a>  CD2DSolidColorBrush::Get

Gibt die ID2D1SolidColorBrush-Schnittstelle

```
ID2D1SolidColorBrush* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1SolidColorBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getcolor"></a>  CD2DSolidColorBrush::GetColor

Ruft die Farbe der Pinsel mit Volltonfarbe

```
D2D1_COLOR_F GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe des dieser Pinsel mit Volltonfarbe

##  <a name="m_colorsolid"></a>  CD2DSolidColorBrush::m_colorSolid

Solid Pinselfarbe.

```
D2D1_COLOR_F m_colorSolid;
```

##  <a name="m_psolidcolorbrush"></a>  CD2DSolidColorBrush::m_pSolidColorBrush

Speichert einen Zeiger auf ein ID2D1SolidColorBrush-Objekt.

```
ID2D1SolidColorBrush* m_pSolidColorBrush;
```

##  <a name="operator_id2d1solidcolorbrush_star"></a>  CD2DSolidColorBrush::operator ID2D1SolidColorBrush*

Gibt die ID2D1SolidColorBrush-Schnittstelle

```
operator ID2D1SolidColorBrush*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1SolidColorBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="setcolor"></a>  CD2DSolidColorBrush::SetColor

Gibt die Farbe des dieser Pinsel mit Volltonfarbe

```
void SetColor(D2D1_COLOR_F color);
```

### <a name="parameters"></a>Parameter

*color*<br/>
Die Farbe des dieser Pinsel mit Volltonfarbe

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
