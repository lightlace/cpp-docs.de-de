---
title: CDCRenderTarget-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 70169d2b89d9ea657898f7a96dea27556023d4e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62168172"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget-Klasse

Ein Wrapper für ID2D1DCRenderTarget.

## <a name="syntax"></a>Syntax

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|Erstellt ein CDCRenderTarget-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDCRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern|
|[CDCRenderTarget::BindDC](#binddc)|Bindet das Renderziel auf den Gerätekontext, die an den sie zeichnen-Befehle ausgibt|
|[CDCRenderTarget::Create](#create)|Erstellt einen CDCRenderTarget.|
|[CDCRenderTarget::Detach](#detach)|Trennt die Render-Ziel-Schnittstelle des Objekts|
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Gibt die ID2D1DCRenderTarget-Schnittstelle|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CDCRenderTarget::operator ID2D1DCRenderTarget*](#operator_id2d1dcrendertarget_star)|Gibt die ID2D1DCRenderTarget-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|Ein Zeiger auf ein ID2D1DCRenderTarget-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="attach"></a>  CDCRenderTarget::Attach

Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern

```
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>Parameter

*pTarget*<br/>
Vorhandene Render-Ziel-Schnittstelle. NULL darf nicht sein

##  <a name="binddc"></a>  CDCRenderTarget::BindDC

Bindet das Renderziel auf den Gerätekontext, die an den sie zeichnen-Befehle ausgibt

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*dc*<br/>
Der Gerätekontext, die an den das Renderziel zeichnen-Befehle ausgibt

*rect*<br/>
Die Dimensionen des Handles für einen Gerätekontext (HDC) an dem das Renderziel gebunden ist

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="cdcrendertarget"></a>  CDCRenderTarget::CDCRenderTarget

Erstellt ein CDCRenderTarget-Objekt.

```
CDCRenderTarget();
```

##  <a name="create"></a>  CDCRenderTarget::Create

Erstellt einen CDCRenderTarget.

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>Parameter

*props*<br/>
Der Renderingmodus, Pixelformat, Remotingoptionen, DPI-Informationen und die minimale DirectX-Unterstützung für das Hardwarerendering erforderlich.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="detach"></a>  CDCRenderTarget::Detach

Trennt die Render-Ziel-Schnittstelle des Objekts

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten rendern, Ziel-Schnittstelle.

##  <a name="getdcrendertarget"></a>  CDCRenderTarget::GetDCRenderTarget

Gibt die ID2D1DCRenderTarget-Schnittstelle

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1DCRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="m_pdcrendertarget"></a>  CDCRenderTarget::m_pDCRenderTarget

Ein Zeiger auf ein ID2D1DCRenderTarget-Objekt.

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

##  <a name="operator_id2d1dcrendertarget_star"></a>  CDCRenderTarget::operator ID2D1DCRenderTarget *

Gibt die ID2D1DCRenderTarget-Schnittstelle

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1DCRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
