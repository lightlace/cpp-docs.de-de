---
title: CBitmapRenderTarget-Klasse
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: ffead8d1f4a903fba79e4b22eefbf0a2955f56fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562239"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget-Klasse

Ein Wrapper für ID2D1BitmapRenderTarget.

## <a name="syntax"></a>Syntax

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Erstellt ein CBitmapRenderTarget-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBitmapRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern|
|[CBitmapRenderTarget::Detach](#detach)|Trennt die Render-Ziel-Schnittstelle des Objekts|
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Ruft die Bitmap für das Renderziel ab. Die zurückgegebene Bitmap kann für das Zeichnen von Vorgängen verwendet werden.|
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Gibt die ID2D1BitmapRenderTarget-Schnittstelle|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Gibt die ID2D1BitmapRenderTarget-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Ein Zeiger auf ein ID2D1BitmapRenderTarget-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="attach"></a>  CBitmapRenderTarget::Attach

Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern

```
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>Parameter

*pTarget*<br/>
Vorhandene Render-Ziel-Schnittstelle. NULL darf nicht sein

##  <a name="cbitmaprendertarget"></a>  CBitmapRenderTarget::CBitmapRenderTarget

Erstellt ein CBitmapRenderTarget-Objekt.

```
CBitmapRenderTarget();
```

##  <a name="detach"></a>  CBitmapRenderTarget::Detach

Trennt die Render-Ziel-Schnittstelle des Objekts

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten rendern, Ziel-Schnittstelle.

##  <a name="getbitmap"></a>  CBitmapRenderTarget::GetBitmap

Ruft die Bitmap für das Renderziel ab. Die zurückgegebene Bitmap kann für das Zeichnen von Vorgängen verwendet werden.

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>Parameter

*Bitmap*<br/>
Bei der Rückgabe dieser Methode enthält die gültigen Bitmap für das Renderziel. Diese Bitmap kann für das Zeichnen von Vorgängen verwendet werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="getbitmaprendertarget"></a>  CBitmapRenderTarget::GetBitmapRenderTarget

Gibt die ID2D1BitmapRenderTarget-Schnittstelle

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1BitmapRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="m_pbitmaprendertarget"></a>  CBitmapRenderTarget::m_pBitmapRenderTarget

Ein Zeiger auf ein ID2D1BitmapRenderTarget-Objekt.

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

##  <a name="operator_id2d1bitmaprendertarget_star"></a>  CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *

Gibt die ID2D1BitmapRenderTarget-Schnittstelle

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1BitmapRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
