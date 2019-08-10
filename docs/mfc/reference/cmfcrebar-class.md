---
title: Cmatkrebar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
ms.openlocfilehash: ccd500547bdcf65e922f7b5e5ca8d30e0423933d
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866166"
---
# <a name="cmfcrebar-class"></a>Cmatkrebar-Klasse

Ein `CMFCReBar` -Objekt ist eine Steuerleiste, die Layout-, Persistenz-und Zustandsinformationen für Grund leisten-Steuerelemente bereitstellt.
Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.
## <a name="syntax"></a>Syntax

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCReBar::AddBar](#addbar)|Fügt ein Band zu einer Info Leiste hinzu.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::CanFloat](#canfloat)|(Überschreibt [cbasepane:: canfloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[Cmatkrebar:: Create](#create)|Erstellt das Grund leisten-Steuerelement und fügt es `CMFCReBar` an das-Objekt an.|
|[CMFCReBar::EnableDocking](#enabledocking)|(Überschreibt [cbasepane:: EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine " [krebarctrl](../../mfc/reference/crebarctrl-class.md) "-Steuerelement.|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Überschreibt [CPANE:: onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Überschreibt [CWnd:: ontoolhittest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [cbasepane:: OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Überschreibt [cbasepane:: setpanealignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Hinweise

Ein `CMFCReBar` -Objekt kann eine Vielzahl untergeordneter Fenster enthalten. Dies schließt Bearbeitungsfelder, Symbolleisten und Listenfelder ein. Sie können die Größe der Info Leiste Programm gesteuert ändern, oder der Benutzer kann die Größe der Info Leiste manuell ändern, indem er seine Zieh Punkt Leiste zieht. Sie können auch den Hintergrund eines Grund leisten-Objekts auf eine Bitmap Ihrer Wahl festlegen.

Ein Grund leisten-Objekt verhält sich ähnlich wie ein Toolbar-Objekt. Ein Grund leisten-Steuerelement kann ein oder mehrere Bänder enthalten, und jedes Band kann eine Zieh Punkt Leiste, eine Bitmap, eine Text Bezeichnung und ein untergeordnetes Fenster enthalten.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCReBar` -Klasse. Das Beispiel zeigt, wie Sie ein Grund leisten-Steuerelement erstellen und diesem ein Band hinzufügen. Das Band fungiert als interne Symbolleiste. Dieser Code Ausschnitt ist Teil des Info leisten- [Test](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cbasepane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPANE](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMF-Leiste](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrebar. h

##  <a name="addbar"></a>CMF-Leiste:: addbar

Fügt ein Band zu einer Info Leiste hinzu.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
[in, out] Ein Zeiger auf das untergeordnete Fenster, das in die Info Leiste eingefügt werden soll. Das Objekt, auf das verwiesen wird, muss über das Fenster **WS_CHILD** verfügen.

*pszText*<br/>
in Gibt den Text an, der auf der Info Leiste angezeigt werden soll. Der Text ist nicht Teil des untergeordneten Fensters. Stattdessen wird er auf der Info Leiste angezeigt.

*pbmp*<br/>
[in, out] Gibt die Bitmap an, die auf dem Hintergrund der Info Leiste angezeigt werden soll.

*dwStyle*<br/>
in Enthält den Stil, der auf das Band angewendet werden soll. Eine komplette Liste der Band Stile finden Sie in der Beschreibung für `fStyle` in der [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) -Struktur in der Windows SDK-Dokumentation.

*clrFore*<br/>
in Stellt die Vordergrundfarbe der Info Leiste dar.

*clrBack*<br/>
in Stellt die Hintergrundfarbe der Info Leiste dar.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Band erfolgreich der Info Leiste hinzugefügt wurde. andernfalls false.

##  <a name="create"></a>Cmatkrebar:: Create

Erstellt das Grund leisten-Steuerelement und fügt es an das [cmfkrebar](../../mfc/reference/cmfcrebar-class.md) -Objekt an.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
[in, out] Ein Zeiger auf das übergeordnete Fenster dieses Grund leisten-Steuer Elements.

*dwCtrlStyle*<br/>
in Gibt den Stil für das Grund leisten-Steuerelement an. Der Standardformat Wert ist **RBS_BANDBORDERS**, in dem schmale Linien angezeigt werden, um angrenzende Bänder im Info leisten-Steuerelement voneinander zu trennen. Eine Liste gültiger Stile finden Sie Untergrund leisten- [Steuerelement Stile](/windows/desktop/Controls/rebar-control-styles) in der Windows SDK-Dokumentation.

*dwStyle*<br/>
in Der Fenster Stil des Grund leisten-Steuer Elements. Eine Liste gültiger Stile finden Sie unter [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
in Die ID des untergeordneten Fensters der Info Leiste.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Info Leiste erfolgreich erstellt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="getrebarctrl"></a>Cmberkrebar:: GetReBarCtrl

Bietet direkten Zugriff auf `CReBarCtrl` das zugrunde liegende allgemeine Steuer `CMFCReBar` Element für-Objekte.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das zugrunde `CReBarCtrl` liegende-Objekt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die gemeinsame Steuerung von Windows-Funktionen beim Anpassen der Info Leiste zu nutzen.

##  <a name="calcfixedlayout"></a>Cmatkrebar:: calcfixedlayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

in *bstretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="canfloat"></a>CMF-Leiste:: canfloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="enabledocking"></a>Cmatkrebar:: EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parameter

in *dwdockstyle*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="getrebarbandinfosize"></a>Cmberkrebar:: getrebarbandinfosize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onshowcontrolbarmenu"></a>Cmberkrebar:: onshowcontrolbarmenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parameter

in *CPoint*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ontoolhittest"></a>CMF-Leiste:: ontoolhittest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parameter

in *Punkt*<br/>
[in] *pTI*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onupdatecmdui"></a>CMF-Leiste:: OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parameter

in *pTARGET*<br/>
in *bdisableifnohndler*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setpanealignment"></a>Cmatkrebar:: setpanealignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parameter

in *dwalignment*<br/>

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl-Klasse](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane-Klasse](../../mfc/reference/cpane-class.md)
