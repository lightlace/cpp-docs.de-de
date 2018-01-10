---
title: COleIPFrameWndEx Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- COleIPFrameWndEx [MFC], AddDockSite
- COleIPFrameWndEx [MFC], AddPane
- COleIPFrameWndEx [MFC], AdjustDockingLayout
- COleIPFrameWndEx [MFC], DockPane
- COleIPFrameWndEx [MFC], DockPaneLeftOf
- COleIPFrameWndEx [MFC], EnableAutoHidePanes
- COleIPFrameWndEx [MFC], EnableDocking
- COleIPFrameWndEx [MFC], EnablePaneMenu
- COleIPFrameWndEx [MFC], GetActivePopup
- COleIPFrameWndEx [MFC], GetContainerFrameWindow
- COleIPFrameWndEx [MFC], GetDefaultResId
- COleIPFrameWndEx [MFC], GetDockFrame
- COleIPFrameWndEx [MFC], GetDockingManager
- COleIPFrameWndEx [MFC], GetMainFrame
- COleIPFrameWndEx [MFC], GetMenuBar
- COleIPFrameWndEx [MFC], GetPane
- COleIPFrameWndEx [MFC], GetTearOffBars
- COleIPFrameWndEx [MFC], GetToolbarButtonToolTipText
- COleIPFrameWndEx [MFC], InsertPane
- COleIPFrameWndEx [MFC], IsMenuBarAvailable
- COleIPFrameWndEx [MFC], IsPointNearDockSite
- COleIPFrameWndEx [MFC], LoadFrame
- COleIPFrameWndEx [MFC], OnCloseDockingPane
- COleIPFrameWndEx [MFC], OnCloseMiniFrame
- COleIPFrameWndEx [MFC], OnClosePopupMenu
- COleIPFrameWndEx [MFC], OnCmdMsg
- COleIPFrameWndEx [MFC], OnDrawMenuImage
- COleIPFrameWndEx [MFC], OnDrawMenuLogo
- COleIPFrameWndEx [MFC], OnMenuButtonToolHitTest
- COleIPFrameWndEx [MFC], OnMoveMiniFrame
- COleIPFrameWndEx [MFC], OnSetPreviewMode
- COleIPFrameWndEx [MFC], OnShowCustomizePane
- COleIPFrameWndEx [MFC], OnShowPanes
- COleIPFrameWndEx [MFC], OnShowPopupMenu
- COleIPFrameWndEx [MFC], OnTearOffMenu
- COleIPFrameWndEx [MFC], PaneFromPoint
- COleIPFrameWndEx [MFC], PreTranslateMessage
- COleIPFrameWndEx [MFC], RecalcLayout
- COleIPFrameWndEx [MFC], RemovePaneFromDockManager
- COleIPFrameWndEx [MFC], SetDockState
- COleIPFrameWndEx [MFC], SetupToolbarMenu
- COleIPFrameWndEx [MFC], ShowPane
- COleIPFrameWndEx [MFC], WinHelpA
- COleIPFrameWndEx [MFC], InitUserToobars
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44004262d9c009ee295404dd5c8781f795eb7bc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx-Klasse
Die Klasse `COleIPFrameWndEx` implementiert einen OLE-Container, der MFC unterstützt. Sie müssen die Klasse für das direkte Rahmenfenster der Anwendung von der `COleIPFrameWndEx` -Klasse ableiten und nicht von der [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)-Klasse. 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
## <a name="syntax"></a>Syntax  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## <a name="members"></a>Member  
  
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
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|Wird von Framework aufgerufen, wenn ein [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)-Objekt eine WM_PAINT-Meldung verarbeitet.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|Wird von Framework aufgerufen, wenn ein [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)-Objekt eine WM_NCHITTEST-Meldung verarbeitet.|  
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
 Das folgende Beispiel zeigt, wie Sie für eine Instanz der `COleIPFrameWndEx` -Klasse eine Unterklasse erstellen und deren Methoden außer Kraft setzen. Das Beispiel veranschaulicht, wie die Methoden `OnDestory` , `RepositionFrame` , `RecalcLayout` und `CalcWindowRect` außer Kraft gesetzt werden. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#1](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Rufen Sie diese Methode, um mehrere Bereich Objekte in einer vordefinierten Reihenfolge andocken. Diese Methode Dockt den Bereich, der vom angegebenen an `pBar` auf der linken Seite des Bereichs von angegebenen `pLeftOf`.  
  
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
 Gibt einen Zeiger auf das aktuell angezeigte Popupmenü zurück.  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die aktives Popupmenü; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie einen Zeiger auf die [CMFCPopupMenu Klasse](../../mfc/reference/cmfcpopupmenu-class.md) -Objekt, das derzeit angezeigt wird.  
  
