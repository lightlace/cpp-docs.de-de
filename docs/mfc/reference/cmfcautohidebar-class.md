---
title: CMFCAutoHideBar-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a029bb2e2cd231d4a1c19bfcc5c7981cfd7f39b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054968"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar-Klasse

Die `CMFCAutoHideBar`-Klasse ist eine besondere Symbolleistenklasse, die die Funktion „Automatisch im Hintergrund“ implementiert.

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

## <a name="syntax"></a>Syntax

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Überschreibt `CPane::AllowShowOnPaneMenu`.)|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCAutoHideBar::Create](#create)|Erstellt eine Steuerleiste und fügt es der [CPane](../../mfc/reference/cpane-class.md) Objekt. (Überschreibt [cpane:: Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird. (Überschreibt [cpane:: Onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(Überschreibt [cpane:: Setactiveingroup](../../mfc/reference/cpane-class.md#setactiveingroup).)|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|Streckt einen Bereich vertikal oder horizontal. (Überschreibt [cbasepane:: Stretchpane](../../mfc/reference/cbasepane-class.md#stretchpane).)|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|Die zeitliche Verzögerung zwischen dem Zeitpunkt, wenn der Benutzer den Cursor über platziert, einem [CMFCAutoHideButton-Klasse](../../mfc/reference/cmfcautohidebutton-class.md) und dem Zeitpunkt, wenn das Framework das zugeordnete Fenster anzeigt.|

## <a name="remarks"></a>Hinweise

Wenn der Benutzer für einen Dockbereich den Modus „Automatisches Ausblenden“ auswählt, erstellt das Framework automatisch ein `CMFCAutoHideBar`-Objekt. Es erstellt außerdem die erforderlichen [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) und [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) Objekte. Jedes `CAutoHideDockSite`-Objekt bezieht sich auf ein einzelne `CMFCAutoHideButton`.

Die `CMFCAutoHideBar`-Klasse implementiert die Anzeige einer `CAutoHideDockSite`, wenn ein Benutzer die Maus über eine `CMFCAutoHideButton` bewegt. Wenn die Symbolleiste eine WM_MOUSEMOVE-Meldung empfängt, startet `CMFCAutoHideBar` einen Zeitgeber. Wenn der Zeitgeber fertig ist, sendet er eine WM_TIMER-Ereignisbenachrichtigung an die Symbolleiste. Die Symbolleiste verarbeitet dieses Ereignis, indem geprüft wird, ob sich der Mauszeiger über der gleichen automatisch ausblendbaren Schaltfläche befindet, über der er sich befand, als der Zeitgeber gestartet wurde. Wenn dies der Fall ist, wird die angehängte `CAutoHideDockSite` angezeigt.

Sie können die Länge der Verzögerung für den Zeitgeber durch Festlegen von `m_nShowAHWndDelay` steuern. Der Standardwert ist 400 ms.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAutoHideBar`-Objekts und die Verwendung der `GetDockSiteRow`-Methode.

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxautohidebar.h

## <a name="addautohidewindow"></a>  CMFCAutoHideBar::AddAutoHideWindow

Fügt einem `CDockablePane` .Fenster Funktionalität hinzu, die ihm automatisches Ausblenden ermöglicht.

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parameter

*pAutoHideWnd*<br/>
[in] Das Fenster, das Sie ausblenden möchten.

*dwAlignment*<br/>
[in] Ein Wert, der die Ausrichtung der automatisch ausblendbaren Schaltfläche an das Anwendungsfenster angibt.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Die *DwAlignment* Parameter gibt an, in dem die Schaltfläche "automatisch ausblenden" in der Anwendung befindet. Der Parameter kann auf einen der folgenden Werte festgelegt werden:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="allowshowonpanemenu"></a>  CMFCAutoHideBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="calcfixedlayout"></a>  CMFCAutoHideBar::CalcFixedLayout

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

## <a name="cmfcautohidebar"></a>  CMFCAutoHideBar::CMFCAutoHideBar

Erstellt ein CMFCAutoHideBar-Objekt.

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>Hinweise

## <a name="create"></a>  CMFCAutoHideBar::Create

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parameter

*"lpszclassname"*<br/>

*dwStyle*<br/>

*Rect*<br/>

*pParentWnd*<br/>

*nID*<br/>

*dwControlBarStyle*<br/>

*pContext*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="getfirstahwindow"></a>  CMFCAutoHideBar::GetFirstAHWindow

Gibt einen Zeiger auf das erste automatisch ausblendbare Fenster in der Anwendung zurück.

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>Rückgabewert

Das erste automatisch ausblendbare Fenster in der Anwendung oder NULL, wenn keines vorhanden ist.

### <a name="remarks"></a>Hinweise

## <a name="getvisiblecount"></a>  CMFCAutoHideBar::GetVisibleCount

Ruft die Anzahl der angezeigten automatisch ausblendbaren Schaltflächen ab.

```
int GetVisibleCount();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der angezeigten automatisch ausblendbaren Schaltflächen zurück.

### <a name="remarks"></a>Hinweise

## <a name="m_nshowahwnddelay"></a>  CMFCAutoHideBar::m_nShowAHWndDelay

Die zeitliche Verzögerung zwischen dem Zeitpunkt, wenn der Benutzer den Cursor über platziert, einem [CMFCAutoHideButton-Klasse](../../mfc/reference/cmfcautohidebutton-class.md) und dem Zeitpunkt, wenn das Framework das zugeordnete Fenster anzeigt.

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>Hinweise

Wenn der Benutzer platziert den Cursor über einem `CMFCAutoHideButton`, besteht eine geringfügige Verzögerung kommen, bevor das Framework das zugeordnete Fenster anzeigt. Dieser Parameter bestimmt die Länge der Verzögerung in Millisekunden.

## <a name="onshowcontrolbarmenu"></a>  CMFCAutoHideBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>Parameter

[in] *CPoint*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="removeautohidewindow"></a>  CMFCAutoHideBar::RemoveAutoHideWindow

Entfernt und zerstört das Automatisch-im-Hintergrund-Fenster.

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>Parameter

CDockablePane * *pAutoHideWnd* die automatisch ausblendbare Fenster entfernen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

## <a name="setactiveingroup"></a>  CMFCAutoHideBar::SetActiveInGroup

Kennzeichnet eine Automatisch-im-Hintergrund-Leiste als aktiv.

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>Parameter

[in] "Bool" *bActive* "true", die auf aktiv festzulegen; andernfalls "false".

### <a name="remarks"></a>Hinweise

Siehe [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup).

## <a name="setrecentvisiblestate"></a>  CMFCAutoHideBar::SetRecentVisibleState

```
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>Parameter

*bState*<br/>
[in] Zustand festlegen.

### <a name="remarks"></a>Hinweise

## <a name="showautohidewindow"></a>  CMFCAutoHideBar::ShowAutoHideWindow

Zeigt das automatisch ausblendbare Fenster an.

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Parameter

*pAutoHideWnd*<br/>
[in] Fenster angezeigt wird.

*bShow*<br/>
[in] "True" zum Anzeigen des Fensters.

*bDelay*<br/>
[in] Dieser Parameter wird ignoriert.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

## <a name="stretchpane"></a>  CMFCAutoHideBar::StretchPane

Ändert die Größe der automatisch ausblendbaren Leiste im reduzierten Zustand, um dem `CMFCAutoHideButton` -Objekt zu entsprechen.

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>Parameter

*nLength*<br/>
[in] Der Wert wird in der basisimplementierung nicht verwendet. Verwenden Sie diesen Wert in abgeleiteten Implementierungen, um die Länge des Bereichs mit der geänderten Größe anzuzeigen.

*bHoriz*<br/>
[in] Der Wert wird in der basisimplementierung nicht verwendet. Verwenden Sie in abgeleiteten Implementierungen "true" Handle der Fall, in dem die automatisch ausblendbare Leiste vertikal reduziert wird, und "false" für den Fall, in dem die automatisch ausblendbare Leiste horizontal reduziert wird.

### <a name="return-value"></a>Rückgabewert

Die resultierende Größe des Bereichs, dessen Größe geändert wurde.

### <a name="remarks"></a>Hinweise

Abgeleitete Klassen können diese Methode zum Anpassen des Verhaltens außer Kraft setzen.

## <a name="unsetautohidemode"></a>  CMFCAutoHideBar::UnSetAutoHideMode

Deaktiviert den automatischen Ausblendemodus für eine Gruppe von automatisch ausblendbaren Leisten.

```
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>Parameter

[in] pFirstBarInGroup ein Zeiger auf die erste automatisch ausblendbare Leiste in der Gruppe.

### <a name="remarks"></a>Hinweise

## <a name="updatevisiblestate"></a>  CMFCAutoHideBar::UpdateVisibleState

Wird vom Framework aufgerufen, wenn die automatisch ausblendbare Leiste neu gezeichnet werden muss.

```
void UpdateVisibleState();
```

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPane-Klasse](../../mfc/reference/cpane-class.md)<br/>
[CAutoHideDockSite-Klasse](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFCAutoHideButton-Klasse](../../mfc/reference/cmfcautohidebutton-class.md)
