---
title: CDockSite-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockSite
dev_langs:
- C++
helpviewer_keywords:
- CDockSite class
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3b230542bface4d729866c37dc4c74cb0173b389
ms.lasthandoff: 02/24/2017

---
# <a name="cdocksite-class"></a>CDockSite Class
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Stellt Funktionen für das Anordnen von Bereichen, die von abgeleitet sind die [CPane-Klasse](../../mfc/reference/cpane-class.md) in Zeilengruppen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockSite: public CBasePane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockSite::AddRow](#addrow)||  
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(Überschreibt [CBasePane::AdjustDockingLayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|  
|[CDockSite::AdjustLayout](#adjustlayout)|(Überschreibt [CBasePane::AdjustLayout](../../mfc/reference/cbasepane-class.md#adjustlayout).)|  
|[CDockSite::AlignDockSite](#aligndocksite)||  
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(Überschreibt [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CDockSite::CanAcceptPane](#canacceptpane)|(Überschreibt [CBasePane::CanAcceptPane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|  
|[CDockSite::CreateEx](#createex)|(Überschreibt [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|  
|[CDockSite::CreateRow](#createrow)||  
|[CDockSite::DockPane](#dockpane)|(Überschreibt [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane).)|  
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Überschreibt [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CDockSite::FindRowIndex](#findrowindex)||  
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||  
|[CDockSite::GetDockSiteID](#getdocksiteid)||  
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||  
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(Überschreibt `CBasePane::IsAccessibilityCompatible`.)|  
|[CDockSite::IsDragMode](#isdragmode)||  
|[CDockSite::IsLastRow](#islastrow)||  
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||  
|[CDockSite::IsResizable](#isresizable)|(Überschreibt [CBasePane::IsResizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CDockSite::MovePane](#movepane)||  
|[CDockSite::OnInsertRow](#oninsertrow)||  
|[CDockSite::OnRemoveRow](#onremoverow)||  
|[CDockSite::OnResizeRow](#onresizerow)||  
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
|[CDockSite::ResizeDockSite](#resizedocksite)||  
|[CDockSite::ResizeRow](#resizerow)||  
|[CDockSite::ShowPane](#showpane)|Zeigt den Bereich an.|  
|[CDockSite::ShowRow](#showrow)||  
|[CDockSite::SwapRows](#swaprows)||  
  
## <a name="remarks"></a>Hinweise  
 Das Framework erstellt `CDockSite` Objekte automatisch beim Aufruf von [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Dockpositionsfenster werden am Rand des Clientbereichs des Hauptframefensters positioniert.  
  
 Sie in der Regel keinen zum Aufrufen der Dienste, die von der Dock-Website bereitgestellt werden, da [CFrameWndEx Klasse](../../mfc/reference/cframewndex-class.md) behandelt diese Dienste.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CDockSite`-Klasse erstellt wird.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#27;](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockSite.h  
  
##  <a name="a-nameaddrowa--cdocksiteaddrow"></a><a name="addrow"></a>CDockSite::AddRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CDockingPanesRow* AddRow(
    POSITION pos,  
    int nHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pos`  
 [in] `nHeight`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameadjustdockinglayouta--cdocksiteadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockSite::AdjustDockingLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustDockingLayout();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameadjustlayouta--cdocksiteadjustlayout"></a><a name="adjustlayout"></a>CDockSite::AdjustLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namealigndocksitea--cdocksitealigndocksite"></a><a name="aligndocksite"></a>CDockSite::AlignDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AlignDockSite(
    const CRect& rectToAlignBy,  
    CRect& rectResult,  
    BOOL bMoveImmediately);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectToAlignBy`  
 [in] `rectResult`  
 [in] `bMoveImmediately`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecalcfixedlayouta--cdocksitecalcfixedlayout"></a><a name="calcfixedlayout"></a>CDockSite::CalcFixedLayout  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecanacceptpanea--cdocksitecanacceptpane"></a><a name="canacceptpane"></a>CDockSite::CanAcceptPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreateexa--cdocksitecreateex"></a><a name="createex"></a>CDockSite::CreateEx  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [in] `dwStyleEx`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `dwControlBarStyle`  
 [in] `pContext`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecreaterowa--cdocksitecreaterow"></a><a name="createrow"></a>CDockSite::CreateRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,  
    int nOffset,  
    int nRowHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentDockBar`  
 [in] `nOffset`  
 [in] `nRowHeight`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedockpanea--cdocksitedockpane"></a><a name="dockpane"></a>CDockSite::DockPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 [in] `dockMethod`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedockpaneleftofa--cdocksitedockpaneleftof"></a><a name="dockpaneleftof"></a>CDockSite::DockPaneLeftOf  
 Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.  
  
```  
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pBarToDock`  
 Ein Zeiger auf den Bereich links angedockt werden `pTargetBar`.  
  
 [in] [out]`pTargetBar`  
 Ein Zeiger auf den Zielbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt ist andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedoesallowdyninsertbeforea--cdocksitedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CDockSite::DoesAllowDynInsertBefore  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefindpanebyida--cdocksitefindpanebyid"></a><a name="findpanebyid"></a>CDockSite::FindPaneByID  
 Gibt den Bereich mit der angegebenen ID zurück  
  
```  
CPane* FindPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Befehls-ID des Bereichs befinden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich mit der angegebenen Befehls-ID oder `NULL` , wenn der Bereich nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefindrowindexa--cdocksitefindrowindex"></a><a name="findrowindex"></a>CDockSite::FindRowIndex  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int FindRowIndex(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRow`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefixupvirtualrectsa--cdocksitefixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockSite::FixupVirtualRects  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetdocksiteida--cdocksitegetdocksiteid"></a><a name="getdocksiteid"></a>CDockSite::GetDockSiteID  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual UINT GetDockSiteID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetdocksiterowslista--cdocksitegetdocksiterowslist"></a><a name="getdocksiterowslist"></a>CDockSite::GetDockSiteRowsList  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CObList& GetDockSiteRowsList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpanelista--cdocksitegetpanelist"></a><a name="getpanelist"></a>CDockSite::GetPaneList  
 Gibt eine Liste von Bereichen, die in der docksite angedockt sind.  
  
```  
const CObList& GetPaneList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein schreibgeschützter Verweis auf die Liste von Bereichen angedockt ist derzeit in der Dockingstation angezeigt.  
  
##  <a name="a-nameisaccessibilitycompatiblea--cdocksiteisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CDockSite::IsAccessibilityCompatible  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisdragmodea--cdocksiteisdragmode"></a><a name="isdragmode"></a>CDockSite::IsDragMode  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameislastrowa--cdocksiteislastrow"></a><a name="islastrow"></a>CDockSite::IsLastRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
bool IsLastRow(CDockingPanesRow* pRow) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRow`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisrectwithindocksitea--cdocksiteisrectwithindocksite"></a><a name="isrectwithindocksite"></a>CDockSite::IsRectWithinDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsRectWithinDockSite(
    CRect rect,  
    CPoint& ptDelta);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 [in] `ptDelta`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisresizablea--cdocksiteisresizable"></a><a name="isresizable"></a>CDockSite::IsResizable  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namemovepanea--cdocksitemovepane"></a><a name="movepane"></a>CDockSite::MovePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL MovePane(
    CPane* pWnd,  
    UINT nFlags,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 [in] `nFlags`  
 [in] `ptOffset`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameoninsertrowa--cdocksiteoninsertrow"></a><a name="oninsertrow"></a>CDockSite::OnInsertRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnInsertRow(POSITION pos);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pos`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonremoverowa--cdocksiteonremoverow"></a><a name="onremoverow"></a>CDockSite::OnRemoveRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnRemoveRow(
    POSITION pos,  
    BOOL bByShow = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pos`  
 [in] `bByShow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonresizerowa--cdocksiteonresizerow"></a><a name="onresizerow"></a>CDockSite::OnResizeRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRowToResize`  
 [in] `nOffset`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsizeparenta--cdocksiteonsizeparent"></a><a name="onsizeparent"></a>CDockSite::OnSizeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnSizeParent(
    CRect& rectAvailable,  
    UINT nSide,  
    BOOL bExpand,  
    int nOffset);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectAvailable`  
 [in] `nSide`  
 [in] `bExpand`  
 [in] `nOffset`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonsetwindowposa--cdocksiteonsetwindowpos"></a><a name="onsetwindowpos"></a>CDockSite::OnSetWindowPos  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,  
    const CRect& rectWnd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndInsertAfter`  
 [in] `rectWnd`  
 [in] `nFlags`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonshowrowa--cdocksiteonshowrow"></a><a name="onshowrow"></a>CDockSite::OnShowRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnShowRow(
    POSITION pos,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pos`  
 [in] `bShow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namepanefrompointa--cdocksitepanefrompoint"></a><a name="panefrompoint"></a>CDockSite::PaneFromPoint  
 Gibt einen an der Dockposition angedockten Bereich anhand des angegebenen Parameters an einem bestimmten Punkt zurück.  
  
```  
virtual CPane* PaneFromPoint(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Ein Punkt in Bildschirmkoordinaten für den Bereich abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich befindet sich am angegebenen Punkt oder `NULL` Wenn kein Bereich an der angegebenen Position vorhanden war.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namerectsidefrompointa--cdocksiterectsidefrompoint"></a><a name="rectsidefrompoint"></a>CDockSite::RectSideFromPoint  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
static int __stdcall RectSideFromPoint(
    const CRect& rect,  
    const CPoint& point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 [in] `point`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremovepanea--cdocksiteremovepane"></a><a name="removepane"></a>CDockSite::RemovePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RemovePane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 [in] `dockMethod`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremoverowa--cdocksiteremoverow"></a><a name="removerow"></a>CDockSite::RemoveRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void RemoveRow(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namereplacepanea--cdocksitereplacepane"></a><a name="replacepane"></a>CDockSite::ReplacePane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL ReplacePane(
    CPane* pOldBar,  
    CPane* pNewBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOldBar`  
 [in] `pNewBar`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namerepositionpanesa--cdocksiterepositionpanes"></a><a name="repositionpanes"></a>CDockSite::RepositionPanes  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectNewClientArea`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameresizedocksitea--cdocksiteresizedocksite"></a><a name="resizedocksite"></a>CDockSite::ResizeDockSite  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ResizeDockSite(
    int nNewWidth,  
    int nNewHeight);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nNewWidth`  
 [in] `nNewHeight`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameresizerowa--cdocksiteresizerow"></a><a name="resizerow"></a>CDockSite::ResizeRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int ResizeRow(
    CDockingPanesRow* pRow,  
    int nNewSize,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRow`  
 [in] `nNewSize`  
 [in] `bAdjustLayout`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameshowpanea--cdocksiteshowpane"></a><a name="showpane"></a>CDockSite::ShowPane  
 Zeigt den Bereich an.  
  
```  
virtual BOOL ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pBar`  
 Ein Zeiger auf den Bereich, um angezeigt oder ausgeblendet werden.  
  
 [in] `bShow`  
 `TRUE`um anzugeben, dass der Bereich ist, angezeigt werden soll; `FALSE` angeben, dass der Bereich ausgeblendet werden.  
  
 [in] `bDelay`  
 `TRUE`um anzugeben, dass das Layout der im Bereich verzögert werden soll, erst nach dem Bereich angezeigt. andernfalls `FALSE`.  
  
 [in] `bActivate`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn im Bereich angezeigt oder ausgeblendet erfolgreich. `FALSE`Wenn im angegebene Bereich nicht auf dieser Website Andocken gehört.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum ein- oder Ausblenden der angedockten Bereiche. Normalerweise, Sie müssen nicht aufrufen `CDockSite::ShowPane` direkt, da sie von der übergeordneten Rahmenfensters oder Bereich Basis aufgerufen wird.  
  
##  <a name="a-nameshowrowa--cdocksiteshowrow"></a><a name="showrow"></a>CDockSite::ShowRow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void ShowRow(
    CDockingPanesRow* pRow,  
    BOOL bShow,  
    BOOL bAdjustLayout);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRow`  
 [in] `bShow`  
 [in] `bAdjustLayout`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameswaprowsa--cdocksiteswaprows"></a><a name="swaprows"></a>CDockSite::SwapRows  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void SwapRows(
    CDockingPanesRow* pFirstRow,  
    CDockingPanesRow* pSecondRow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFirstRow`  
 [in] `pSecondRow`  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)