##  <a name="getcontainerframewindow"></a>COleIPFrameWndEx::GetContainerFrameWindow  

  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getdefaultresid"></a>COleIPFrameWndEx::GetDefaultResId  
 Gibt zurück, die im Menü-Ressourcen-ID, die angegeben, wenn das Rahmenfenster im Menü geladen.  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Ressourcen-ID, der das Menü oder 0 zurück, wenn das Rahmenfenster keine Menüleisten hat.  
  
### <a name="remarks"></a>Hinweise  
 Aufruf dieser Funktion zum Abrufen der Ressourcen-ID, die angegeben, wenn das Rahmenfenster die Menüressource durch den Aufruf geladen `COleIPFrameWndEx::LoadFrame`.  
  
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
 Ein Zeiger auf das menüleistenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Zeiger auf das menüleistenobjekt abzurufen, die zu gehört die `COleIPFrameWndEx` Objekt.  
  
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
 Ein Verweis auf eine `CObList` -Objekt, das eine Auflistung von Zeigern auf enthält die [CBasePane Klasse](../../mfc/reference/cbasepane-class.md)-abgeleitete Objekte.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleIPFrameWndEx` -Objekt verwaltet die Auflistung von abtrennbare Menüs als eine Liste der [CBasePane Klasse](../../mfc/reference/cbasepane-class.md)--abgeleitete Objekte. Verwenden Sie diese Methode, um einen Verweis auf diese Liste abzurufen.  
  
##  <a name="gettoolbarbuttontooltiptext"></a>COleIPFrameWndEx::GetToolbarButtonToolTipText  
 Wird vom Framework aufgerufen, bevor die QuickInfo für die Schaltfläche angezeigt wird.  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pButton`  
 Ein Zeiger auf die Schaltfläche "".  
  
 [in] `strTTText`  
 Ein Zeiger auf den QuickInfo-Text.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardimplementierung gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Anzeige der QuickInfo auf Symbolleisten-Schaltflächen anpassen.  
  
