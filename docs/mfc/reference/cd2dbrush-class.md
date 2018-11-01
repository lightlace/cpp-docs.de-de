---
title: CD2DBrush-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 9e0be4b3b4f39d8fcf32f713bc8765d1f344babe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517883"
---
# <a name="cd2dbrush-class"></a>CD2DBrush-Klasse

Ein Wrapper für ID2D1Brush.

## <a name="syntax"></a>Syntax

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Erstellt ein CD2DBrush-Objekt.|
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Brush-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|
|[CD2DBrush:: Destroy](#destroy)|Zerstört ein CD2DBrush-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DBrush::Detach](#detach)|Resource-Schnittstelle aus dem Objekt getrennt|
|[CD2DBrush::Get](#get)|Gibt die ID2D1Brush-Schnittstelle|
|[CD2DBrush::GetOpacity](#getopacity)|Ruft den Grad der Deckkraft dieses Pinsels|
|[CD2DBrush::GetTransform](#gettransform)|Ruft die aktuelle Transformation des Renderziels|
|[CD2DBrush::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DBrush::SetOpacity](#setopacity)|Legt den Grad der Deckkraft dieses Pinsels|
|[CD2DBrush::setTransform](#settransform)|Wendet die angegebene Transformation auf das Renderziel, und Ersetzen Sie dabei die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge ausgeführt wird, im Bereich der transformierten|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DBrush::Operator ID2D1Brush *](#operator_id2d1brush_star)|Gibt die ID2D1Brush-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DBrush::m_pBrush](#m_pbrush)|Speichert einen Zeiger auf ein ID2D1Brush-Objekt.|
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Pinseleigenschaften.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush

Der Destruktor. Wird aufgerufen, wenn ein D2D-Brush-Objekt zerstört wird.

```
virtual ~CD2DBrush();
```

##  <a name="attach"></a>  CD2DBrush::Attach

Fügt die vorhandene Ressourcenschnittstelle für das Objekt.

```
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>Parameter

*pResource*<br/>
Vorhandene Ressourcenschnittstelle. Darf nicht NULL sein.

##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush

Erstellt ein CD2DBrush-Objekt.

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*pBrushProperties*<br/>
Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="destroy"></a>  CD2DBrush:: Destroy

Zerstört ein CD2DBrush-Objekt.

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBrush::Detach

Trennt die Ressourcenschnittstelle des Objekts.

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten Resource-Schnittstelle.

##  <a name="get"></a>  CD2DBrush::Get

Gibt die ID2D1Brush-Schnittstelle

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1Brush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getopacity"></a>  CD2DBrush::GetOpacity

Ruft den Grad der Deckkraft dieses Pinsels

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert zwischen 0 und 1, der die Deckkraft des Pinsels angibt. Dieser Wert ist ein konstanter Multiplikator, der den Alphawert alle Pixel, die durch den Pinsel gefüllt linear skaliert wird. Im Bereich von 0 bis 1 werden die Deckkraftwerte gebunden sind, bevor sie miteinander multipliziert werden.

##  <a name="gettransform"></a>  CD2DBrush::GetTransform

Ruft die aktuelle Transformation des Renderziels

```
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>Parameter

*transform*<br/>
Wenn dieser zurückgegeben wird, enthält die aktuelle Transformation des Renderziels. Dieser Parameter wird nicht initialisiert übergeben.

##  <a name="isvalid"></a>  CD2DBrush::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush

Speichert einen Zeiger auf ein ID2D1Brush-Objekt.

```
ID2D1Brush* m_pBrush;
```

##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties

Pinseleigenschaften.

```
CD2DBrushProperties* m_pBrushProperties;
```

##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::Operator ID2D1Brush *

Gibt die ID2D1Brush-Schnittstelle

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1Brush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="setopacity"></a>  CD2DBrush::SetOpacity

Legt den Grad der Deckkraft dieses Pinsels

```
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>Parameter

*Deckkraft*<br/>
Ein Wert zwischen 0 und 1, der die Deckkraft des Pinsels angibt. Dieser Wert ist ein konstanter Multiplikator, der den Alphawert alle Pixel, die durch den Pinsel gefüllt linear skaliert wird. Im Bereich von 0 bis 1 werden die Deckkraftwerte gebunden sind, bevor sie miteinander multipliziert werden.

##  <a name="settransform"></a>  CD2DBrush::setTransform

Wendet die angegebene Transformation auf das Renderziel, und Ersetzen Sie dabei die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten in der transformierten Speicherplatz.

```
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>Parameter

*transform*<br/>
Die Transformation, die auf das Renderziel anwenden

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
