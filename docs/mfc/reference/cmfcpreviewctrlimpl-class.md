---
title: CMFCPreviewCtrlImpl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
ms.openlocfilehash: f66ed8478023bd42e185da4f21740d1de2536140
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295746"
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl-Klasse

Diese Klasse implementiert ein Fenster, das auf ein Hostfenster, bereitgestellt von der Shell for Rich Preview platziert wird.

## <a name="syntax"></a>Syntax

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl](#dtor)|Destructs ein Vorschau-Control-Objekt.|
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|Erstellt ein Objekt der Preview-Steuerelement.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::Create](#create)|Überladen. Wird aufgerufen, von einem Rich Preview-Handler, der Windows-Fenster zu erstellen.|
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|Wird von einem Rich Preview-Handler aufgerufen, wenn es sich bei muss dieses Steuerelements zu zerstören.|
|[CMFCPreviewCtrlImpl::Focus](#focus)|Legt den Eingabefokus auf dieses Steuerelement.|
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|Gibt ein Dokument mit dieser Vorschau verbunden.|
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|Weist diesem Steuerelement neu zeichnet.|
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|Wird aufgerufen, durch den Vorschauhandler, um eine Beziehung zwischen der Implementierung des Dokuments und dem Vorschausteuerelement zu erstellen.|
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|Legt ein neues übergeordnetes Element für dieses Steuerelement fest.|
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|Wird aufgerufen, von einem Rich Preview-Handler beim Festlegen der visuellen Elemente des umfangreichen Vorschaufunktionen muss Inhalt.|
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|Legt ein neues umschließendes Rechteck für dieses Steuerelement fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|Vom Framework aufgerufen, die Vorschau zu rendern.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|Hintergrundfarbe des Vorschaufensters.|
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|Textfarbe des Vorschaufensters.|
|[CMFCPreviewCtrlImpl::m_font](#m_font)|Schriftart für Text in einem Vorschaufenster angezeigt.|
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|Ein Zeiger auf ein Dokument, dessen Inhalt in das Steuerelement in der Vorschau angezeigt wird.|

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl

Erstellt ein Objekt der Preview-Steuerelement.

### <a name="syntax"></a>Syntax

CMFCPreviewCtrlImpl();

## <a name="create"></a> CMFCPreviewCtrlImpl::Create

Überladen. Wird aufgerufen, von einem Rich Preview-Handler, der Windows-Fenster zu erstellen.

### <a name="syntax"></a>Syntax

```
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc
);
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc,
   CCreateContext* pContext
);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das Hostfenster, die von der Shell for Rich Preview bereitgestellt.

*prc*<br/>
Gibt an, die ursprüngliche Größe und Position des Fensters.

*pContext*<br/>
Ein Zeiger auf einen Kontext erstellen.

### <a name="return-value"></a>Rückgabewert

„True“, wenn die Erstellung erfolgreich war, andernfalls „false“.

## <a name="destroy"></a> CMFCPreviewCtrlImpl::Destroy

Wird von einem Rich Preview-Handler aufgerufen, wenn es sich bei muss dieses Steuerelements zu zerstören.

### <a name="syntax"></a>Syntax

```
virtual void Destroy();
```

## <a name="dopaint"></a> CMFCPreviewCtrlImpl::DoPaint

Vom Framework aufgerufen, die Vorschau zu rendern.

### <a name="syntax"></a>Syntax

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger auf einen Gerätekontext zum Zeichnen.

## <a name="focus"></a> CMFCPreviewCtrlImpl::Focus

Legt den Eingabefokus auf dieses Steuerelement.

### <a name="syntax"></a>Syntax

```
virtual void Focus();
```

## <a name="getdocument"></a> CMFCPreviewCtrlImpl::GetDocument

Gibt ein Dokument mit dieser Vorschau verbunden.

### <a name="syntax"></a>Syntax

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Dokument, in der Vorschau, deren Inhalt im Steuerelement angezeigt wird.

## <a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl::m_clrBackColor

Hintergrundfarbe des Vorschaufensters.

### <a name="syntax"></a>Syntax

```
COLORREF m_clrBackColor;
```

## <a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl::m_clrTextColor

Die Textfarbe des Vorschaufensters.

### <a name="syntax"></a>Syntax

```
COLORREF m_clrTextColor;
```

## <a name="m_font"></a> CMFCPreviewCtrlImpl::m_font Schriftart für Text in einem Vorschaufenster angezeigt.

### <a name="syntax"></a>Syntax

```
CFont m_font;
```

## <a name="m_pdocument"></a> CMFCPreviewCtrlImpl::m_pDocument

Ein Zeiger auf ein Dokument, dessen Inhalt in das Steuerelement in der Vorschau angezeigt wird.

### <a name="syntax"></a>Syntax

```
ATL::IDocument* m_pDocument;
```

## <a name="redraw"></a> CMFCPreviewCtrlImpl::Redraw

Weist diesem Steuerelement neu zeichnet.

### <a name="syntax"></a>Syntax

```
virtual void Redraw();
```

## <a name="setdocument"></a> CMFCPreviewCtrlImpl::SetDocument

Wird aufgerufen, durch den Vorschauhandler, um eine Beziehung zwischen der Implementierung des Dokuments und dem Vorschausteuerelement zu erstellen.

### <a name="syntax"></a>Syntax

```
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>Parameter

*pDocument*<br/>
Ein Zeiger auf die Implementierung des Dokuments.

## <a name="sethost"></a> CMFCPreviewCtrlImpl::SetHost

Legt ein neues übergeordnetes Element für dieses Steuerelement fest.

### <a name="syntax"></a>Syntax

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>Parameter

*hWndParent*<br/>
Ein Handle für das neue übergeordnete Fenster.

## <a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl::SetPreviewVisuals

Wird aufgerufen, von einem Rich Preview-Handler beim Festlegen der visuellen Elemente des umfangreichen Vorschaufunktionen muss Inhalt.

### <a name="syntax"></a>Syntax

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>Parameter

*clrBack*<br/>
Hintergrundfarbe des Vorschaufensters.

*clrText*<br/>
Textfarbe des Vorschaufensters.

*plf*<br/>
Schriftart für Text in einem Vorschaufenster angezeigt.

##  <a name="setrect"></a> CMFCPreviewCtrlImpl::SetRect

Legt ein neues umschließendes Rechteck für dieses Steuerelement fest.

### <a name="syntax"></a>Syntax

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>Parameter

*prc*<br/>
Gibt an, die neue Größe und Position des Steuerelements (Vorschau).

*bRedraw*<br/>
Gibt an, ob das Steuerelement neu gezeichnet werden muss.

### <a name="remarks"></a>Hinweise

In der Regel wird ein neues umschließendes Rechteck festgelegt, wenn es sich bei Steuerelement geändert wird.

## <a name="dtor"></a> CMFCPreviewCtrlImpl::~CMFCPreviewCtrlImpl

Destructs ein Vorschau-Control-Objekt.

### <a name="syntax"></a>Syntax

```
virtual ~CMFCPreviewCtrlImpl();
```
