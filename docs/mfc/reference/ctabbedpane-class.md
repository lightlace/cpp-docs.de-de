---
title: CTabbedPane-Klasse
ms.date: 11/04/2016
f1_keywords:
- CTabbedPane
- AFXTABBEDPANE/CTabbedPane
- AFXTABBEDPANE/CTabbedPane::DetachPane
- AFXTABBEDPANE/CTabbedPane::EnableTabAutoColor
- AFXTABBEDPANE/CTabbedPane::FloatTab
- AFXTABBEDPANE/CTabbedPane::GetTabArea
- AFXTABBEDPANE/CTabbedPane::GetTabWnd
- AFXTABBEDPANE/CTabbedPane::HasAutoHideMode
- AFXTABBEDPANE/CTabbedPane::IsTabLocationBottom
- AFXTABBEDPANE/CTabbedPane::ResetTabs
- AFXTABBEDPANE/CTabbedPane::SetTabAutoColors
- AFXTABBEDPANE/CTabbedPane::m_bTabsAlwaysTop
- AFXTABBEDPANE/CTabbedPane::m_pTabWndRTC
helpviewer_keywords:
- CTabbedPane [MFC], DetachPane
- CTabbedPane [MFC], EnableTabAutoColor
- CTabbedPane [MFC], FloatTab
- CTabbedPane [MFC], GetTabArea
- CTabbedPane [MFC], GetTabWnd
- CTabbedPane [MFC], HasAutoHideMode
- CTabbedPane [MFC], IsTabLocationBottom
- CTabbedPane [MFC], ResetTabs
- CTabbedPane [MFC], SetTabAutoColors
- CTabbedPane [MFC], m_bTabsAlwaysTop
- CTabbedPane [MFC], m_pTabWndRTC
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
ms.openlocfilehash: af9c65e51f7230b0fc6a59d0eed42eca08d24837
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263350"
---
# <a name="ctabbedpane-class"></a>CTabbedPane-Klasse

Implementiert die Funktionalität eines Bereichs mit abtrennbaren Registerkarten.

oder weitere Details anzuzeigen, die im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

## <a name="syntax"></a>Syntax

