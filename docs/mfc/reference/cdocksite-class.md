---
title: CDockSite Class
ms.date: 10/18/2018
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
ms.openlocfilehash: 9c154fe621fb88a6dc96a9835fae95c4b86763de
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866190"
---
# <a name="cdocksite-class"></a>CDockSite Class

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

Stellt eine Funktionalität bereit, mit der Bereiche, die von [CPane Class](../../mfc/reference/cpane-class.md) abgeleitet sind, in Zeilengruppen angeordnet werden können

## <a name="syntax"></a>Syntax

```
class CDockSite: public CBasePane
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDockSite::AddRow](#addrow)||
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(Überschreibt [cbasepane:: Anpassung dockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|
|[Cdocksite::-Layout](#adjustlayout)|(Überschreibt [cbasepane:: Anpassung Layout](../../mfc/reference/cbasepane-class.md#adjustlayout).)|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [cbasepane:: calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CDockSite::CanAcceptPane](#canacceptpane)|(Überschreibt [cbasepane:: canakzeptpane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|
|[CDockSite::CreateEx](#createex)|(Überschreibt [cbasepane:: deateex](../../mfc/reference/cbasepane-class.md#createex).)|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|(Überschreibt [cbasepane::D ockpane](../../mfc/reference/cbasepane-class.md#dockpane).)|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Überschreibt [cbasepane::D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(Überschreibt `CBasePane::IsAccessibilityCompatible`.)|
|[CDockSite::IsDragMode](#isdragmode)||
|[CDockSite::IsLastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[Cdocksite:: isresisierbar](#isresizable)|(Überschreibt [cbasepane:: isresisierbar](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[CDockSite::OnRemoveRow](#onremoverow)||
|[Cdocksite:: onresizerow](#onresizerow)||
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||
|[CDockSite::OnShowRow](#onshowrow)||
|[CDockSite::OnSizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|Gibt einen an der Dockposition angedockten Bereich anhand des angegebenen Parameters an einem bestimmten Punkt zurück.|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|
|[CDockSite::FindPaneByID](#findpanebyid)|Gibt den Bereich zurück, der anhand der angegebenen ID bestimmt wird.|
|[CDockSite::GetPaneList](#getpanelist)|Gibt eine Liste von Bereichen zurück, die an der Dockposition angedockt sind.|
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||
|[CDockSite::RemovePane](#removepane)||
|[CDockSite::RemoveRow](#removerow)||
|[CDockSite::ReplacePane](#replacepane)||
|[CDockSite::RepositionPanes](#repositionpanes)||
|[Cdocksite:: resizedocksite](#resizedocksite)||
|[Cdocksite:: resizerow](#resizerow)||
|[CDockSite::ShowPane](#showpane)|Zeigt den Bereich an.|
|[CDockSite::ShowRow](#showrow)||
|[CDockSite::SwapRows](#swaprows)||

## <a name="remarks"></a>Hinweise

Das Framework erstellt `CDockSite` Objekte automatisch, wenn [CFrameWndEx:: EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking)aufgerufen wird. Dockpositionsfenster werden am Rand des Clientbereichs des Hauptframefensters positioniert.

Normalerweise müssen Sie die Dienste, die von der Dock Site bereitgestellt werden, nicht anrufen, da diese Dienste von der [CFrameWndEx-Klasse](../../mfc/reference/cframewndex-class.md) verarbeitet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CDockSite`-Klasse erstellt wird.

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cbasepane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cdocksite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdocksite. h

##  <a name="addrow"></a>Cdocksite:: AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>Parameter

in *POS*<br/>

in *nheight*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="adjustdockinglayout"></a>Cdocksite:: Anpassungen dockinglayout

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>Hinweise

##  <a name="adjustlayout"></a>Cdocksite::-Layout

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Hinweise

##  <a name="aligndocksite"></a>Cdocksite:: aligndocksite

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>Parameter

in " *rectto alignby* "<br/>

in *rectresult*<br/>

in *bmuveimmediately*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="calcfixedlayout"></a>Cdocksite:: calcfixedlayout

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

##  <a name="canacceptpane"></a>Cdocksite:: canakzeptpane

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parameter

[in] *pBar*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="createex"></a>Cdocksite:: "forateex"

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    DWORD dwControlBarStyle,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Parameter

in *dwstyleex*<br/>

in *dwstyle*<br/>

in *Rect*<br/>

in *pparser*<br/>

in *dwcontrolbarstyle*<br/>

in *pContext*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="createrow"></a>Cdocksite:: kreaterow

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>Parameter

in *pparameentdockbar*<br/>

[in] *nOffset*<br/>

in *nrowheight*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="dockpane"></a>Cdocksite::D ockpane

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parameter

in *pwnd*<br/>

in *dockmethod*<br/>

in *lprect*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="dockpaneleftof"></a>Cdocksite::D ockpaneleftof

Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Parameter

*pBarToDock*<br/>
[in, out] Ein Zeiger auf den Bereich, der Links neben *ptargetbar*angedockt werden soll.

*pTargetBar*<br/>
[in, out] Ein Zeiger auf den Zielbereich.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Bereich erfolgreich angedockt ist. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="doesallowdyninsertbefore"></a>Cdocksite::D oesallowdyninsertbefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="findpanebyid"></a>Cdocksite:: findpanebyid