##  <a name="initusertoobars"></a>COleIPFrameWndEx::InitUserToobars  
 Gibt einen Bereich von Steuerelement-IDs, die die benutzerdefinierten Symbolleisten das Framework zuweist.  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszRegEntry`  
 Der Registrierungseintrag, in dem die Bibliothek Symbolleiste benutzereinstellungen speichert.  
  
 [in] `uiUserToolbarFirst`  
 Steuerelement-ID, die die erste benutzerdefinierte Symbolleiste zugewiesen.  
  
 [in] `uiUserToolbarLast`  
 Steuerelement-ID der letzten eine benutzerdefinierte Symbolleiste zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Bereich von Steuerelement-IDs für die Zuweisung zu Symbolleisten zu initialisieren, die Benutzer dynamisch zu definieren. Die Parameter `uiUserToolbarFirst` und `uiUserToolbarLast` definieren Sie einen Bereich der zulässigen Toolbar-Steuerelement-IDs. Um die Erstellung von benutzerdefinierten Symbolleisten zu deaktivieren, legen `uiUserToolbarFirst` oder `uiUserToolbarLast` auf-1 festgelegt.  
  
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
 Ermittelt, ob der Zeiger auf das Menüleistenobjekt nicht `NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein NULL-Wert, wenn das Rahmenfenster eine Menüleiste; hat Andernfalls wird 0 zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob das Rahmenfenster nicht verwaltet `NULL` Zeiger auf seine menüleistenobjekt.  
  
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
 Vom Framework aufgerufen, wenn ein aktives Popupmenü verarbeitet eine `WM_DESTROY` Nachricht.  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPopup`  
 Ein Zeiger auf das Popupmenü-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Empfangen von Benachrichtigungen von `CMFCPopupMenu` beim Verarbeiten von Objekten `WM_DESTROY` Nachrichten.  
  
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
 Ein Zeiger auf die Menüschaltfläche.  
  
 [in] `rectImage`  
 Das Bild dem Menüelement zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie für die Menüelemente, die auf der Menüleiste, die im Besitz von gehören zeichnen Bild anpassen möchten die `COleIPFrameWndEx`-abgeleitetes Objekt.  
  
##  <a name="ondrawmenulogo"></a>COleIPFrameWndEx::OnDrawMenuLogo  
 Vom Framework aufgerufen, wenn eine [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)-Objekt Prozesse eine `WM_PAINT` Nachricht.  
  
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
 Überschreiben Sie diese Methode, um ein Logo im Popupmenü der Menüleiste, die im Besitz von zugeordneten Anzeigen der `COleIPFrameWndEx`-abgeleitetes Objekt. Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="onmenubuttontoolhittest"></a>COleIPFrameWndEx::OnMenuButtonToolHitTest  
 Vom Framework aufgerufen, wenn eine [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)-Objekt Prozesse eine `WM_NCHITTEST` Nachricht.  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] pButton  
 Ein Zeiger auf eine Menüschaltfläche.  
  
 [out] pTI  
 Zeiger auf eine `TOOLINFO`-Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt 0 zurück. Die Implementierung muss einen Wert ungleich NULL zurückgeben, wenn es voll ist die `pTI` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um QuickInfo-Informationen zu einem bestimmten Menüelement anzugeben.  
  
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
 Vom Framework aufgerufen, wenn ein Popupmenü angezeigt wird.  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pMenuPopup`  
 Ein Zeiger auf das Menü das Popupmenü angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei der Standardimplementierung wird keine Aktion ausgeführt, und gibt einen Wert ungleich 0 (null) zurück. Die Implementierung sollte zurückgeben `FALSE` Popupmenü angezeigt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Anzeige eines Popupmenüs anpassen. Beispielsweise können Menüschaltflächen in Farbe Menüschaltflächen ändern oder abtrennbare Balken zu initialisieren.  
  
##  <a name="ontearoffmenu"></a>COleIPFrameWndEx::OnTearOffMenu  
 Vom Framework aufgerufen, wenn der Benutzer ein Menü auswählt, die einen Balken abtrennbare verfügt.  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenuPopup`  
 Ein Zeiger auf das Menü das Popupmenü, das der Benutzer ausgewählt.  
  
 [in] `pBar`  
 Ein Zeiger auf den Bereich, der das Menü hostet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework das Menü das Popupmenü aktiviert werden sollen; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, wenn Sie das Setup von abtrennbarer Leiste anpassen möchten.  
  
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
 Wendet den angegebenen Andockstatus auf Bereiche, die zum Rahmenfenster gehören.  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `state`  
 Gibt den andockzustand an.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie eine neue andockzustand für Bereiche angeben, die zu gehören die `COleIPFrameWndEx` Objekt.  
  
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
 Gibt die erste benutzerdefinierte-Befehl.  
  
 [in] `uiViewUserToolbarCmdLast`  
 Gibt den letzten benutzerdefinierte-Befehl.  
  
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