```
class CTabbedPane : public CBaseTabbedPane
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CTabbedPane::CTabbedPane`|Standardkonstruktor|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTabbedPane::DetachPane](#detachpane)|(Überschreibt [cbasetabbedpane:: Detachpane](../../mfc/reference/cbasetabbedpane-class.md#detachpane).)|
|[CTabbedPane::EnableTabAutoColor](#enabletabautocolor)|Aktiviert oder deaktiviert die automatische Registerkartenfärbung.|
|[CTabbedPane::FloatTab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet. (Overrides [CBaseTabbedPane::FloatTab](../../mfc/reference/cbasetabbedpane-class.md#floattab).)|
|[CTabbedPane::GetTabArea](#gettabarea)|Gibt die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zurück.|
|[CTabbedPane::GetTabWnd](#gettabwnd)||
|[CTabbedPane::HasAutoHideMode](#hasautohidemode)|Bestimmt, ob der Bereich im Registerkartenformat automatisch in den Hintergrundmodus gewechselt werden kann. (Überschreibt [cbasetabbedpane:: Hasautohidemode](../../mfc/reference/cbasetabbedpane-class.md#hasautohidemode).)|
|[CTabbedPane::IsTabLocationBottom](#istablocationbottom)|Bestimmt, ob sich die Registerkarten am unteren Rand des Fensters befinden.|
|[CTabbedPane::ResetTabs](#resettabs)|Setzt alle Bereiche im Registerkartenformat auf den Standardstatus zurück.|
|[CTabbedPane::SetTabAutoColors](#settabautocolors)|Legt eine Liste benutzerdefinierter Farben fest, die verwendet werden kann, wenn die Funktion für automatische Farben aktiviert ist.|

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CTabbedPane::m_bTabsAlwaysTop](#m_btabsalwaystop)|Die Standardposition für Registerkarten in der Anwendung.|
|[CTabbedPane::m_pTabWndRTC](#m_ptabwndrtc)|Laufzeitklasseninformationen für ein benutzerdefiniertes `CMFCTabCtrl`-abgeleitetes Objekt.|

## <a name="remarks"></a>Hinweise

Das Framework erstellt automatisch eine Instanz dieser Klasse, wenn ein Benutzer einen Bereich an einen anderen anfügt, indem es auf die Beschriftung des zweiten Bereichs verweist. Alle der vom Framework erstellten Bereiche im Registerkartenformat besitzen eine ID von "-1".

Um normale Registerkarten anstatt von Registerkarten von Outlook-Stil anzugeben, übergeben die AFX_CBRS_REGULAR_TABS Formatvorlage, die die [CDockablePane:: CreateEx](../../mfc/reference/cdockablepane-class.md#createex) Methode.

Wenn Sie einen Bereich im Registerkartenformat mit abtrennbaren Registerkarten erstellen, kann der Bereich automatisch durch das Framework zerstört werden. Speichern Sie daher nicht den Zeiger. Um einen Zeiger zum Bereich im Registerkartenformat zu erhalten, rufen Sie die `CBasePane::GetParentTabbedPane`-Methode auf.

## <a name="example"></a>Beispiel

In diesem Beispiel erstellen wir ein `CTabbedPane`-Objekt. Als Nächstes verwenden wir [cbasetabbedpane:: addTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) um zusätzliche Registerkarten anzufügen.

```cpp
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);

if (!pTabbededBar->Create (_T(""),
    this,
    CRect (0,
    0,
    200,
    200),
    TRUE,
    (UINT) -1,
    WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |
    WS_CLIPCHILDREN | CBRS_LEFT |
    CBRS_FLOAT_MULTI))
{
    TRACE0("Failed to create Solution Explorer bar\n");

    return FALSE;      // fail to create
}

pTabbededBar->AddTab (&m_wndClassView);
pTabbededBar->AddTab (&m_wndResourceView);

pTabbededBar->AddTab (&m_wndFileView);
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);

DockPane(pTabbededBar);
```

## <a name="example"></a>Beispiel

Eine weitere Möglichkeit zum Erstellen Sie ein Steuerleistenobjekt im Registerkartenformat ist die Verwendung [CDockablePane:: Attachtotabwnd](../../mfc/reference/cdockablepane-class.md#attachtotabwnd). Die `AttachToTabWnd` -Methode erstellt dynamisch ein Bereichsobjekt im Registerformat mithilfe von festgelegten laufzeitklasseninformationen [CDockablePane:: Settabbedpanertc](../../mfc/reference/cdockablepane-class.md#settabbedpanertc).

In diesem Beispiel erstellen wir einen dynamischen Bereich im Registerkartenformat, fügen zwei Registerkarten an und legen die zweite Registerkarte als nicht entfernbar fest.

```cpp
DockPane(&m_wndClassView);

CTabbedPane* pTabbedBar = NULL;
m_wndResourceView.AttachToTabWnd (&m_wndClassView,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

m_wndFileView.AttachToTabWnd (pTabbedBar,
    DM_SHOW,
    TRUE,
    (CDockablePane**) &pTabbedBar);

pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1,
    FALSE);
```

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)

[CTabbedPane](../../mfc/reference/ctabbedpane-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxTabbedPane.h

##  <a name="detachpane"></a>  CTabbedPane::DetachPane

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>

[in] *bHide*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="enabletabautocolor"></a>  CTabbedPane::EnableTabAutoColor

Aktiviert oder deaktiviert die automatische Registerkartenfärbung.

```
static void EnableTabAutoColor(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] True, um die automatische registerkartenfärbung zu aktivieren. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese statische Methode zum Aktivieren oder deaktivieren die automatische registerkartenfärbung in alle Bereiche, die in der Anwendung im Registerkartenformat. Wenn dieses Feature aktiviert ist, wird jede Registerkarte durch eine eigene Farbe gefüllt. Sie finden die Liste der Farben, die verwendet werden, um die Farbe der Registerkarten, die durch Aufrufen der [CMFCBaseTabCtrl::GetAutoColors](../../mfc/reference/cmfcbasetabctrl-class.md#getautocolors) Methode.

Sie können angeben, die Liste der Farben, die durch den Aufruf für Registerkarten verwendet werden [CTabbedPane::SetTabAutoColors](#settabautocolors).

Standardmäßig ist diese Option deaktiviert.

##  <a name="floattab"></a>  CTabbedPane::FloatTab

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>
[in] *nTabID*<br/>
[in] *DockMethod*<br/>
[in] *bHide*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="gettabarea"></a>  CTabbedPane::GetTabArea

Gibt die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zurück.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parameter

*rectTabAreaTop*<br/>
[out] Enthält die Größe und Position in Bildschirmkoordinaten der oberen Registerkarte-Bereich.

*rectTabAreaBottom*<br/>
[out] Enthält die Größe und Position des Registerkartenbereichs nach unten, in Bildschirmkoordinaten.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode, um zu bestimmen, wie einen Bereich anzudocken, den ein Benutzer gezogen wird. Wenn der Benutzer einen Bereich über den Registerkartenbereich der der Bereich "Ziel" zieht, versucht das Framework ab, fügen Sie es als eine neue Registerkarte, der den Bereich "Ziel". Andernfalls wird versucht, die im Bereich der Seite klicken Sie im Bereich "Ziel" angedockt und dazu erstellen einen neuen Container für den Bereich mit einen bereichsteiler, der zwischen den beiden Fenstern.

Überschreiben Sie diese Methode in einer `CTabbedPane`-abgeleitete Klasse, um dieses Verhalten zu ändern.

##  <a name="gettabwnd"></a>  CTabbedPane::GetTabWnd

```
CMFCTabCtrl* GetTabWnd() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="hasautohidemode"></a>  CTabbedPane::HasAutoHideMode

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="istablocationbottom"></a>  CTabbedPane::IsTabLocationBottom

Bestimmt, ob sich die Registerkarten am unteren Rand des Fensters befinden.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Registerkartenbereich am unteren Rand des Fensters im Registerkartenformat befindet. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="m_btabsalwaystop"></a>  CTabbedPane::m_bTabsAlwaysTop

Die Standardposition für Registerkarten in der Anwendung.

```
AFX_IMPORT_DATA static BOOL m_bTabsAlwaysTop;
```

### <a name="remarks"></a>Hinweise

Legen Sie dieses statische Element auf "true"-Force-alle Registerkarten in der Anwendung, die am oberen Rand der Seite im Registerformat angezeigt werden.

Sie müssen diesen Wert festlegen, bevor ein Fenster mit Registerkarten erstellt wurde.

Der Standardwert ist "false".

##  <a name="m_ptabwndrtc"></a>  CTabbedPane::m_pTabWndRTC

Laufzeitklasseninformationen für ein benutzerdefiniertes `CMFCTabCtrl`-abgeleitetes Objekt.

```
AFX_IMPORT_DATA static CRuntimeClass* m_pTabWndRTC;
```

### <a name="remarks"></a>Hinweise

Legen Sie die statischen Member-Variable auf einen Zeiger auf die laufzeitklasseninformationen der ein `CMFCTabCtrl`-abgeleitetes Objekt aus, wenn Sie ein benutzerdefiniertes Fenster im Registerkartenformat in einem Bereich im Registerkartenformat verwenden.

##  <a name="resettabs"></a>  CTabbedPane::ResetTabs

Setzt alle Bereiche im Registerkartenformat auf den Standardstatus zurück.

```
static void ResetTabs();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um alle Bereiche der im Registerkartenformat auf den Standardzustand zurückgesetzt. Wenn Sie aufgerufen wird, setzt diese Methode zurück, die Border-Größen und den Auto-farbenzustand von alle Bereiche im Registerkartenformat.

##  <a name="settabautocolors"></a>  CTabbedPane::SetTabAutoColors

Legt eine Liste der Farben, die verwendet werden, wenn die Funktion für automatische Farben aktiviert ist.

```
static void SetTabAutoColors(const CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Parameter

*arColors*<br/>
[in] Enthält das Array von Farben zu legen.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die Liste der Farben anzupassen, die verwendet werden, wenn die Funktion für automatische Farben aktiviert ist. Dies ist eine statische Funktion und wirkt sich auf Bereiche, die in Ihrer Anwendung alle im Registerkartenformat.

Verwendung [CTabbedPane::EnableTabAutoColor](#enabletabautocolor) aktivieren oder deaktivieren die Funktion für automatische Farben.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)<br/>
[CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)<br/>
[CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)
