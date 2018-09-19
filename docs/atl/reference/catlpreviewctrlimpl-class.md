---
title: CAtlPreviewCtrlImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Create
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Destroy
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Focus
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::OnPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::Redraw
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetHost
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetPreviewVisuals
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::SetRect
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::DoPaint
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_plf
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrBack
- ATLPREVIEWCTRLIMPL/ATL::CAtlPreviewCtrlImpl::m_clrText
dev_langs:
- C++
helpviewer_keywords:
- CAtlPreviewCtrlImpl class
ms.assetid: 39b3299e-07e4-4abc-9b6e-b54bfa3b0802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef1469c40de8aae06460f1874905c53e91a47ca1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079335"
---
# <a name="catlpreviewctrlimpl-class"></a>CAtlPreviewCtrlImpl-Klasse

Diese Klasse ist eine ATL-Implementierung eines Fensters, das auf ein Hostfenster, bereitgestellt von der Shell for Rich Preview eingefügt wird.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CAtlPreviewCtrlImpl : public CWindowImpl<CAtlPreviewCtrlImpl>, public IPreviewCtrl;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl](#dtor)|Destructs ein Vorschau-Control-Objekt.|
|[CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl](#catlpreviewctrlimpl)|Erstellt ein Objekt der Preview-Steuerelement.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::Create](#create)|Wird aufgerufen, von einem Rich Preview-Handler, der Windows-Fenster zu erstellen.|
|[CAtlPreviewCtrlImpl::Destroy](#destroy)|Wird von einem Rich Preview-Handler aufgerufen, wenn es sich bei muss dieses Steuerelements zu zerstören.|
|[CAtlPreviewCtrlImpl::Focus](#focus)|Legt den Eingabefokus auf dieses Steuerelement.|
|[CAtlPreviewCtrlImpl::OnPaint](#onpaint)|Verarbeitet die WM_PAINT-Meldung.|
|[CAtlPreviewCtrlImpl::Redraw](#redraw)|Weist diesem Steuerelement neu zeichnet.|
|[CAtlPreviewCtrlImpl::SetHost](#sethost)|Legt ein neues übergeordnetes Element für dieses Steuerelement fest.|
|[CAtlPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Wird aufgerufen, von einem Rich Preview-Handler beim Festlegen der visuellen Elemente des umfangreichen Vorschaufunktionen muss Inhalt.|
|[CAtlPreviewCtrlImpl::SetRect](#setrect)|Legt ein neues umschließendes Rechteck für dieses Steuerelement fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::DoPaint](#dopaint)|Vom Framework aufgerufen, die Vorschau zu rendern.|

### <a name="protected-constants"></a>Geschützte Konstanten

|name|Beschreibung|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_plf](#m_plf)|Schriftart für Text in einem Vorschaufenster angezeigt.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAtlPreviewCtrlImpl::m_clrBack](#m_clrback)|Hintergrundfarbe des Vorschaufensters.|
|[CAtlPreviewCtrlImpl::m_clrText](#m_clrtext)|Textfarbe des Vorschaufensters.|  

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`TBase`

`ATL::CMessageMap`

`ATL::CWindowImplRoot<TBase>`

`ATL::CWindowImplBaseT<TBase,TWinTraits>`

[ATL::CWindowImpl\<CAtlPreviewCtrlImpl >](../../atl/reference/cwindowimpl-class.md)

`IPreviewCtrl`

`ATL::CAtlPreviewCtrlImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlpreviewctrlimpl.h

##  <a name="catlpreviewctrlimpl"></a>  CAtlPreviewCtrlImpl::CAtlPreviewCtrlImpl

Erstellt ein Objekt der Preview-Steuerelement.

```
CAtlPreviewCtrlImpl(void) : m_clrText(0),
   m_clrBack(RGB(255, 255, 255)), m_plf(NULL);
```

### <a name="remarks"></a>Hinweise

##  <a name="dtor"></a>  CAtlPreviewCtrlImpl:: ~ CAtlPreviewCtrlImpl

Destructs ein Vorschau-Control-Objekt.

```
virtual ~CAtlPreviewCtrlImpl(void);
```

### <a name="remarks"></a>Hinweise

##  <a name="create"></a>  CAtlPreviewCtrlImpl::Create

Wird aufgerufen, von einem Rich Preview-Handler, der Windows-Fenster zu erstellen.

```
virtual BOOL Create(HWND hWndParent, const RECT* prc);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das Hostfenster, die von der Shell for Rich Preview bereitgestellt.

*Volksrepublik China*<br/>
Gibt an, die ursprüngliche Größe und Position des Fensters.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

##  <a name="destroy"></a>  CAtlPreviewCtrlImpl::Destroy

Wird von einem Rich Preview-Handler aufgerufen, wenn es sich bei muss dieses Steuerelements zu zerstören.

```
virtual void Destroy();
```

### <a name="remarks"></a>Hinweise

##  <a name="dopaint"></a>  CAtlPreviewCtrlImpl::DoPaint

Vom Framework aufgerufen, die Vorschau zu rendern.

```
virtual void DoPaint(HDC hdc);
```

### <a name="parameters"></a>Parameter

*hdc*<br/>
Ein Handle für einen Gerätekontext zum Zeichnen.

### <a name="remarks"></a>Hinweise

##  <a name="focus"></a>  CAtlPreviewCtrlImpl::Focus

Legt den Eingabefokus auf dieses Steuerelement.

```
virtual void Focus();
```

### <a name="remarks"></a>Hinweise

##  <a name="m_clrback"></a>  CAtlPreviewCtrlImpl::m_clrBack

Hintergrundfarbe des Vorschaufensters.

```
COLORREF m_clrBack;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_clrtext"></a>  CAtlPreviewCtrlImpl::m_clrText

Die Textfarbe des Vorschaufensters.

```
COLORREF m_clrText;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_plf"></a>  CAtlPreviewCtrlImpl::m_plf

Schriftart für Text in einem Vorschaufenster angezeigt.

```
const LOGFONTW* m_plf;
```

### <a name="remarks"></a>Hinweise

##  <a name="onpaint"></a>  CAtlPreviewCtrlImpl::OnPaint

Verarbeitet die WM_PAINT-Meldung.

```
LRESULT OnPaint(  
    UINT nMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parameter

*nMsg*<br/>
Legen Sie auf der WM_PAINT.

*wParam-Parameter*<br/>
Dieser Parameter wird nicht verwendet.

*lParam*<br/>
Dieser Parameter wird nicht verwendet.

*bHandled*<br/>
Wenn diese Funktion zurückkehrt, enthält es "true".

### <a name="return-value"></a>Rückgabewert

Gibt immer 0 zurück.

### <a name="remarks"></a>Hinweise

##  <a name="redraw"></a>  CAtlPreviewCtrlImpl::Redraw

Weist diesem Steuerelement neu zeichnet.

```
virtual void Redraw();
```

### <a name="remarks"></a>Hinweise

##  <a name="sethost"></a>  CAtlPreviewCtrlImpl::SetHost

Legt ein neues übergeordnetes Element für dieses Steuerelement fest.

```
virtual void SetHost(HWND hWndParent);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

##  <a name="setpreviewvisuals"></a>  CAtlPreviewCtrlImpl::SetPreviewVisuals

Wird aufgerufen, von einem Rich Preview-Handler beim Festlegen der visuellen Elemente des umfangreichen Vorschaufunktionen muss Inhalt.

```
virtual void SetPreviewVisuals(
    COLORREF clrBack,
    COLORREF clrText,
    const LOGFONTW* plf);
```

### <a name="parameters"></a>Parameter

*clrBack*<br/>
Hintergrundfarbe des Vorschaufensters.

*clrText*<br/>
Die Textfarbe des Vorschaufensters.

*PLF*<br/>
Schriftart für Text in einem Vorschaufenster angezeigt.

### <a name="remarks"></a>Hinweise

##  <a name="setrect"></a>  CAtlPreviewCtrlImpl::SetRect

Legt ein neues umschließendes Rechteck für dieses Steuerelement fest.

```
virtual void SetRect(const RECT* prc, BOOL bRedraw);
```

### <a name="parameters"></a>Parameter

*Volksrepublik China*<br/>
Gibt an, die neue Größe und Position des Steuerelements (Vorschau).

*bRedraw*<br/>
Gibt an, ob das Steuerelement neu gezeichnet werden muss.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