Gibt den Bereich mit der angegebenen ID zurück.

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
in Die Befehls-ID des Bereichs, der gefunden werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Bereich mit der angegebenen Befehls-ID oder NULL, wenn der Bereich nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

##  <a name="findrowindex"></a>Cdocksite:: findrowindex

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Parameter

in *Prow*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="fixupvirtualrects"></a>Cdocksite:: fixupvirtualrects

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Hinweise

##  <a name="getdocksiteid"></a>Cdocksite:: getdocksiteid

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getdocksiterowslist"></a>Cdocksite:: getdocksiterowslist

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getpanelist"></a>Cdocksite:: getpanelist

Gibt eine Liste der Bereiche zurück, die an der Dock Site angedockt sind.

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Schreib geschützter Verweis auf die Liste der Bereiche, die derzeit in der Andock Leiste angedockt sind.

##  <a name="isaccessibilitycompatible"></a>Cdocksite:: isaccessibilitycompatible

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isdragmode"></a>Cdocksite:: isdragmode

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="islastrow"></a>Cdocksite:: islastrow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>Parameter

in *Prow*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isrectwithindocksite"></a>Cdocksite:: isrectwithindocksite

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>Parameter

in *Rect*<br/>

[in] *ptDelta*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isresizable"></a>Cdocksite:: isresisierbar

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="movepane"></a>Cdocksite:: movepane

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>Parameter

in *pwnd*<br/>

in *nFlags*<br/>

[in] *ptOffset*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="oninsertrow"></a>Cdocksite:: oninsertrow

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>Parameter

in *POS*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onremoverow"></a>Cdocksite:: onremoverow

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>Parameter

in *POS*<br/>

[in] *bByShow*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onresizerow"></a>Cdocksite:: onresizerow

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>Parameter

in *prowtor esize*<br/>

[in] *nOffset*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onsizeparent"></a>Cdocksite:: onsizeparent

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>Parameter

in *rectavailable*<br/>

in *nside*<br/>

in *bexpand*<br/>

[in] *nOffset*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onsetwindowpos"></a>Cdocksite:: onsetwindowpos

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>Parameter

in *pwndinsertafter*<br/>

in Wiederholung<br/>

in *nFlags*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onshowrow"></a>Cdocksite:: onshowrow

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>Parameter

in *POS*<br/>

[in] *bShow*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="panefrompoint"></a>Cdocksite::P anefrompoint

Gibt einen an der Dockposition angedockten Bereich anhand des angegebenen Parameters an einem bestimmten Punkt zurück.

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
in Ein Punkt (in Bildschirm Koordinaten), für den der Bereich abgerufen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Bereich, der sich am angegebenen Punkt befindet, oder NULL, wenn am angegebenen Punkt kein Bereich vorhanden war.

### <a name="remarks"></a>Hinweise

##  <a name="rectsidefrompoint"></a>Cdocksite:: rectsidefrompoint

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>Parameter

in *Rect*<br/>

in *Punkt*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="removepane"></a>Cdocksite:: removepane

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

in *pwnd*<br/>

in *dockmethod*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="removerow"></a>Cdocksite:: removerow

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>Parameter

in *Prow*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="replacepane"></a>Cdocksite:: replacepane

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>Parameter

[in] *pOldBar*<br/>

in *pnewbar*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="repositionpanes"></a>Cdocksite:: repositionbereichs

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>Parameter

in *rectnewclientarea*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="resizedocksite"></a>Cdocksite:: resizedocksite

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>Parameter

in *nnewwidth*<br/>

in *nnetwheight*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="resizerow"></a>Cdocksite:: resizerow

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>Parameter

in *Prow*<br/>

in *nnewSize*<br/>

in *banpassungen-Layout*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="showpane"></a>Cdocksite:: ShowPane

Zeigt den Bereich an.

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
[in, out] Ein Zeiger auf den Bereich, der angezeigt oder ausgeblendet werden soll.

*bShow*<br/>
in TRUE, um anzugeben, dass der Bereich angezeigt werden soll. FALSE, um anzugeben, dass der Bereich ausgeblendet werden soll.

*bDelay*<br/>
in TRUE, um anzugeben, dass das Layout des Bereichs verzögert werden soll, bis der Bereich angezeigt wird. andernfalls false.

*bactivate*<br/>
in Dieser Parameter wird nicht verwendet.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Bereich erfolgreich angezeigt oder ausgeblendet wurde. FALSE, wenn der angegebene Bereich nicht zu dieser Dock Site gehört.

### <a name="remarks"></a>Hinweise

Ruft diese Methode auf, um angedockte Bereiche anzuzeigen oder auszublenden. Normalerweise müssen Sie nicht direkt aufrufen `CDockSite::ShowPane` , da es vom übergeordneten Rahmen Fenster oder vom Basisbereich aufgerufen wird.

##  <a name="showrow"></a>Cdocksite:: showrow

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>Parameter

in *Prow*<br/>

[in] *bShow*<br/>

in *banpassungen-Layout*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="swaprows"></a>Cdocksite:: swaprows

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>Parameter

in *Pfirsich Zeilen*<br/>

in *psecondrow*<br/>

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)
