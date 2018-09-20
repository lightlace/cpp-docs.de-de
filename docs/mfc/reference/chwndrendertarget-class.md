---
title: CHwndRenderTarget-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbbc8a6aa76cb5ebd6efe8f7bba231ad342067f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434987"
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget-Klasse

Ein Wrapper für ID2D1HwndRenderTarget.

## <a name="syntax"></a>Syntax

```
class CHwndRenderTarget : public CRenderTarget;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Erstellt ein Objekt CHwndRenderTarget von HWND.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHwndRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern|
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Gibt an, ob es sich bei okkludierte das HWND, das Renderziel zugeordnet ist.|
|[CHwndRenderTarget::Create](#create)|Erstellt ein Renderziel mit dem Fenster verknüpft ist|
|[CHwndRenderTarget::Detach](#detach)|Trennt die Render-Ziel-Schnittstelle des Objekts|
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Gibt das zugeordnete HWND-Renderziel.|
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Gibt die ID2D1HwndRenderTarget-Schnittstelle.|
|[CHwndRenderTarget::ReCreate](#recreate)|Ein Renderziel, die dem Fenster zugeordneten erstellt erneut|
|[CHwndRenderTarget::Resize](#resize)|Ändert die Größe des Renderziels in die angegebene Pixelgröße|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Gibt die ID2D1HwndRenderTarget-Schnittstelle.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Ein Zeiger auf ein ID2D1HwndRenderTarget-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="attach"></a>  CHwndRenderTarget::Attach

Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern

```
void Attach(ID2D1HwndRenderTarget* pTarget);
```

### <a name="parameters"></a>Parameter

*pTarget*<br/>
Vorhandene Render-Ziel-Schnittstelle. NULL darf nicht sein

##  <a name="checkwindowstate"></a>  CHwndRenderTarget::CheckWindowState

Gibt an, ob es sich bei okkludierte das HWND, das Renderziel zugeordnet ist.

```
D2D1_WINDOW_STATE CheckWindowState() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der angibt, ob das zugeordnete HWND-Renderziel okkludiert wird.

##  <a name="chwndrendertarget"></a>  CHwndRenderTarget::CHwndRenderTarget

Erstellt ein Objekt CHwndRenderTarget von HWND.

```
CHwndRenderTarget(HWND hwnd = NULL);
```

### <a name="parameters"></a>Parameter

*HWND*<br/>
Das HWND zugeordneten Renderziel

##  <a name="create"></a>  CHwndRenderTarget::Create

Erstellt ein Renderziel mit dem Fenster verknüpft ist

```
BOOL Create(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
Das HWND zugeordneten Renderziel

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird "false" zurückgegeben

##  <a name="detach"></a>  CHwndRenderTarget::Detach

Trennt die Render-Ziel-Schnittstelle des Objekts

```
ID2D1HwndRenderTarget* Detach();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf getrennten rendern, Ziel-Schnittstelle.

##  <a name="gethwnd"></a>  CHwndRenderTarget::GetHwnd

Gibt das zugeordnete HWND-Renderziel.

```
HWND GetHwnd() const;
```

### <a name="return-value"></a>Rückgabewert

Das HWND zugeordneten Renderziel.

##  <a name="gethwndrendertarget"></a>  CHwndRenderTarget::GetHwndRenderTarget

Gibt die ID2D1HwndRenderTarget-Schnittstelle.

```
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1HwndRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="m_phwndrendertarget"></a>  CHwndRenderTarget::m_pHwndRenderTarget

Ein Zeiger auf ein ID2D1HwndRenderTarget-Objekt.

```
ID2D1HwndRenderTarget* m_pHwndRenderTarget;
```

##  <a name="operator_id2d1hwndrendertarget_star"></a>  CHwndRenderTarget::operator ID2D1HwndRenderTarget *

Gibt die ID2D1HwndRenderTarget-Schnittstelle.

```
operator ID2D1HwndRenderTarget*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine ID2D1HwndRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="recreate"></a>  CHwndRenderTarget::ReCreate

Ein Renderziel, die dem Fenster zugeordneten erstellt erneut

```
BOOL ReCreate(HWND hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
Das HWND zugeordneten Renderziel

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

##  <a name="resize"></a>  CHwndRenderTarget::Resize

Ändert die Größe des Renderziels in die angegebene Pixelgröße

```
BOOL Resize(const CD2DSizeU& size);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Die neue Größe des Renderziels in Pixeln

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird FALSE zurückgegeben.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
