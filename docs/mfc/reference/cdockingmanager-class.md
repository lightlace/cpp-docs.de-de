---
title: Klasse CDockingManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager class
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
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
ms.openlocfilehash: 106046dc9dc671b5baea7c6df78b91ba37098978
ms.lasthandoff: 02/24/2017

---
# <a name="cdockingmanager-class"></a>CDockingManager-Klasse
Implementiert die Kernfunktionen, die das Andocklayout in einem Hauptrahmenfenster steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Erstellt einen Bereich andocken und fügt es der Liste der Steuerleisten hinzu.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Fügt ein Handle zu einer Menüleiste Bereich, um die Liste der ausgeblendeten MDI-Leiste Bereiche im Registerkartenformat.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Die Liste der Mini-Frames hinzugefügt ein Rahmen.|  
|[CDockingManager::AddPane](#addpane)|Registriert einen Bereich mit dem docking-Manager.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Neu berechnet, und passt das Layout von allen Bereichen in einem Rahmenfenster.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Bewirkt, dass die `WM_NCCALCSIZE` Meldung an alle Fenster gesendet werden und `CPaneFrameWnd` Windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Passt die Ausrichtung eines Rechtecks an.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Ändert einen andockbaren Bereich im Ausblendmodus zum automatischen, die gesamte Breite dauert oder Höhe des Rahmens des Clientbereichs umgeben von Andocken Websites.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Erstellt eine Symbolleiste zum automatischen ausblenden.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Bringt die angedockten Balken, die die angegebene Ausrichtung am Anfang haben.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Namen andockbare Bereiche und Symbolleisten wird zu einem Menü hinzugefügt.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Berechnet das erwartete Rechteck eines angedockten Fensters.|  
|[CDockingManager::Create](#create)|Erstellt einen andockbaren Manager.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Bestimmt den Bereich mit einem bestimmten Zeitpunkt und seine docking-Status.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Aktiviert oder deaktiviert das Laden von andocklayout aus der Registrierung.|  
|[CDockingManager::DockPane](#dockpane)|Dockt an einen Bereich in einen anderen Bereich oder einem Rahmenfenster.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Andocken des Bereichs der Hauptframe ermöglicht, erstellt einen Bereich andocken und fügt es der Liste der Steuerleisten.|  
|[CDockingManager::EnableDocking](#enabledocking)|Erstellt einen Bereich andocken und im Bereich der Hauptframe andocken können.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Zeigt eine weitere Schaltfläche, die ein Popup-Menü auf die Titel aller andockbare Bereiche geöffnet wird.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Weist die Bibliothek, um eine spezielle Kontextmenü anzuzeigen, das eine Liste der Symbolleisten und andockbare Bereiche verfügt, wenn der Benutzer klickt auf die rechte Maustaste gedrückt, und die Bibliothek die WM_CONTEXTMENU-Meldung verarbeitet.|  
|[CDockingManager::FindDockSite](#finddocksite)|Ruft die Leiste Bereich, die an der angegebenen Position und der angegebenen Ausrichtung.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Gibt die Leiste Bereich, der die Id der Ziel-Leistenbereich hat.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Sucht einen Bereich von der angegebenen Steuerelement-ID|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Führt einen Commit für alle aktuellen symbolleistenpositionen virtuellen Rechtecke.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Gibt den Frame, der den angegebenen Punkt enthält.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Ruft das Rechteck, das die Grenzen des Clientbereichs enthält.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Gibt den aktuellen Andockmodus zurück.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Ruft einen Zeiger auf den übergeordneten Fenster Frame.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Gibt die Ausrichtung aktivierte der Bereiche zurück.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Ruft eine Liste von Miniframes ab.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Ruft ein Rechteck, das den äußeren Rand des Rahmens enthält.|  
|[CDockingManager::GetPaneList](#getpanelist)|Gibt eine Liste von Bereichen, die an die Dockingstation Manager gehören. Dies schließt alle unverankerter Bereiche.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Ruft einen Zeiger auf den intelligenten docking-Manager.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Ruft einen Zeiger auf den intelligenten docking-Manager.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Gibt die intelligente andockbaren Parameter für den docking-Manager zurück.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Eine statische Methode, die ein Design zur Anzeige von intelligenter andockmarkern zurückgibt.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Blendet einen Bereich, der im automatisch im Hintergrund ausgeführt wird.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Erstellt einen Bereich andocken und fügt es in die Liste der Steuerleisten.|  
|[CDockingManager::InsertPane](#insertpane)|Fügt einen Bereich des Steuerelements in der Liste der Steuerleisten.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Gibt an, ob ein Popup-Menü auf alle Bereiche der Titel angezeigt wird.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Bestimmt, ob das Layout von allen Bereichen angepasst werden.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Gibt an, ob der docking-Manager im OLE-Container-Modus.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob es sich bei ein angegebenen Punkt in der Nähe der Dock-Website befindet.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Bestimmt, ob der Seitenansicht-Modus festgelegt ist.|  
|[CDockingManager::LoadState](#loadstate)|Lädt den docking-Manager-Status aus der Registrierung.|  
|[CDockingManager::LockUpdate](#lockupdate)|Sperrt das angegebene Fenster an.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Wird vom Framework aufgerufen, wenn das Rahmenfenster verfügbar ist, oder ist deaktiviert.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Aufgerufen, um ein Minirahmenfenster zu verschieben.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Vom Framework aufgerufen, wenn ein Menü erstellt, die eine Liste von Bereichen.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Wird aufgerufen, durch das Framework aktivieren oder deaktivieren Sie das Kontrollkästchen für den angegebenen Befehl und neu berechnet das Layout eines Bereichs angezeigt.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Berechnet das interne Layout der Steuerelemente in der Liste der Steuerelemente.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Gibt den leeren Bereich Container frei.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Entfernt das angegebene Strich Bereich ausgeblendet.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Entfernt einen angegebenen Rahmen aus der Liste der Mini-Frames.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung eines Bereichs, und entfernt sie aus der Liste in der Dockingstation-Manager.|  
|[CDockingManager::ReplacePane](#replacepane)|Ersetzt einen Bereich durch einen anderen.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Sortiert die Frames in der Liste der Mini-Frames.|  
|[CDockingManager::SaveState](#savestate)|Status der Dockingstation Manager in der Registrierung gespeichert.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Sendet die angegebene Meldung an alle Mini-Frames.|  
|[CDockingManager::Serialize](#serialize)|Schreibt den docking-Manager in ein Archiv. (Überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Legt die Größe, Breite und Höhe der Steuerleisten und im angegebenen Bereich.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Legt den Andockmodus fest.|  
|[CDockingManager::SetDockState](#setdockstate)|Legt den andockzustand die Steuerleisten, die Mini-Frames und automatisch im Hintergrund Balken fest.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Legt den Seitenansichtsmodus der Balken, die in der Seitenansicht angezeigt werden.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Legt die Parameter, die das Verhalten des intelligentes Andocken definieren.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Anzeigen oder Ausblenden der Windows der Mini-Frames.|  
|[CDockingManager::ShowPanes](#showpanes)|Anzeigen oder Ausblenden der Bereiche der Balken Kontrolle und automatisch im Hintergrund.|  
|[CDockingManager::StartSDocking](#startsdocking)|Startet die intelligentes Andocken des angegebenen Fensters entsprechend der Ausrichtung des intelligenten docking-Managers.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Beendet smart andocken.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Gibt an, ob die Dockingstation Manager Bereiche im OLE-Container-Modus ausgeblendet.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Gibt den globalen Andockmodus an.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Gibt die Dockingstation Vertraulichkeit.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Gibt die Zeit in Millisekunden, bevor Sie ein andockbarer Bereich in den Befehlsmodus Dockingstation angedockt ist.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Gibt die Zeit in Millisekunden, bevor das Hauptrahmenfenster eine Symbolleiste angedockt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Das Hauptrahmenfenster erstellt und initialisiert diese Klasse automatisch.  
  
 Das Andocken-Objekt enthält eine Übersicht über alle Bereiche, die in der Dockingstation Layout sowie eine Liste aller [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) Windows, die an das Hauptrahmenfenster gehören.  
  
 Die `CDockingManager` -Klasse implementiert einige Dienste, die Sie verwenden können, um einen Bereich zu suchen oder eine `CPaneFrameWnd` Fenster. Sie in der Regel nicht diese Dienste direkt aufrufen, weil sie das Hauptrahmenfenster-Objekt umschlossen werden. Weitere Informationen finden Sie unter [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgenden Tipps gelten für `CDockingManager` Objekte:  
  
- [CDockingManager-Klasse](../../mfc/reference/cdockingmanager-class.md) unterstützt diese andockbaren Modi:  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Diese andockbaren Modi werden definiert, indem [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) und werden durch Aufrufen von [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Wenn Sie einen Bereich verankerte, fester Größe erstellen möchten, rufen Sie die [CDockingManager::AddPane](#addpane) Methode. Diese Methode registriert den Bereich mit dem docking-Manager, verantwortlich für das Layout der im Bereich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CDockingManager` Klasse zum Konfigurieren einer `CDockingManager` Objekt. Das Beispiel zeigt, wie eine weitere Schaltfläche angezeigt, die ein Popup-Menü auf die Titel aller andockbare Bereiche geöffnet wird und wie den Andockmodus des Objekts festgelegt. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#24;](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>CDockingManager::AddDockSite  
 Erstellt einen Bereich andocken und fügt es der Liste der Steuerleisten hinzu.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `info`  
 Ein Verweis auf ein Informationsstruktur, die enthält Andocken Bereich Ausrichtung.  
  
 [out] `ppDockBar`  
 Ein Zeiger auf einen Zeiger auf den neuen Andocken Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Andocken Bereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar  
 Fügt ein Handle zu einer Menüleiste Bereich, um die Liste der ausgeblendeten MDI-Leiste Bereiche im Registerkartenformat.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen Balken im Bereich  
  
##  <a name="addpane"></a>CDockingManager::AddPane  
 Registriert einen Bereich mit dem docking-Manager.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pWnd`  
 Gibt den Bereich der docking-Manager hinzu.  
  
 [in] `bTail`  
 `TRUE`So fügen im Bereich am Ende der Liste der Bereiche für den docking-Manager; andernfalls `FALSE`.  
  
 [in] `bAutoHide`  
 Nur für interne Verwendung. Verwenden Sie immer den Standardwert `FALSE`.  
  
 [in] `bInsertForOuterEdge`  
 Nur für interne Verwendung. Verwenden Sie immer den Standardwert `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`im Bereich mit den docking-Manager; erfolgreich registriert wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die verankerte, fester Größe Bereiche Andocken-Manager zu registrieren. Wenn Sie die Bereiche nicht registrieren, werden sie bei der Dockingstation Manager angelegt wird nicht ordnungsgemäß angezeigt.  
  
##  <a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout  
 Neu berechnet, und passt das Layout von allen Bereichen in einem Rahmenfenster.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hdwp`  
 Gibt die verzögerte Fenster Position-Struktur. Weitere Informationen finden Sie unter [Windows Data Types](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addminiframe"></a>CDockingManager::AddMiniFrame  
 Die Liste der Mini-Frames hinzugefügt ein Rahmen.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf einen Frame.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Frame nicht in der Liste der Mini-Frames ist und erfolgreich hinzugefügt wurde; `FALSE` andernfalls.  
  
##  <a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames  
 Bewirkt, dass die `WM_NCCALCSIZE` Meldung an alle Fenster gesendet werden und `CPaneFrameWnd` Windows.  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="adjustrecttoclientarea"></a>CDockingManager::AdjustRectToClientArea  
 Passt die Ausrichtung eines Rechtecks an.  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectResult`  
 Ein Verweis auf ein `CRect` Objekt  
  
 [in] `dwAlignment`  
 Die Ausrichtung der `CRect` Objekt  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Ausrichtung der `CRect` Objekt wurde geändert. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Die `dwAlignment` Parameter kann einen der folgenden Werte aufweisen:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane  
 Ändert einen andockbaren Bereich im Ausblendmodus zum automatischen, die gesamte Breite dauert oder Höhe des Rahmens des Clientbereichs umgeben von Andocken Websites.  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDefaultSlider`  
 Der Schieberegler andockbaren.  
  
 [in] `bIsVisible`  
 `TRUE`Wenn die andockbare Bereich sichtbar ist; `FALSE` andernfalls.  
  
##  <a name="autohidepane"></a>CDockingManager::AutoHidePane  
 Erstellt eine Symbolleiste zum automatischen ausblenden.  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf die Leiste im Bereich.  
  
 [in] `pCurrAutoHideToolBar`  
 Ein Zeiger auf ein Auto-Symbolleiste ausblenden.  
  
### <a name="return-value"></a>Rückgabewert  
 `NULL`Wenn das automatische Symbolleiste ausblenden wurde erstellt. andernfalls ein Zeiger auf die neue Symbolleiste.  
  
##  <a name="bringbarstotop"></a>CDockingManager::BringBarsToTop  
 Bringt die angedockten Balken, die die angegebene Ausrichtung am Anfang haben.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Die Ausrichtung der Dock Balken die oben in der anderen Windows übertragen werden.  
  
 [in] `bExcludeDockedBars`  
 `TRUE`die angedockten Balken ausschließen, wird im Vordergrund; andernfalls `FALSE`.  
  
##  <a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu  
 Namen andockbare Bereiche und Symbolleisten wird zu einem Menü hinzugefügt.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menu`  
 Ein Menü zum Hinzufügen der Namen von andockbaren Bereiche und Symbolleisten.  
  
 [in] `bToolbarsOnly`  
 `TRUE`nur die Namen von Symbolleisten zum Menü hinzufügen; `FALSE` andernfalls.  
  
##  <a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect  
 Berechnet das erwartete Rechteck eines angedockten Fensters.  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf das Fenster angedockt.  
  
 [in] `ptMouse`  
 Die Position des Mauszeigers.  
  
 [out] `rectResult`  
 Das berechnete Rechteck.  
  
 [in] `bDrawTab`  
 `TRUE`Um eine Registerkarte zu zeichnen. andernfalls `FALSE`.  
  
 [out] `ppTargetBar`  
 Ein Zeiger auf einen Zeiger auf den Zielbereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet das Rechteck, das ein Fenster einnehmen würde, wenn ein Benutzer das Fenster durch festgelegten Punkt gezogen `ptMouse` und es gibt es angedockt.  
  
##  <a name="create"></a>CDockingManager::Create  
 Erstellt einen andockbaren Manager.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Ein Zeiger auf den übergeordneten Frame des docking-Managers. Dieser Wert darf nicht sein `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`immer.  
  
##  <a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus  
 Bestimmt den Bereich mit einem bestimmten Zeitpunkt und seine docking-Status.  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Die Position des Bereichs zu überprüfen.  
  
 [in] `nSensitivity`  
 Der Wert, der das Rechteck im Fenster für jeden aktivierten Bereich erhöhen. Ein Bereich entspricht die Suchkriterien entsprechen, ist der angegebene Punkt in dieser Region erhöhte.  
  
 [in] `dwEnabledAlignment`  
 Die Ausrichtung des andockbaren Bereich.  
  
 [out] `ppTargetBar`  
 Ein Zeiger auf einen Zeiger auf den Zielbereich.  
  
 [in] `pBarToIgnore`  
 Der Bereich, in dem die Methode ignoriert.  
  
 [in] `pBarToDock`  
 Der Bereich, der angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Docking-Status.  
  
### <a name="remarks"></a>Hinweise  
 Docking-Status kann eine der folgenden Werte sein:  
  
|AFX_CS_STATUS Wert|Bedeutung|  
|---------------------------|-------------|  
|CS_NOTHING|Der Zeiger ist nicht über eine docksite. Halten Sie daher im Bereich Gleitkommazahl.|  
|CS_DOCK_IMMEDIATELY|Der Zeiger wird über die Dock-Website in den Befehlsmodus (DT_IMMEDIATE Style aktiviert ist), damit Bereich sofort verankert sein muss.|  
|CS_DELAY_DOCK|Der Zeiger wird über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe.|  
|CS_DELAY_DOCK_TO_TAB|Der Zeiger wird über eine docksite, bei dem der Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Mauszeiger über eine Beschriftung für ein anderes andockbaren Bereich oder einen Registerkartenbereich ein Fenster mit Registerkarten.|  
  
##  <a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState  
 Aktiviert oder deaktiviert das Laden von andocklayout aus der Registrierung.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDisable`  
 `TRUE`zum Laden von andocklayout aus der Registrierung zu deaktivieren. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Aufgerufen Sie diese Methode wird, wenn Sie das aktuelle Layout des andockbaren Bereiche und Symbolleisten beibehalten müssen, wenn der Zustand der Anwendung geladen wird.  
  
##  <a name="dockpane"></a>CDockingManager::DockPane  
 Dockt an einen Bereich in einen anderen Bereich oder einem Rahmenfenster.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen Balken im Bereich angedockt.  
  
 [in] `nDockBarID`  
 Die Id des Balkens andocken.  
  
 [in] `lpRect`  
 Das Zielrechteck.  
  
##  <a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf  
 Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBarToDock`  
 Ein Zeiger auf den Bereich links angedockt werden `pTargetBar`.  
  
 [in] `pTargetBar`  
 Ein Zeiger auf den Zielbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
##  <a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes  
 Andocken des Bereichs der Hauptframe ermöglicht, erstellt einen Bereich andocken und fügt es der Liste der Steuerleisten.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyle`  
 Die Dockingstation Ausrichtung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Andocken Bereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="enabledocking"></a>CDockingManager::EnableDocking  
 Erstellt einen Bereich andocken und im Bereich der Hauptframe andocken können.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyle`  
 Die Dockingstation Ausrichtung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Andocken Bereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu  
 Zeigt eine weitere Schaltfläche, die ein Popup-Menü auf die Titel aller andockbare Bereiche geöffnet wird.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie im Menü des Dock-Website; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im Menü des Dock-Website zeigt die folgenden Optionen zum Ändern der Andockstatus des Bereichs an:  
  
- `Floating`-Einen Bereich wird verschoben  
  
- `Docking`-Dockt einen Bereich in den Hauptframe an der Position, an die im Bereich zuletzt angedockt wurde  
  
- `AutoHide`-Wechselt den Bereich in den Ausblendmodus zum automatischen  
  
- `Hide`-Einen Bereich ausgeblendet  
  
 Standardmäßig wird dieses Menü nicht angezeigt.  
  
##  <a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu  
 Weist die Bibliothek, um eine spezielle Kontextmenü anzuzeigen, das eine Liste der Symbolleisten und andockbare Bereiche verfügt, wenn der Benutzer klickt auf die rechte Maustaste gedrückt, und die Bibliothek die WM_CONTEXTMENU-Meldung verarbeitet.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Wenn `TRUE`, die Bibliothek aktiviert die Unterstützung für automatische Kontextmenü; Falls `FALSE` die Bibliothek deaktiviert die Unterstützung für automatische Kontextmenü.  
  
 [in] `uiCustomizeCmd`  
 Befehls-Id für die **anpassen** Element im Menü.  
  
 [in] `strCustomizeText`  
 Der Text, der die **anpassen** Element.  
  
 [in] `bToolbarsOnly`  
 Wenn `TRUE`, klicken Sie im Menü zeigt nur eine Liste der Symbolleisten der Anwendung, wenn `FALSE`, die Bibliothek andockbare Bereiche der Anwendung zu dieser Liste hinzugefügt.  
  
##  <a name="finddocksite"></a>CDockingManager::FindDockSite  
 Ruft die Leiste Bereich, die an der angegebenen Position und der angegebenen Ausrichtung.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Die Ausrichtung des Balkens Bereich.  
  
 [in] `bOuter`  
 Wenn `TRUE`, die Leiste Head Position in der Liste der Steuerleisten abzurufen. Andernfalls abgerufen Sie die Leiste in der Endposition in der Liste der Steuerleisten werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die andockbaren Bereich, der die angegebene Ausrichtung hat; `NULL` andernfalls.  
  
##  <a name="findpanebyid"></a>CDockingManager::FindPaneByID  
 Sucht einen Bereich von der angegebenen Steuerelement-ID  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uBarID`  
 Gibt die Steuerelement-ID des Bereichs zu suchen.  
  
 [in] `bSearchMiniFrames`  
 `TRUE`Um alle unverankerter Bereiche in die Suche einbeziehen möchten. `FALSE`Um nur die angedockten Bereiche einzuschließen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [CBasePane](../../mfc/reference/cbasepane-class.md) Objekt mit dem angegebenen Steuerelement-ID oder `NULL` im angegebene Bereich gefunden werden kann.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane  
 Gibt die Leiste Bereich, der die Id der Ziel-Leistenbereich hat.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTargetBar`  
 Ein Zeiger auf die Ziel-Leistenbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Leiste Bereich, der die ID des Ziel-Leistenbereich; `NULL` Wenn kein derartiger Balken Bereich vorhanden ist.  
  
##  <a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects  
 Führt einen Commit für alle aktuellen symbolleistenpositionen virtuellen Rechtecke.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer beginnt, eine Symbolleiste ziehen, die Anwendung speichert die Daten ihrer ursprünglichen Position in der *virtuellen Rechteck*. Wenn der Benutzer eine Symbolleiste über seine docksite bewegt, kann die Symbolleiste andere Symbolleisten verlagert werden. Die ursprüngliche Position der anderen Symbolleisten werden in die entsprechenden virtuellen Rechtecke gespeichert.  
  
##  <a name="framefrompoint"></a>CDockingManager::FrameFromPoint  
 Gibt den Frame, der den angegebenen Punkt enthält.  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Gibt den Punkt in Bildschirmkoordinaten, um zu überprüfen.  
  
 [in] `pFrameToExclude`  
 Ein Zeiger auf einen Rahmen um auszuschließen.  
  
 [in] `bFloatMultiOnly`  
 `TRUE`Um Rahmen auszuschließen, die keine Instanzen von sind `CMultiPaneFrameWnd`; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Frame, der den angegebenen Punkt enthält; `NULL` andernfalls.  
  
##  <a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds  
 Ruft das Rechteck, das die Grenzen des Clientbereichs enthält.  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rcClient`  
 Ein Verweis auf das Rechteck, das die Grenzen des Clientbereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Rechteck, das die Grenzen des Clientbereichs enthält.  
  
##  <a name="getdockingmode"></a>CDockingManager::GetDockingMode  
 Gibt den aktuellen Andockmodus zurück.  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Enumeratorwert, der den aktuellen Andockmodus darstellt. Die folgenden Werte sind möglich:  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Festlegen des Andockmodus [CDockingManager::SetDockingMode](#setdockingmode).  
  
##  <a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd  
 Ruft einen Zeiger auf den übergeordneten Fenster Frame.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den übergeordneten Fenster Frame.  
  
##  <a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment  
 Gibt die Ausrichtung aktivierte der Bereiche zurück.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination von `CBRS_ALIGN_` Flags oder 0, wenn Automatisches Ausblenden Bereiche nicht aktiviert sind. Weitere Informationen finden Sie unter [EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Hinweise  
 Die Methode gibt die Ausrichtung aktivierte Steuerleisten automatisch im Hintergrund. Rufen Sie zum Aktivieren von leisten zum automatischen Ausblenden [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="getminiframes"></a>CDockingManager::GetMiniFrames  
 Ruft eine Liste von Miniframes ab.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Liste der Miniframes, die die Steuerleisten enthalten, die an die Dockingstation Manager gehören.  
  
##  <a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds  
 Ruft ein Rechteck, das den äußeren Rand des Rahmens enthält.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rechteck, das den äußeren Rand des Rahmens enthält.  
  
##  <a name="getpanelist"></a>CDockingManager::GetPaneList  
 Gibt eine Liste von Bereichen, die an die Dockingstation Manager gehören. Dies schließt alle unverankerter Bereiche.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `lstBars`  
 Enthält alle Bereiche des aktuellen docking-Managers.  
  
 [in] `bIncludeAutohide`  
 `TRUE`die Bereiche enthalten, die im Ausblendmodus zum automatischen sind; andernfalls `FALSE`.  
  
 [in] `pRTCFilter`  
 Wenn dies nicht `NULL`, die zurückgegebene Liste enthält die Bereiche nur der angegebene Runtime-Klasse.  
  
 [in] `bIncludeTabs`  
 `TRUE`um die Registerkarten enthalten. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn alle Bereiche im Registerkartenformat in der Dockingstation-Manager vorhanden sind, gibt die Methode Zeiger auf [CBaseTabbedPane Klasse](../../mfc/reference/cbasetabbedpane-class.md) Objekte, und Sie müssen die Registerkarten explizit auflisten.  
  
 Verwendung `pRTCFilter` zum Abrufen einer bestimmten Klasse Bereiche. Beispielsweise können Sie nur Symbolleisten abrufen, wird dieser Wert entsprechend festgelegt.  
  
##  <a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager  
 Ruft einen Zeiger auf den intelligenten docking-Manager.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [smart andockbaren Manager](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent  
 Ruft einen Zeiger auf den intelligenten docking-Manager.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den intelligenten docking-Manager.  
  
##  <a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams  
 Gibt die intelligente andockbaren Parameter für den docking-Manager zurück.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Klasse, die intelligente docking-Parameter für den aktuellen docking-Manager enthält. Weitere Informationen finden Sie unter [CSmartDockingInfo Klasse](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes  
 Blendet einen Bereich, der im automatisch im Hintergrund ausgeführt wird.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBarToExclude`  
 Ein Zeiger auf eine Leiste ausblenden ausgeschlossen.  
  
 [in] `bImmediately`  
 `TRUE`So blenden Sie im Bereich sofort aus; `FALSE` zum Ausblenden des Fensters mit dem Effekt automatisch im Hintergrund.  
  
##  <a name="insertdocksite"></a>CDockingManager::InsertDockSite  
 Erstellt einen Bereich andocken und fügt es in die Liste der Steuerleisten.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `info`  
 Eine Struktur, die Informationen für die Ausrichtung zum Bereich andocken enthält.  
  
 [in] `dwAlignToInsertAfter`  
 Die Ausrichtung des Bereichs andocken.  
  
 [out] `ppDockBar`  
 Ein Zeiger auf einen Zeiger auf einen Bereich andocken.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Andocken Bereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="insertpane"></a>CDockingManager::InsertPane  
 Fügt einen Bereich des Steuerelements in der Liste der Steuerleisten.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf einen Bereich des Steuerelements.  
  
 [in] `pTarget`  
 Ein Zeiger auf ein Zielbereich.  
  
 [in] `bAfter`  
 `TRUE`den Bereich nach der Position des Bereichs Ziel einfügen; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Steuerelement im Bereich der Liste der Steuerleisten erfolgreich hinzugefügt wurde; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt false zurück, wenn der Steuerelement Bereich bereits in der Liste der Steuerleisten ist oder im Zielbereich nicht in der Liste der Steuerleisten vorhanden ist.  
  
##  <a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu  
 Gibt an, ob ein Popup-Menü auf alle Bereiche der Titel angezeigt wird.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Website andockmenüs auf alle andockbare Bereiche der Titel angezeigt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können im Menü des Dock-Website aktivieren, durch Aufrufen von [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout  
 Bestimmt, ob das Layout von allen Bereichen angepasst werden.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Layout von allen Bereichen angepasst werden. `FALSE` andernfalls.  
  
##  <a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode  
 Gibt an, ob der docking-Manager im OLE-Container-Modus.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der docking-Manager im OLE-Container-Modus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im OLE-Container-Modus werden alle andockbare Bereiche und Anwendungssymbolleisten ausgeblendet. Die Bereiche werden ebenfalls in diesem Modus ausgeblendet, wenn Sie festgelegt haben [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) auf `TRUE`.  
  
##  <a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite  
 Bestimmt, ob es sich bei ein angegebenen Punkt in der Nähe der Dock-Website befindet.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der angegebene Punkt.  
  
 [out] `dwBarAlignment`  
 Gibt an, welchen Rand in der Nähe der Punkt ist. Mögliche Werte sind `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP` und `CBRS_ALIGN_BOTTOM`.  
  
 [out] `bOuterEdge`  
 `TRUE`Wenn der Punkt in der Nähe von den äußeren Rahmen des Standorts Dock ist; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Punkt in der Nähe der Dock-Website ist. andernfalls `FALSE`.  
  
##  <a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid  
 Bestimmt, ob der Seitenansicht-Modus festgelegt ist.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Seitenansicht festgelegt wird. `FALSE` andernfalls.  
  
##  <a name="loadstate"></a>CDockingManager::LoadState  
 Lädt den docking-Manager-Status aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Profilname.  
  
 [in] `uiID`  
 Die Id des docking-Managers.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn sich der Andockstatus Manager erfolgreich geladen wurde. andernfalls `FALSE`.  
  
##  <a name="lockupdate"></a>CDockingManager::LockUpdate  
 Sperrt das angegebene Fenster an.  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bLock`  
 `TRUE`Wenn das Fenster gesperrt ist. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Fenster gesperrt ist, kann nicht verschoben werden, und kann nicht neu gezeichnet werden.  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode  
 Gibt an, ob die Dockingstation Manager Bereiche im OLE-Container-Modus ausgeblendet.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert auf `FALSE` , wenn alle Bereiche, die an den Hauptframe sichtbar angedockt werden soll die Anwendung wird im OLE-Container-Modus. Standardmäßig ist dieser Wert `TRUE`.  
  
##  <a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal  
 Gibt den globalen Andockmodus an.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verwendet jedes andockbaren dieser Andockmodus. Weitere Informationen zu den Werten, die auf dieses Feld festgelegt werden kann, finden Sie unter [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity  
 Gibt die Dockingstation Vertraulichkeit.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Dockingstation Empfindlichkeit definiert wie schließen eine Gleitkommazahl im Bereich kann einen andockbaren Bereich, andockbaren Website oder einem anderen Bereich Ansatz, bevor das Framework den angedockten Zustand ändert.  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Gibt die Zeit in Millisekunden, bevor Sie ein andockbarer Bereich in den Befehlsmodus Dockingstation angedockt ist.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Hinweise  
 Bevor Sie ein Bereich angedockt ist, wartet das Framework die angegebene Zeitdauer. Dadurch wird verhindert, dass den Bereich versehentlich Andocken an einen Speicherort während der Benutzer ziehen ist.  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock  
 Gibt die Zeit in Millisekunden, bevor das Hauptrahmenfenster eine Symbolleiste angedockt ist.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Hinweise  
 Bevor eine Symbolleiste angedockt ist, wartet das Framework die angegebene Zeitdauer. Dadurch wird verhindert, dass die Symbolleiste wird versehentlich an eine Position angedockt, während der Benutzer es weiterhin zieht.  
  
##  <a name="onactivateframe"></a>CDockingManager::OnActivateFrame  
 Wird vom Framework aufgerufen, wenn das Rahmenfenster verfügbar ist, oder ist deaktiviert.  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActivate`  
 Wenn `TRUE`, das Rahmenfenster ist verfügbar, wenn `FALSE`, das Rahmenfenster ist deaktiviert.  
  
##  <a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu  
 Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework sendet eine Nachricht WM_DESTROY bei der aktuelle Hauptfenster zu schließen. Überschreiben Sie diese Methode zum Behandeln von Benachrichtigungen von `CMFCPopupMenu` Objekte, die an das Rahmenfenster gehören bei einer `CMFCPopupMenu` -Objekt Prozesse eine `WM_DESTROY` Nachricht.  
  
##  <a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame  
 Aufgerufen, um ein Minirahmenfenster zu verschieben.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Ein Zeiger auf ein Minirahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist. andernfalls `FALSE`.  
  
##  <a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu  
 Vom Framework aufgerufen, wenn ein Menü erstellt, die eine Liste von Bereichen.  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt den Speicherort des Menüs.  
  
##  <a name="panefrompoint"></a>CDockingManager::PaneFromPoint  
 Gibt den Bereich, der den angegebenen Punkt enthält.  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt den Punkt in Bildschirmkoordinaten, um zu überprüfen.  
  
 [in] `nSensitivity`  
 Der Wert, der das Rechteck im Fenster für jeden aktivierten Bereich vergrößert werden soll. Ein Bereich erfüllt die Suchkriterien, wenn der angegebene Punkt in diesem vergrößerte Bereich ist.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht `NULL`, die-Methode sucht nur die Bereiche des angegebenen Typs.  
  
 [in] `bCheckVisibility`  
 `TRUE`Um nur die sichtbaren Bereiche zu überprüfen. andernfalls `FALSE`.  
  
 [out] `dwAlignment`  
 Wenn ein Bereich am angegebenen Punkt gefunden wird, enthält dieser Parameter den Rand des Bereichs, der dem angegebenen Punkt am nächsten ist. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `pBarToIgnore`  
 Wenn dies nicht `NULL`, die Methode mit diesem Parameter angegebenen Bereiche ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [CBasePane](../../mfc/reference/cbasepane-class.md)-abgeleitetes Objekt mit dem angegebenen Punkt oder `NULL` Wenn kein Bereich gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Funktion zurückgibt und ein Bereich gefunden wurde, `dwAlignment` die Ausrichtung des angegebenen Punkt enthält. Wenn der Punkt am nächsten am Anfang des Bereichs befand sich z. B. `dwAlignment` Wert `CBRS_ALIGN_TOP`.  
  
##  <a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand  
 Wird aufgerufen, durch das Framework aktivieren oder deaktivieren Sie das Kontrollkästchen für den angegebenen Befehl und neu berechnet das Layout eines Bereichs angezeigt.  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Id einer Steuerleiste im Menü.  
  
 [in] `nCode`  
 Der Befehl Benachrichtigungscode.  
  
 [in] `pExtra`  
 Ein Zeiger auf, die "void" ist ein Zeiger auf die Typumwandlung `CCmdUI` Wenn `nCode` aufgerufen wird.  
  
 [in] `pHandlerInfo`  
 Ein Zeiger auf ein Info-Struktur. Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pEXtra` ist nicht NULL und `nCode` gleich aufgerufen, oder wenn es eine Steuerleiste mit dem angegebenen `nID`.  
  
##  <a name="recalclayout"></a>CDockingManager::RecalcLayout  
 Berechnet das interne Layout der Steuerelemente in der Liste der Steuerelemente.  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNotify`  
 Dieser Parameter wird nicht verwendet.  
  
##  <a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers  
 Gibt den leeren Bereich Container frei.  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar  
 Entfernt das angegebene Strich Bereich ausgeblendet.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen Balken im Bereich zu entfernen.  
  
##  <a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame  
 Entfernt einen angegebenen Rahmen aus der Liste der Mini-Frames.  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf einen Rahmen zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der angegebene Frame entfernt wird; `FALSE` andernfalls.  
  
##  <a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager  
 Hebt die Registrierung eines Bereichs, und entfernt sie aus der Liste in der Dockingstation-Manager.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf einen Bereich entfernt werden soll.  
  
 [in] `bDestroy`  
 Wenn `TRUE`, entfernte Bereich zerstört wird.  
  
 [in] `bAdjustLayout`  
 Wenn `TRUE`, passen Sie das Andocken Layout sofort.  
  
 [in] `bAutoHide`  
 Wenn `TRUE`, Bereich aus der Liste automatisch im Hintergrund Balken entfernt wird. Wenn `FALSE`, Bereich aus der Liste der regulären Bereiche entfernt wird.  
  
 [in] `pBarReplacement`  
 Ein Zeiger auf einen Bereich, der Bereich entfernten ersetzt.  
  
##  <a name="replacepane"></a>CDockingManager::ReplacePane  
 Ersetzt einen Bereich durch einen anderen.  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOriginalBar`  
 Ein Zeiger auf den ursprünglichen Bereich.  
  
 [in] `pNewBar`  
 Ein Zeiger auf den Bereich, der den ursprünglichen Bereich ersetzt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich ersetzt wird. `FALSE` andernfalls.  
  
##  <a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesForZOrder  
 Sortiert die Frames in der Liste der Mini-Frames.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>CDockingManager::SaveState  
 Status der Dockingstation Manager in der Registrierung gespeichert.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Ein Pfad zu einem Registrierungsschlüssel.  
  
 [in] `uiID`  
 Die Dockingstation Manager-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Umfasst das Speichern des Zustands von der Dockingstation-Manager in der Registrierung speichern die Zustände der Steuerleisten, die Zustände der Balken automatisch im Hintergrund und die Zustände der Mini-Frames in der Dockingstation-Manager vorhanden.  
  
##  <a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames  
 Sendet die angegebene Meldung an alle Mini-Frames.  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uMessage`  
 Die Nachricht gesendet werden.  
  
 [in] `wParam`  
 Zusätzliche abhängige Nachrichteninformationen.  
  
 [in] `lParam`  
 Zusätzliche abhängige Nachrichteninformationen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`immer.  
  
##  <a name="serialize"></a>CDockingManager::Serialize  
 Schreibt den docking-Manager in ein Archiv.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
 Ein Verweis auf ein Archivobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Schreiben eines Archivs des Dockingstation Managers umfasst das Bestimmen der Anzahl von andocken, Steuerleisten und Schieberegler, und schreiben die Steuerleisten Mini-Frames, die automatisch im Hintergrund Balken und MDI im Registerkartenformat Balken in das Archiv.  
  
##  <a name="setautohidezorder"></a>CDockingManager::SetAutohideZOrder  
 Legt die Größe, Breite und Höhe der Steuerleisten und im angegebenen Bereich.  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pAHDockingBar`  
 Ein Zeiger auf einen andockbaren Bereich.  
  
##  <a name="setdockingmode"></a>CDockingManager::SetDockingMode  
 Legt den Andockmodus fest.  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>Parameter  
 `dockMode`  
 Gibt den neuen Andockmodus an. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `theme`  
 Gibt das Design für den intelligenten andockmarkern verwendet werden soll. Es kann eine der folgenden Enumerationswerte: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese statische Methode, um den Andockmodus festzulegen.  
  
 `dockMode`Dabei kann es sich um eine der folgenden Werte sein:  
  
- `DT_STANDARD`-Standard-Modus andocken, wie Sie in Visual Studio .NET 2003 implementiert. Bereiche werden ohne Ziehen Kontext gezogen.  
  
- `DT_IMMEDIATE`-In Microsoft Visio sofortige Andockmodus als implementiert wurde. Bereiche werden mit einem Drag & Drop Kontext gezogen, aber kein Marker angezeigt werden.  
  
- `DT_SMART`-Smart Andockmodus wie in Visual Studio 2005 implementiert. Bereiche werden mit einem Drag & Drop Kontext gezogen und intelligente Marker angezeigt werden, anzeigen, in dem Bereich angedockt werden kann.  
  
##  <a name="setdockstate"></a>CDockingManager::SetDockState  
 Legt den andockzustand die Steuerleisten, die Mini-Frames und automatisch im Hintergrund Balken fest.  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode  
 Legt den Seitenansichtsmodus der Balken, die in der Seitenansicht angezeigt werden.  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bPreview`  
 `TRUE`Wenn die Seitenansicht festgelegt wird. `FALSE` andernfalls.  
  
 [in] `pState`  
 Ein Zeiger auf eine Preview-Status. Dieser Parameter wird nicht verwendet.  
  
##  <a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams  
 Legt die Parameter, die das Verhalten des intelligentes Andocken definieren.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `params`  
 Definiert die Parameter für intelligentes Andocken.  
  
### <a name="remarks"></a>Hinweise  
 Aufgerufen Sie diese Methode wird, wenn Sie die Darstellung, die Farbe oder die Form von intelligenten andockmarkern anpassen möchten.  
  
 Um die Standard-Darstellung für intelligenten andockmarkern zu verwenden, übergeben Sie eine nicht initialisierte Instanz des [CSmartDockingInfo Klasse](../../mfc/reference/csmartdockinginfo-class.md) auf `params`.  
  
##  <a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames  
 Anzeigen oder Ausblenden der Windows der Mini-Frames.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`um das Fenster des angezeigten Frames zu aktivieren; `FALSE to` Ausblenden des Fensters des Frames.  
  
##  <a name="showpanes"></a>CDockingManager::ShowPanes  
 Anzeigen oder Ausblenden der Bereiche der Balken Kontrolle und automatisch im Hintergrund.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`um die Bereiche anzuzeigen; `FALSE to` Bereiche ausblenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
##  <a name="startsdocking"></a>CDockingManager::StartSDocking  
 Startet die intelligentes Andocken des angegebenen Fensters entsprechend der Ausrichtung des intelligenten docking-Managers.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockingWnd`  
 Ein Zeiger auf ein Fenster zu verankern.  
  
##  <a name="stopsdocking"></a>CDockingManager::StopSDocking  
 Beendet smart andocken.  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme  
 Eine statische Methode, die ein Design zur Anzeige von intelligenter andockmarkern zurückgibt.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen der folgenden Enumerationswerte: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx-Klasse](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd-Klasse](../../mfc/reference/cpaneframewnd-class.md)

