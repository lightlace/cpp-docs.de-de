---
title: CMFCReBar-Klasse
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
ms.openlocfilehash: 7776bf504d502feee8ef51949b8adc8e44f94c8e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772292"
---
# <a name="cmfcrebar-class"></a>CMFCReBar-Klasse

Ein `CMFCReBar` Objekt ist eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.
Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.
## <a name="syntax"></a>Syntax

```
class CMFCReBar : public CPane
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCReBar::AddBar](#addbar)|Eine grundleiste wird ein Band hinzugefügt.|
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCReBar::CanFloat](#canfloat)|(Überschreibt [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CMFCReBar::Create](#create)|Erstellt das Grundleistensteuerelement, und fügt es der `CMFCReBar` Objekt.|
|[CMFCReBar::EnableDocking](#enabledocking)|(Überschreibt [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Bietet direkten Zugriff auf die zugrunde liegende [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Standardsteuerelements.|
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Überschreibt [cpane:: Onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Überschreibt [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Überschreibt [CBasePane::OnUpdateCmdUI](cbasepane-class.md).)|
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Überschreibt [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|

## <a name="remarks"></a>Hinweise

Ein `CMFCReBar` Objekt kann eine Vielzahl von untergeordneten Fenstern enthalten. Dies schließt Bearbeitungsfelder, Symbolleisten und Listenfelder. Sie können die Größe der Infoleiste programmgesteuert oder des Benutzers kann manuell grundleiste durch Ziehen der Ziehpunktleiste. Sie können auch den Hintergrund eines Grundleisten-Objekts in eine Bitmap Ihrer Wahl festlegen.

Einem Grundleisten-Objekt verhält sich ähnlich wie ein Symbolleistenobjekt. Einem Grundleisten-Steuerelement kann eine oder mehrere Bänder enthalten, und jedes Band kann eine Ziehpunktleiste, eine Bitmap, einer textbezeichnung und einem untergeordneten Fenster enthalten.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCReBar` -Klasse. Das Beispiel zeigt das Erstellen eines Grundleisten-Steuerelements, und fügen Sie ein Band hinzu. Das Band fungiert als eine interne-Symbolleiste. Dieser Codeausschnitt ist Teil der [Grundleisten-Testbeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRebar.h

##  <a name="addbar"></a>  CMFCReBar::AddBar

Eine grundleiste wird ein Band hinzugefügt.

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
[in, out] Ein Zeiger auf das untergeordnete Fenster, in die Infoleiste eingefügt werden soll. Das referenzierte Objekt müssen die **WS_CHILD** Fensterstil.

*pszText*<br/>
[in] Gibt den Text auf der grundleiste angezeigt werden. Der Text ist nicht Teil des untergeordneten Fensters. Stattdessen wird er auf sich selbst grundleiste angezeigt.

*pbmp*<br/>
[in, out] Gibt an, die Bitmap auf den Hintergrund der Infoleiste angezeigt werden.

*dwStyle*<br/>
[in] Enthält die Formatvorlage, die auf dem Band angewendet. Eine vollständige Liste der-Band-Formate, finden Sie in der Beschreibung für `fStyle` in die [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) Struktur in der Windows SDK-Dokumentation.

*clrFore*<br/>
[in] Stellt die Vordergrundfarbe der Infoleiste dar.

*clrBack*<br/>
[in] Stellt die Hintergrundfarbe der Infoleiste dar.

### <a name="return-value"></a>Rückgabewert

True, wenn das Band der Infoleiste wurde erfolgreich hinzugefügt wurde. andernfalls "false".

##  <a name="create"></a>  CMFCReBar::Create

Erstellt das Grundleistensteuerelement, und fügt es der [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) Objekt.

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
[in, out] Ein Zeiger auf das übergeordnete Fenster dieses Grundleisten-Steuerelements.

*dwCtrlStyle*<br/>
[in] Gibt den Stil für das Grundleistensteuerelement. Der Standardwert für das Format ist **RBS_BANDBORDERS**, zeigt Einschränken der Zeilen aus, um benachbarte Bänder für das Grundleistensteuerelement zu trennen. Eine Liste der gültigen Stile, finden Sie unter [Stile für Grundleisten-Steuerelemente](/windows/desktop/Controls/rebar-control-styles) in der Windows SDK-Dokumentation.

*dwStyle*<br/>
[in] Der Fensterstil des Infoleisten-Steuerelements. Eine Liste der gültigen Stile, finden Sie unter [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*nID*<br/>
[in] Die Infoleiste untergeordneten Fensters-ID.

### <a name="return-value"></a>Rückgabewert

True, wenn der Infoleiste wurde erfolgreich erstellt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl

Bietet direkten Zugriff auf `CReBarCtrl` das zugrunde liegende allgemeine Steuerelement für `CMFCReBar` Objekte.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die zugrunde liegende `CReBarCtrl` Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um Sie beim Anpassen Ihrer Infoleiste allgemeine Windows Grundleisten-Steuerelement-Funktionen nutzen.

##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

[in] *bStretch*<br/>
[in] *bHorz*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="canfloat"></a>  CMFCReBar::CanFloat

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parameter

[in] *dwDockStyle*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize

```
UINT GetReBarBandInfoSize() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parameter

[in] *CPoint*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parameter

[in] *point*<br/>
[in] *pTI*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parameter

[in] *pTarget*<br/>
[in] *bDisableIfNoHndler*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>Parameter

[in] *DwAlignment*<br/>

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CReBarCtrl-Klasse](../../mfc/reference/crebarctrl-class.md)<br/>
[CPane-Klasse](../../mfc/reference/cpane-class.md)
