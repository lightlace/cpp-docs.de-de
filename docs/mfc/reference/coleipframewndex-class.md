---
title: Klasse COleIPFrameWndEx | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AdjustDockingLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPaneLeftOf
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableAutoHidePanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableDocking
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnablePaneMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetActivePopup
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetContainerFrameWindow
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDefaultResId
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockingManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMainFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMenuBar
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetTearOffBars
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetToolbarButtonToolTipText
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InsertPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsMenuBarAvailable
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsPointNearDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::LoadFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseDockingPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnClosePopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCmdMsg
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuImage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuLogo
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMenuButtonToolHitTest
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMoveMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnSetPreviewMode
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowCustomizePane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnTearOffMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PaneFromPoint
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PreTranslateMessage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RecalcLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RemovePaneFromDockManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetDockState
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetupToolbarMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::ShowPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::WinHelpA
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InitUserToobars
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWndEx class
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5eec8e3a9cc4ad71a1ee3de9f6d5f25cffef1242
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx-Klasse
Die Klasse `COleIPFrameWndEx` implementiert einen OLE-Container, der MFC unterstützt. Leiten Sie die direkte Rahmenfenster (Klasse) für die Anwendung aus der `COleIPFrameWndEx` -Klasse, nicht von der [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)Klasse. 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>Syntax  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleIPFrameWndEx::AddDockSite](#adddocksite)||  
|[COleIPFrameWndEx::AddPane](#addpane)||  
|[COleIPFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)||  
|[COleIPFrameWndEx::DockPane](#dockpane)||  
|[COleIPFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)||  
|[COleIPFrameWndEx::EnableDocking](#enabledocking)||  
|[COleIPFrameWndEx::EnablePaneMenu](#enablepanemenu)||  
|[COleIPFrameWndEx::GetActivePopup](#getactivepopup)|Gibt einen Zeiger auf das aktuell angezeigte Popupmenü zurück.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](#getcontainerframewindow)||  
|[COleIPFrameWndEx::GetDefaultResId](#getdefaultresid)|Gibt die Ressourcen-ID des Rahmenfensters zurück, die Sie beim Laden des Fensters angegeben haben.|  
|[COleIPFrameWndEx::GetDockFrame](#getdockframe)||  
|[COleIPFrameWndEx::GetDockingManager](#getdockingmanager)||  
|[COleIPFrameWndEx::GetMainFrame](#getmainframe)||  
|[COleIPFrameWndEx::GetMenuBar](#getmenubar)|Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.|  
|[COleIPFrameWndEx::GetPane](#getpane)||  
|[COleIPFrameWndEx::GetTearOffBars](#gettearoffbars)|Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|Wird vom Framework aufgerufen, bevor die QuickInfo für die Schaltfläche angezeigt wird.|  
|[COleIPFrameWndEx::InsertPane](#insertpane)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|Ermittelt, ob der Zeiger auf das Menüleistenobjekt nicht `NULL`ist.|  
|[COleIPFrameWndEx::IsPointNearDockSite](#ispointneardocksite)||  
|[COleIPFrameWndEx::LoadFrame](#loadframe)|(Überschreibt `COleIPFrameWnd::LoadFrame`.)|  
|[COleIPFrameWndEx::OnCloseDockingPane](#onclosedockingpane)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)||  
|[COleIPFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.|  
|[COleIPFrameWndEx::OnCmdMsg](#oncmdmsg)|(Überschreibt `CFrameWnd::OnCmdMsg`.)|  
|[COleIPFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|Wird vom Framework aufgerufen, wenn das einem Menüelement zugeordnete Bild gezeichnet wird.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Aufgerufen, wenn ein [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)Objekt eine WM_PAINT-Meldung verarbeitet.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Aufgerufen, wenn ein [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)Objekt verarbeitet WM_NCHITTEST Nachricht.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)||  
|[COleIPFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|Rufen Sie diese Memberfunktion auf, um für das Hauptrahmenfenster den Seitenansichtmodus zu aktivieren oder zu deaktivieren. (Überschreibt [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode).)|  
|[COleIPFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)||  
|[COleIPFrameWndEx::OnShowPanes](#onshowpanes)||  
|[COleIPFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|Wird vom Framework aufgerufen, wenn ein Popupmenü aktiviert wird.|  
|[COleIPFrameWndEx::OnTearOffMenu](#ontearoffmenu)|Wird vom Framework aufgerufen, wenn ein Menü mit abtrennbarer Leiste aktiviert wird.|  
|[COleIPFrameWndEx::PaneFromPoint](#panefrompoint)||  
|[COleIPFrameWndEx::PreTranslateMessage](#pretranslatemessage)|(Überschreibt `COleIPFrameWnd::PreTranslateMessage`.)|  
|[COleIPFrameWndEx::RecalcLayout](#recalclayout)|(Überschreibt `COleIPFrameWnd::RecalcLayout`.)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)||  
|[COleIPFrameWndEx::SetDockState](#setdockstate)|Wendet den angegebenen Andockstatus auf Bereiche an, die zum Rahmenfenster gehören.|  
|[COleIPFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|Ändert ein Symbolleistenobjekt durch die Suche nach Dummy-Elementen und durch das anschließende Ersetzen dieser Dummy-Elemente durch die angegebenen benutzerdefinierten Elemente.|  
|[COleIPFrameWndEx::ShowPane](#showpane)||  
|[COleIPFrameWndEx::WinHelpA](#winhelpa)|Wird vom Framework aufgerufen, um die WinHelp-Anwendung oder die Kontexthilfe zu initiieren.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleIPFrameWndEx::InitUserToobars](#initusertoobars)|Weist das Framework an, einen Bereich von Steuerelement-IDs zu initialisieren, die benutzerdefinierten Symbolleisten zugeordnet sind.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie für eine Instanz der `COleIPFrameWndEx` -Klasse eine Unterklasse erstellen und deren Methoden außer Kraft setzen. Das Beispiel veranschaulicht, wie die Methoden `OnDestory` , `RepositionFrame` , `RecalcLayout` und `CalcWindowRect` außer Kraft gesetzt werden. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#1;](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxoleipframewndex.h  
  
##  <a name="adddocksite"></a>COleIPFrameWndEx::AddDockSite  

  
```  
void AddDockSite();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addpane"></a>COleIPFrameWndEx::AddPane  

  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 [in] `bTail`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="adjustdockinglayout"></a>COleIPFrameWndEx::AdjustDockingLayout  

  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hdwp`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dockpane"></a>COleIPFrameWndEx::DockPane  

  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `nDockBarID`  
 [in] `lpRect`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="dockpaneleftof"></a>COleIPFrameWndEx::DockPaneLeftOf  
 Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich angedockt.  
  
 [in] `pLeftOf`  
 Ein Zeiger auf den Bereich, der als Ursprung dient.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` , wenn der Vorgang erfolgreich ist. Andernfalls wird `FALSE` zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um mehrere Bereich Objekte in einer vordefinierten Reihenfolge andocken. Diese Methode wird im angegebenen Bereich angedockt `pBar` auf der linken Seite des angegebenen Bereichs `pLeftOf`.  
  
##  <a name="enableautohidepanes"></a>COleIPFrameWndEx::EnableAutoHidePanes  

  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabledocking"></a>COleIPFrameWndEx::EnableDocking  

  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwDockStyle`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enablepanemenu"></a>COleIPFrameWndEx::EnablePaneMenu  

  
```  
void EnablePaneMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeLabel,  
    UINT uiViewToolbarsMenuEntryID,  
    BOOL bContextMenuShowsToolbarsOnly = FALSE,  
    BOOL bViewMenuShowsToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 [in] `uiCustomizeCmd`  
 [in] `strCustomizeLabel`  
 [in] `uiViewToolbarsMenuEntryID`  
 [in] `bContextMenuShowsToolbarsOnly`  
 [in] `bViewMenuShowsToolbarsOnly`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getactivepopup"></a>COleIPFrameWndEx::GetActivePopup  
 Gibt einen Zeiger auf den momentan angezeigten Popupmenü.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktive Popupmenü; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie einen Zeiger auf die [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das derzeit angezeigt wird.  
  
##  <a name="getcontainerframewindow"></a>COleIPFrameWndEx::GetContainerFrameWindow  

  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdefaultresid"></a>COleIPFrameWndEx::GetDefaultResId  
 Gibt die Ressourcen-ID, die zurück, wenn das Rahmenfenster im Menü geladen.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Ressourcen-ID im Menü oder 0 zurück, das Rahmenfenster besitzt keine Menüleiste.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Abrufen der Ressourcen-ID, die angegeben beim Rahmenfenster Menüressource durch Aufrufen von laden `COleIPFrameWndEx::LoadFrame`.  
  
##  <a name="getdockframe"></a>COleIPFrameWndEx::GetDockFrame  

  
```  
CFrameWnd* GetDockFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdockingmanager"></a>COleIPFrameWndEx::GetDockingManager  

  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmainframe"></a>COleIPFrameWndEx::GetMainFrame  

  
```  
CFrameWnd* GetMainFrame();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getmenubar"></a>COleIPFrameWndEx::GetMenuBar  
 Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Menü Bar-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Zeiger auf das Menü Bar-Objekt abzurufen, zu der gehört die `COleIPFrameWndEx` Objekt.  
  
##  <a name="getpane"></a>COleIPFrameWndEx::GetPane  

  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettearoffbars"></a>COleIPFrameWndEx::GetTearOffBars  
 Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine `CObList` -Objekt, das eine Auflistung von Zeigern auf enthält die [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)-abgeleiteten Objekten.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleIPFrameWndEx` Objekt verwaltet die Auflistung der abtrennbare Menüs als Liste von [CBasePane-Klasse](../../mfc/reference/cbasepane-class.md)-abgeleiteten Objekten. Verwenden Sie diese Methode, um einen Verweis auf diese Liste abzurufen.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>COleIPFrameWndEx::GetToolbarButtonToolTipText  
 Wird vom Framework aufgerufen, bevor die QuickInfo für die Schaltfläche angezeigt wird.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die Schaltfläche.  
  
 [in] `strTTText`  
 Ein Zeiger auf den QuickInfo-Text.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Anzeige von QuickInfos auf Symbolleisten-Schaltflächen anpassen.  
  
##  <a name="initusertoobars"></a>COleIPFrameWndEx::InitUserToobars  
 Gibt einen Bereich von Steuerelement-IDs, die das Framework die benutzerdefinierten Symbolleisten zuweist.  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszRegEntry`  
 Der Registrierungseintrag, in die Bibliothek Benutzer Toolbar-Einstellungen speichert.  
  
 [in] `uiUserToolbarFirst`  
 Steuerelement-ID, die erste benutzerdefinierte Symbolleiste zugewiesen.  
  
 [in] `uiUserToolbarLast`  
 Steuerelement-ID, die letzte benutzerdefinierte Symbolleiste zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Bereich von Steuerelement-IDs für die Zuordnung zur Symbolleisten zu initialisieren, die Benutzer dynamisch zu definieren. Die Parameter `uiUserToolbarFirst` und `uiUserToolbarLast` definieren die zulässigen Toolbar-Steuerelement-IDs. Legen Sie zum Deaktivieren der Erstellung von benutzerdefinierten Symbolleisten `uiUserToolbarFirst` oder `uiUserToolbarLast` auf-1 festgelegt.  
  
##  <a name="insertpane"></a>COleIPFrameWndEx::InsertPane  

  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 [in] `pTarget`  
 [in] `bAfter`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ismenubaravailable"></a>COleIPFrameWndEx::IsMenuBarAvailable  
 Bestimmt, ob der Zeiger auf das Menü Bar-Objekt nicht ist`NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein NULL-Wert weist das Rahmenfenster Menüleiste; Andernfalls wird 0 zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob das Rahmenfenster nicht verwaltet `NULL` Zeiger auf die im Menü Bar-Objekt.  
  
##  <a name="ispointneardocksite"></a>COleIPFrameWndEx::IsPointNearDockSite  

  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 [in] `dwBarAlignment`  
 [in] `bOuterEdge`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="loadframe"></a>COleIPFrameWndEx::LoadFrame  

  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIDResource`  
 [in] `dwDefaultStyle`  
 [in] `pParentWnd`  
 [in] `pContext`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclosedockingpane"></a>COleIPFrameWndEx::OnCloseDockingPane  

  
```  
virtual BOOL OnCloseDockingPane(CDockablePane*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CDockablePane*`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="oncloseminiframe"></a>COleIPFrameWndEx::OnCloseMiniFrame  

  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CPaneFrameWnd*`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onclosepopupmenu"></a>COleIPFrameWndEx::OnClosePopupMenu  
 Vom Framework aufgerufen, wenn eine aktive Popupmenü verarbeitet eine `WM_DESTROY` Nachricht.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPopup`  
 Ein Zeiger auf das Popupmenü-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Empfangen von Benachrichtigungen von `CMFCPopupMenu` Objekte beim Verarbeiten von `WM_DESTROY` Nachrichten.  
  
##  <a name="oncmdmsg"></a>COleIPFrameWndEx::OnCmdMsg  

  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 [in] `nCode`  
 [in] `pExtra`  
 [in] `pHandlerInfo`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawmenuimage"></a>COleIPFrameWndEx::OnDrawMenuImage  
 Vom Framework aufgerufen, wenn das Bild, das ein Menüelement zugeordnet ist, gezeichnet wird.  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext.  
  
 [in] `pMenuButton`  
 Ein Zeiger auf die Schaltfläche.  
  
 [in] `rectImage`  
 Das Bild dem Menüelement zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung führt keine Aktion aus und gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie Image für die Menüelemente, die auf der Menüleiste, die im Besitz von gehören zeichnen anpassen möchten, überschreiben Sie diese Methode die `COleIPFrameWndEx`-abgeleitetes Objekt.  
  
##  <a name="ondrawmenulogo"></a>COleIPFrameWndEx::OnDrawMenuLogo  
 Vom Framework aufgerufen wird bei einer [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)-Objekt Prozesse eine `WM_PAINT` Nachricht.  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger auf den Gerätekontext.  
  
 [in] `pMenu`  
 Zeiger auf das Popupmenü-Objekt.  
  
 [in] `rectLogo`  
 Ein Zeiger auf das Logo angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um ein Logo im Popupmenü die Menüleiste, die im Besitz von zugeordneten Anzeigen der `COleIPFrameWndEx`-abgeleitetes Objekt. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="onmenubuttontoolhittest"></a>COleIPFrameWndEx::OnMenuButtonToolHitTest  
 Vom Framework aufgerufen wird bei einer [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)-Objekt Prozesse eine `WM_NCHITTEST` Nachricht.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] pButton  
 Ein Zeiger auf eine Schaltfläche.  
  
 [out] pTI  
 Zeiger auf eine `TOOLINFO`-Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung führt keine Aktion aus und gibt 0 zurück. Die Implementierung muss einen Wert ungleich NULL zurückgeben, wenn sie voll der `pTI` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um QuickInfo-Informationen über ein bestimmtes Menüelement bereitzustellen.  
  
##  <a name="onmoveminiframe"></a>COleIPFrameWndEx::OnMoveMiniFrame  

  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onsetpreviewmode"></a>COleIPFrameWndEx::OnSetPreviewMode  

  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPreview`  
 [in] `pState`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowcustomizepane"></a>COleIPFrameWndEx::OnShowCustomizePane  

  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPane`  
 [in] `uiToolbarID`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowpanes"></a>COleIPFrameWndEx::OnShowPanes  

  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onshowpopupmenu"></a>COleIPFrameWndEx::OnShowPopupMenu  
 Wird vom Framework aufgerufen, wenn ein Popup-Menü angezeigt wird.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pMenuPopup`  
 Ein Zeiger auf das Popupmenü angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die standardmäßige Implementierung führt keine Aktion aus und gibt einen Wert ungleich NULL zurück. Die Implementierung sollte zurückgeben `FALSE` kann im Popupmenü angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Anzeige eines Popupmenüs anpassen. Sie können z. B. Menüschaltflächen in Farbe Menüschaltflächen ändern oder abtrennbare Balken zu initialisieren.  
  
##  <a name="ontearoffmenu"></a>COleIPFrameWndEx::OnTearOffMenu  
 Vom Framework aufgerufen, wenn der Benutzer ein Menü auswählt, die ein positionierbar wird.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPopup`  
 Ein Zeiger auf dem vom Benutzer ausgewählte Popup-Menü.  
  
 [in] `pBar`  
 Ein Zeiger auf den Bereich, der im Menü hostet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie das Framework, aktivieren Sie im Popupmenü möchten; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie das Setup des Balkens abtrennbare anpassen möchten.  
  
##  <a name="panefrompoint"></a>COleIPFrameWndEx::PaneFromPoint  

  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar,  
    CRuntimeClass* pRTCBarType) const;  
  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 [in] `nSensitivity`  
 [in] `bExactBar`  
 [in] `pRTCBarType`  
 [in] `dwAlignment`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="pretranslatemessage"></a>COleIPFrameWndEx::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMsg`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="recalclayout"></a>COleIPFrameWndEx::RecalcLayout  

  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNotify`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removepanefromdockmanager"></a>COleIPFrameWndEx::RemovePaneFromDockManager  

  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 [in] `bDestroy`  
 [in] `bAdjustLayout`  
 [in] `bAutoHide`  
 [in] `pBarReplacement`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdockstate"></a>COleIPFrameWndEx::SetDockState  
 Bereiche, die an das Rahmenfenster gehören gilt der angegebenen Andockstatus.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `state`  
 Gibt den andockzustand an.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen neuen docking Status für Bereiche angeben, die zu gehören die `COleIPFrameWndEx` Objekt.  
  
##  <a name="setuptoolbarmenu"></a>COleIPFrameWndEx::SetupToolbarMenu  
 Ändert ein Symbolleistenobjekt durch die Suche nach Dummy-Elementen und durch das anschließende Ersetzen dieser Dummy-Elemente durch die angegebenen benutzerdefinierten Elemente.  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menu`  
 Ein Verweis auf eine [CMenu](../../mfc/reference/cmenu-class.md) Objekt geändert werden.  
  
 [in] `uiViewUserToolbarCmdFirst`  
 Gibt den ersten benutzerdefinierten Befehl.  
  
 [in] `uiViewUserToolbarCmdLast`  
 Gibt den letzten benutzerdefinierten Befehl.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="showpane"></a>COleIPFrameWndEx::ShowPane  

  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 [in] `bShow`  
 [in] `bDelay`  
 [in] `bActivate`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="winhelpa"></a>COleIPFrameWndEx::WinHelpA  
 Wird vom Framework aufgerufen, um die WinHelp-Anwendung oder die Kontexthilfe zu initiieren.  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Parameter  
 [in] dwData  
 Gibt die für den durch `nCmd`angegeben Typ der Hilfe erforderlichen Daten an.  
  
 [in] `nCmd`  
 Gibt den Typ der angeforderten Hilfe an. Eine Liste der möglichen Werte und deren Einfluss auf den `dwData` -Parameter finden Sie unter der [WinHelp-Funktion](http://msdn.microsoft.com/library/windows/desktop/bb762267) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx-Klasse](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx-Klasse](../../mfc/reference/cmdiframewndex-class.md)

