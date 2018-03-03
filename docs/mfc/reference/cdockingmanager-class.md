---
title: CDockingManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f1a436ab6bfbc5e21e43267d3992310ed6f6a20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdockingmanager-class"></a>CDockingManager-Klasse
Implementiert die Kernfunktionen, die das Andocklayout in einem Hauptrahmenfenster steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|Erstellt einen Dockbereich und fügt es der Liste der Steuerleisten hinzu.|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Fügt ein Handle auf eine Leiste Bereich, um die Liste der ausgeblendeten MDI Strich Bereiche im Registerkartenformat.|  
|[CDockingManager::AddMiniFrame](#addminiframe)|Die Liste der Mini-Frames hinzugefügt ein Rahmen.|  
|[CDockingManager::AddPane](#addpane)|Registriert einen Bereich beim Dock-Manager.|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|Passt das Layout von allen Bereichen in einem Rahmenfenster und neu berechnet.|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Bewirkt, dass die `WM_NCCALCSIZE` an alle Bereiche zu sendende Nachricht und `CPaneFrameWnd` Windows.|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|Passt die Ausrichtung eines Rechtecks an.|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Ändert einen andockbaren Bereich in den Hintergrundmodus, sodass die gesamte Breite dauert oder Höhe des Frames Clientbereich enthaltender Andocken Websites.|  
|[CDockingManager::AutoHidePane](#autohidepane)|Erstellt eine Symbolleiste zum automatischen ausblenden.|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Schaltet den angedockten Balken an, die die angegebene Ausrichtung an den Anfang haben.|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Ein Menü mit hinzugefügt Namen von andockbare Bereiche und Symbolleisten.|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Berechnet das erwartete Rechteck eines angedockten Fensters.|  
|[CDockingManager::Create](#create)|Erstellt einen andockbaren-Manager.|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Bestimmt, der Bereich, der einem bestimmten Zeitpunkt und deren andockbaren Status enthält.|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Aktiviert oder deaktiviert das Laden der andocklayout aus der Registrierung.|  
|[CDockingManager::DockPane](#dockpane)|Dockt einen Bereich an, zu einem anderen Bereich oder einem Rahmenfenster.|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Andocken des Bereichs zum Hauptframe ermöglicht, einen Dockbereich erstellt und die Liste der Steuerleisten hinzugefügt.|  
|[CDockingManager::EnableDocking](#enabledocking)|Erstellt einen Dockbereich und des Bereichs zum Hauptframe andocken können.|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Zeigt eine weitere Schaltfläche, die ein Popupmenü auf Beschriftungen von allen andockbare Bereiche geöffnet wird.|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Weist die Bibliothek, um eine spezielle Kontextmenü anzuzeigen, das eine Liste der Anwendungssymbolleisten und andockbare Bereiche aufweist, wenn der Benutzer klickt auf die rechte Maustaste gedrückt, und die Bibliothek WM_CONTEXTMENU Nachricht verarbeitet.|  
|[CDockingManager::FindDockSite](#finddocksite)|Ruft die Leiste Bereich, die an der angegebenen Position und die angegebene Ausrichtung.|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Gibt die Leiste Bereich, der die Id des Ziel-Leistenbereich verfügt.|  
|[CDockingManager::FindPaneByID](#findpanebyid)|Sucht nach einem Bereich durch das angegebene Steuerelement-ID.|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Führt einen Commit für alle aktuellen symbolleistenpositionen virtuellen Rechtecke.|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|Gibt den Frame, der den angegebenen Punkt enthält.|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Ruft das Rechteck, das die Grenzen des Clientbereichs enthält.|  
|[CDockingManager::GetDockingMode](#getdockingmode)|Gibt den aktuellen Andockmodus zurück.|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Ruft einen Zeiger auf den Frame des übergeordneten Fenster.|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Gibt die Ausrichtung aktiviert der Bereiche zurück.|  
|[CDockingManager::GetMiniFrames](#getminiframes)|Ruft eine Liste der Miniframes ab.|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Ruft ein Rechteck, das die äußeren Rändern des Frames enthält.|  
|[CDockingManager::GetPaneList](#getpanelist)|Gibt eine Liste von Bereichen, die zu Dock-Manager gehören. Dies schließt alle unverankerter Bereiche.|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Ruft einen Zeiger auf den intelligenten Dock-Manager ab.|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|Ruft einen Zeiger auf den intelligenten Dock-Manager ab.|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Gibt die intelligente andockbaren Parameter für Dock-Manager zurück.|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Eine statische Methode, die ein Design verwendet, um die Anzeige von intelligenter andockmarkern zurückgibt.|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Blendet einen Bereich, der in den Hintergrundmodus ist.|  
|[CDockingManager::InsertDockSite](#insertdocksite)|Erstellt einen Dockbereich und die Liste der Steuerleisten eingefügt.|  
|[CDockingManager::InsertPane](#insertpane)|Fügt einen Bereich des Steuerelements in der Liste der Steuerleisten ein.|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Gibt an, ob die Beschriftungen für alle Bereiche ein Popupmenü angezeigt wird.|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|Bestimmt, ob die Layouts für alle Bereiche angepasst werden.|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Gibt an, ob Dock-Manager im OLE-Container-Modus befindet.|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob ein angegebener Punkt in der Nähe der DockPosition ist.|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Bestimmt, ob der Seitenansicht-Modus festgelegt ist.|  
|[CDockingManager::LoadState](#loadstate)|Lädt die Dock-Manager-Status aus der Registrierung.|  
|[CDockingManager::LockUpdate](#lockupdate)|Sperrt das angegebene Fenster an.|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|Vom Framework aufgerufen, wenn das Rahmenfenster verfügbar ist, oder ist deaktiviert.|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM_DESTROY-Meldung verarbeitet.|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Wird aufgerufen, durch das Framework ein Minirahmenfenster zu verschieben.|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Vom Framework aufgerufen, wenn sie ein Menü erstellt, das eine Liste von Bereichen verfügt.|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Wird aufgerufen, durch das Framework aktivieren oder deaktivieren Sie das Kontrollkästchen für den angegebenen Befehl und neu berechnet das Layout eines gezeigt angezeigt.|  
|[CDockingManager::RecalcLayout](#recalclayout)|Berechnet das interne Layout der Steuerelemente in der Liste der Steuerelemente vorhanden.|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Gibt den leeren Bereich Container frei.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Entfernt das angegebene Strich Bereich ausgeblendet ist.|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Entfernt einen angegebenen Rahmen aus der Liste der Mini-Frames.|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung auf einen Bereich, und entfernt es aus der Liste im Dock-Manager.|  
|[CDockingManager::ReplacePane](#replacepane)|Ersetzt einen Bereich durch einen anderen.|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|Fällt die Frames in der Liste der Mini-Frames zurück.|  
|[CDockingManager::SaveState](#savestate)|Dock-Manager-Status in der Registrierung gespeichert.|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Sendet die angegebene Meldung an alle Mini-Frames.|  
|[CDockingManager::Serialize](#serialize)|Schreibt die Dock-Manager in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|Legt die Größe, Breite und Höhe der Steuerleisten und im angegebenen Bereich.|  
|[CDockingManager::SetDockingMode](#setdockingmode)|Legt den Andockmodus fest.|  
|[CDockingManager::SetDockState](#setdockstate)|Legt den andockzustand den Steuerleisten, die kurzen Frames und die Leisten zum automatischen Ausblenden fest.|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Legt den Seitenansichtsmodus der Balken, die in der Seitenansicht angezeigt werden.|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Die Parameter, die das Verhalten des intelligentes Andocken definieren festgelegt.|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|Anzeigen oder Ausblenden der Windows Mini Frames.|  
|[CDockingManager::ShowPanes](#showpanes)|Zeigt an, oder blendet Sie aus den Bereichen der Balken Steuerelement und automatisches ausblenden.|  
|[CDockingManager::StartSDocking](#startsdocking)|Startet die intelligentes Andocken des angegebenen Fensters gemäß die Ausrichtung des intelligenten Dock-Manager.|  
|[CDockingManager::StopSDocking](#stopsdocking)|Beendet für intelligente andocken.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Gibt an, ob es sich bei Dock-Manager Bereiche im Modus für OLE-Container ausgeblendet.|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Gibt die globalen Andockmodus an.|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Gibt die andockbare Vertraulichkeit.|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Gibt die Zeit in Millisekunden, bevor Sie ein andockbarer Bereich im unmittelbaren Andockmodus angedockt ist.|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Gibt die Zeit in Millisekunden, bevor eine Symbolleiste an das Hauptrahmenfenster angedockt ist.|  
  
## <a name="remarks"></a>Hinweise  
 Das Hauptrahmenfenster erstellt und initialisiert diese Klasse automatisch.  
  
 Dock-Manager-Objekt enthält eine Liste aller Bereiche, die Layout des Docks teilnehmen und auch eine Liste aller [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) Windows, die an das Hauptrahmenfenster gehören.  
  
 Die `CDockingManager` Klasse implementiert einige Dienste, die Sie verwenden können, um einen Bereich zu suchen oder eine `CPaneFrameWnd` Fenster. In der Regel Aufrufen nicht diese Dienste direkt, da sie in das Hauptrahmenfenster-Objekt umschlossen ist. Weitere Informationen finden Sie unter [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgenden Tipps gelten für `CDockingManager` Objekte:  
  
- [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) unterstützt diese andockbaren Modi:  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     Diese andockbaren Modi werden definiert, indem [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) und sind festgelegt werden, indem [CDockingManager::SetDockingMode](#setdockingmode).  
  
-   Wenn Sie einen unverankerte, nicht veränderbare Größen-Bereich erstellen möchten, rufen Sie die [CDockingManager::AddPane](#addpane) Methode. Diese Methode registriert den Bereich beim Dock-Manager, die für das Layout des Bereichs verwendet wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CDockingManager` Klasse zum Konfigurieren einer `CDockingManager` Objekt. Im Beispiel wird gezeigt, wie Sie eine weitere Schaltfläche anzuzeigen, die ein Popupmenü auf Beschriftungen von allen andockbare Bereiche geöffnet wird und wie den Andockmodus des Objekts festgelegt. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>CDockingManager::AddDockSite  
 Erstellt einen Dockbereich und fügt es der Liste der Steuerleisten hinzu.  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `info`  
 Ein Verweis auf ein Informationsstruktur, die enthält Andocken Bereich Ausrichtung.  
  
 [out] `ppDockBar`  
 Ein Zeiger auf einen Zeiger auf die neue Dockbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Dockbereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar  
 Fügt ein Handle auf eine Leiste Bereich, um die Liste der ausgeblendeten MDI Strich Bereiche im Registerkartenformat.  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf eine Leiste Bereich  
  
##  <a name="addpane"></a>CDockingManager::AddPane  
 Registriert einen Bereich beim Dock-Manager.  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pWnd`  
 Gibt den Bereich so Dock-Manager hinzu.  
  
 [in] `bTail`  
 `TRUE`So fügen Sie den Bereich an das Ende der Liste von Bereichen für Dock-Manager; andernfalls `FALSE`.  
  
 [in] `bAutoHide`  
 Nur für interne Verwendung. Verwenden Sie immer den Standardwert `FALSE`.  
  
 [in] `bInsertForOuterEdge`  
 Nur für interne Verwendung. Verwenden Sie immer den Standardwert `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich beim Dock-Manager; erfolgreich registriert wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um unverankerte, nicht veränderbare Größen Bereiche beim Dock-Manager zu registrieren. Wenn Sie die Bereiche nicht registrieren, werden sie beim Dock-Manager angeordnet sind nicht ordnungsgemäß angezeigt.  
  
##  <a name="adjustdockinglayout"></a>CDockingManager::AdjustDockingLayout  
 Passt das Layout von allen Bereichen in einem Rahmenfenster und neu berechnet.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hdwp`  
 Gibt an, die verzögerte Fenster Position-Struktur. Weitere Informationen finden Sie unter [Windows-Datentypen](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="addminiframe"></a>CDockingManager::AddMiniFrame  
 Die Liste der Mini-Frames hinzugefügt ein Rahmen.  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Ein Zeiger auf einen Rahmen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Frame nicht in der Liste der Mini-Frames und wurde erfolgreich hinzugefügt; `FALSE` andernfalls.  
  
##  <a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames  
 Bewirkt, dass die `WM_NCCALCSIZE` an alle Bereiche zu sendende Nachricht und `CPaneFrameWnd` Windows.  
  
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
 Ein Verweis auf eine `CRect` Objekt  
  
 [in] `dwAlignment`  
 Die Ausrichtung der `CRect` Objekt  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Ausrichtung der `CRect` Objekt wurde angepasst. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Die `dwAlignment` Parameter kann einen der folgenden Werte aufweisen:  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane  
 Ändert einen andockbaren Bereich in den Hintergrundmodus, sodass die gesamte Breite dauert oder Höhe des Frames Clientbereich enthaltender Andocken Websites.  
  
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
 Ein Zeiger auf die Leiste Bereich.  
  
 [in] `pCurrAutoHideToolBar`  
 Ein Zeiger auf eine automatische Symbolleiste ausblenden.  
  
### <a name="return-value"></a>Rückgabewert  
 `NULL`Wenn die automatische Symbolleiste ausblenden wurde nicht erstellt. andernfalls ein Zeiger auf die neue Symbolleiste.  
  
##  <a name="bringbarstotop"></a>CDockingManager::BringBarsToTop  
 Schaltet den angedockten Balken an, die die angegebene Ausrichtung an den Anfang haben.  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Die Ausrichtung der Andocken Balken an, die an den Anfang über anderen Fenstern hinzugefügt werden.  
  
 [in] `bExcludeDockedBars`  
 `TRUE`die angedockten Balken ausschließen, wird im Vordergrund; andernfalls `FALSE`.  
  
##  <a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu  
 Ein Menü mit hinzugefügt Namen von andockbare Bereiche und Symbolleisten.  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menu`  
 Ein Menü mit die Namen der andockbare Bereiche und Symbolleisten hinzufügen.  
  
 [in] `bToolbarsOnly`  
 `TRUE`So fügen Sie nur die Namen von Symbolleisten zum Menü; `FALSE` andernfalls.  
  
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
 `TRUE`auf eine Registerkarte zu zeichnen. andernfalls `FALSE`.  
  
 [out] `ppTargetBar`  
 Ein Zeiger auf einen Zeiger auf den Zielbereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet das Rechteck, das ein Fenster einnehmen würde, wenn ein Benutzer das Fenster zu den vom angegebenen Punkt gezogen haben `ptMouse` und er es angedockt.  
  
##  <a name="create"></a>CDockingManager::Create  
 Erstellt einen andockbaren-Manager.  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Ein Zeiger auf den übergeordneten Frame des Dock-Manager. Dieser Wert darf nicht sein `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`immer.  
  
##  <a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus  
 Bestimmt, der Bereich, der einem bestimmten Zeitpunkt und deren andockbaren Status enthält.  
  
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
 Die Position des Bereichs, um zu überprüfen.  
  
 [in] `nSensitivity`  
 Der Wert, um das fensterrechtecke jedes aktivierte Bereichs zu erhöhen. Ein Bereich erfüllt die Suchkriterien, wenn der angegebene Punkt in dieser Region erhöhte ist.  
  
 [in] `dwEnabledAlignment`  
 Die Ausrichtung des andockbaren Bereich.  
  
 [out] `ppTargetBar`  
 Ein Zeiger auf einen Zeiger auf den Zielbereich.  
  
 [in] `pBarToIgnore`  
 Der Bereich, den die Methode ignoriert.  
  
 [in] `pBarToDock`  
 Der Bereich, der in der Dockingstation ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Der andockbaren Status.  
  
### <a name="remarks"></a>Hinweise  
 Docking Status kann einer der folgenden Werte sein:  
  
|AFX_CS_STATUS Wert|Bedeutung|  
|---------------------------|-------------|  
|CS_NOTHING|Der Zeiger ist nicht über eine docksite. Halten Sie daher den Bereich Gleitkommazahl.|  
|CS_DOCK_IMMEDIATELY|Der Zeiger ist, über die DockPosition in unmittelbarer Modus (DT_IMMEDIATE-Format aktiviert ist), damit der Bereich muss sofort angedockt werden.|  
|CS_DELAY_DOCK|Der Zeiger wird über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe.|  
|CS_DELAY_DOCK_TO_TAB|Der Zeiger wird über eine docksite, die bewirkt, dass der Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn die Maus über eine Beschriftung von einem anderen andockbaren Bereich oder eine Registerkartenbereich, der einen Bereich im Registerkartenformat.|  
  
##  <a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState  
 Aktiviert oder deaktiviert das Laden der andocklayout aus der Registrierung.  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDisable`  
 `TRUE`Laden von andocklayout aus der Registrierung zu deaktivieren; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, wenn Sie das aktuelle Layout des andockbaren Bereiche und Symbolleisten beibehalten müssen, wenn der Zustand der Anwendung geladen wird.  
  
##  <a name="dockpane"></a>CDockingManager::DockPane  
 Dockt einen Bereich an, zu einem anderen Bereich oder einem Rahmenfenster.  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf eine Leiste Bereich angedockt.  
  
 [in] `nDockBarID`  
 Die Id des Balkens angedockt werden soll.  
  
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
 Ein Zeiger auf den Bereich, um auf der linken Seite des angedockt werden `pTargetBar`.  
  
 [in] `pTargetBar`  
 Ein Zeiger auf den Zielbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
##  <a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes  
 Andocken des Bereichs zum Hauptframe ermöglicht, einen Dockbereich erstellt und die Liste der Steuerleisten hinzugefügt.  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyle`  
 Die andockbaren Ausrichtung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Dockbereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="enabledocking"></a>CDockingManager::EnableDocking  
 Erstellt einen Dockbereich und des Bereichs zum Hauptframe andocken können.  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyle`  
 Die andockbaren Ausrichtung.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Dockbereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu  
 Zeigt eine weitere Schaltfläche, die ein Popupmenü auf Beschriftungen von allen andockbare Bereiche geöffnet wird.  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie das Menü "Vorschauwebsite andocken"; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Menü "Vorschauwebsite andocken" zeigt die folgenden Optionen zum Ändern des Status des andockbaren Bereich:  
  
- `Floating`-: Verschiebt einen Bereich  
  
- `Docking`-Dockt einen Bereich in die Hauptframe an der Position, an der letzten Bereich angedockt  
  
- `AutoHide`-Wechselt der Bereich in den Hintergrundmodus  
  
- `Hide`-Blendet einen Bereich  
  
 Standardmäßig wird das Menü nicht angezeigt.  
  
##  <a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu  
 Weist die Bibliothek, um eine spezielle Kontextmenü anzuzeigen, das eine Liste der Anwendungssymbolleisten und andockbare Bereiche aufweist, wenn der Benutzer klickt auf die rechte Maustaste gedrückt, und die Bibliothek WM_CONTEXTMENU Nachricht verarbeitet.  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Wenn `TRUE`, die Bibliothek aktiviert die Unterstützung für die automatische Kontextmenü; Falls `FALSE` die Bibliothek deaktiviert die Unterstützung für die automatische Kontextmenü.  
  
 [in] `uiCustomizeCmd`  
 Eine Befehls-Id für die **anpassen** Element im Menü.  
  
 [in] `strCustomizeText`  
 Der Text, der die **anpassen** Element.  
  
 [in] `bToolbarsOnly`  
 Wenn `TRUE`, zeigt das Menü nur eine Liste der Anwendungssymbolleisten; Wenn `FALSE`, die Bibliothek andockbare Bereiche der Anwendung zu dieser Liste hinzugefügt.  
  
##  <a name="finddocksite"></a>CDockingManager::FindDockSite  
 Ruft die Leiste Bereich, die an der angegebenen Position und die angegebene Ausrichtung.  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Die Ausrichtung des Balkens Bereich.  
  
 [in] `bOuter`  
 Wenn `TRUE`, die Leiste in der die Head Position in der Liste der Steuerleisten abzurufen. Andernfalls abgerufen Sie die Leiste in der Endposition in der Liste der Steuerleisten werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die andockbaren Bereich, der die angegebene Ausrichtung verfügt; `NULL` andernfalls.  
  
##  <a name="findpanebyid"></a>CDockingManager::FindPaneByID  
 Sucht nach einem Bereich durch das angegebene Steuerelement-ID.  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uBarID`  
 Gibt die Steuerelement-ID des Bereichs zu suchen.  
  
 [in] `bSearchMiniFrames`  
 `TRUE`die Suche alle unverankerter Bereiche einschließt. `FALSE`Um nur die angedockten Bereiche einzuschließen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [CBasePane](../../mfc/reference/cbasepane-class.md) Objekt mit dem angegebenen Steuerelement-ID oder `NULL` , wenn der angegebene Bereich nicht gefunden werden kann.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane  
 Gibt die Leiste Bereich, der die Id des Ziel-Leistenbereich verfügt.  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTargetBar`  
 Ein Zeiger auf den Ziel-Leistenbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Leiste Bereich mit der Id des Ziel-Leistenbereich; `NULL` Wenn derartig Strich Bereich vorhanden ist.  
  
##  <a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects  
 Führt einen Commit für alle aktuellen symbolleistenpositionen virtuellen Rechtecke.  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer beginnt, eine Symbolleiste ziehen, wird die Anwendung speichert seiner ursprüngliche Position in der *virtuellen Rechteck*. Wenn der Benutzer eine Symbolleiste über seine DockPosition bewegt, möglicherweise andere Symbolleisten die Symbolleiste verschoben werden. Die ursprüngliche Positionen der anderen Symbolleisten sind in die entsprechenden virtuellen Rechtecke gespeichert.  
  
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
 `TRUE`Um Frames auszuschließen, die nicht auf Instanzen von sind `CMultiPaneFrameWnd`; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rahmen, der den angegebenen Punkt enthält; `NULL` andernfalls.  
  
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
 Ruft einen Zeiger auf den Frame des übergeordneten Fenster.  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den übergeordneten Fenster Frame.  
  
##  <a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment  
 Gibt die Ausrichtung aktiviert der Bereiche zurück.  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise Kombination von `CBRS_ALIGN_` Flags bzw. 0, wenn Automatisches Ausblenden Bereiche nicht aktiviert sind. Weitere Informationen finden Sie unter [EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).  
  
### <a name="remarks"></a>Hinweise  
 Die Methode gibt die Ausrichtung des Schiebeleisten-Steuerelemente zum automatischen Ausblenden aktiviert. Rufen Sie zum Aktivieren von leisten zum automatischen Ausblenden [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).  
  
##  <a name="getminiframes"></a>CDockingManager::GetMiniFrames  
 Ruft eine Liste der Miniframes ab.  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Liste der Miniframes, die die Steuerleisten enthalten, die zu Dock-Manager gehören.  
  
##  <a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds  
 Ruft ein Rechteck, das die äußeren Rändern des Frames enthält.  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rechteck, das die äußeren Rändern des Frames enthält.  
  
##  <a name="getpanelist"></a>CDockingManager::GetPaneList  
 Gibt eine Liste von Bereichen, die zu Dock-Manager gehören. Dies schließt alle unverankerter Bereiche.  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `lstBars`  
 Enthält alle Bereiche des aktuellen Dock-Manager.  
  
 [in] `bIncludeAutohide`  
 `TRUE`die Bereiche enthalten, in den Hintergrundmodus sind; andernfalls `FALSE`.  
  
 [in] `pRTCFilter`  
 Wenn dies nicht der `NULL`, die zurückgegebene Liste enthält Bereiche nur aus dem angegebenen Common Language Runtime-Klasse.  
  
 [in] `bIncludeTabs`  
 `TRUE`auf den Registerkarten enthalten. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn alle Bereiche im Registerkartenformat im Dock-Manager vorhanden sind, gibt die Methode Zeiger auf [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md) Objekte und Sie müssen die Registerkarten explizit auflisten.  
  
 Verwendung `pRTCFilter` zum Abrufen einer bestimmten Klasse Bereiche. Sie können z. B. nur Symbolleisten abrufen, indem entsprechend festlegen dieses Werts.  
  
##  <a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager  
 Ruft einen Zeiger auf den intelligenten Dock-Manager ab.  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [intelligenten Dock-Manager](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534).  
  
##  <a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerPermanent  
 Ruft einen Zeiger auf den intelligenten Dock-Manager ab.  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den intelligenten Dock-Manager.  
  
##  <a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams  
 Gibt die intelligente andockbaren Parameter für Dock-Manager zurück.  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Klasse, die smart andockbaren Parameter für die aktuelle Dock-Manager enthält. Weitere Informationen finden Sie unter [CSmartDockingInfo Klasse](../../mfc/reference/csmartdockinginfo-class.md).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes  
 Blendet einen Bereich, der in den Hintergrundmodus ist.  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBarToExclude`  
 Ein Zeiger auf einen Balken ausblenden ausgeschlossen.  
  
 [in] `bImmediately`  
 `TRUE`So blenden Sie den Bereich unmittelbar aus; `FALSE` um den Bereich mit den Effekt Taskleisten auszublenden.  
  
##  <a name="insertdocksite"></a>CDockingManager::InsertDockSite  
 Erstellt einen Dockbereich und die Liste der Steuerleisten eingefügt.  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `info`  
 Eine Struktur, die Ausrichtungsinformationen über den Bereich "andocken" enthält.  
  
 [in] `dwAlignToInsertAfter`  
 Die Ausrichtung des Bereichs "andocken".  
  
 [out] `ppDockBar`  
 Ein Zeiger auf einen Zeiger auf einen Dockbereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Dockbereich erfolgreich erstellt wurde. `FALSE` andernfalls.  
  
##  <a name="insertpane"></a>CDockingManager::InsertPane  
 Fügt einen Bereich des Steuerelements in der Liste der Steuerleisten ein.  
  
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
 `TRUE`den Bereich nach der Position des Bereichs "Ziel" eingefügt; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Steuerelement-Bereich der Liste der Steuerleisten erfolgreich hinzugefügt wurde; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt false zurück, wenn der Steuerelement-Bereich bereits in der Liste der Steuerleisten ist oder die Zielbereich nicht in der Liste der Steuerleisten vorhanden ist.  
  
##  <a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu  
 Gibt an, ob die Beschriftungen für alle Bereiche ein Popupmenü angezeigt wird.  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Menü "Vorschauwebsite andocken" auf die Beschriftungen von allen andockbare Bereiche angezeigt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Menü "Vorschauwebsite andocken" aktivieren, durch den Aufruf [CDockingManager::EnableDockSiteMenu](#enabledocksitemenu).  
  
##  <a name="isinadjustlayout"></a>CDockingManager::IsInAdjustLayout  
 Bestimmt, ob die Layouts für alle Bereiche angepasst werden.  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Layouts für alle Bereiche angepasst werden. `FALSE` andernfalls.  
  
##  <a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode  
 Gibt an, ob Dock-Manager im OLE-Container-Modus befindet.  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Dock-Manager im Modus für OLE-Container ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im Modus für OLE-Container werden alle andockbare Bereiche und Anwendungssymbolleisten ausgeblendet. Die Bereiche sind auch in diesem Modus ausgeblendet, wenn Sie festgelegt haben [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) auf `TRUE`.  
  
##  <a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite  
 Bestimmt, ob ein angegebener Punkt in der Nähe der DockPosition ist.  
  
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
 Gibt an, welche Kante, die in der Nähe der Punkt ist. Mögliche Werte sind `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP` und `CBRS_ALIGN_BOTTOM`.  
  
 [out] `bOuterEdge`  
 `TRUE`Wenn der Punkt in der Nähe von den äußeren Rahmen der DockPosition ist; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Punkt in der Nähe der DockPosition ist; andernfalls `FALSE`.  
  
##  <a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid  
 Bestimmt, ob der Seitenansicht-Modus festgelegt ist.  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Seitenansichtmodus festgelegt ist; `FALSE` andernfalls.  
  
##  <a name="loadstate"></a>CDockingManager::LoadState  
 Lädt die Dock-Manager-Status aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Profilname.  
  
 [in] `uiID`  
 Die Id des Dock-Manager.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie der andockzustand-Manager erfolgreich geladen wurde. andernfalls `FALSE`.  
  
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
 Gibt an, ob es sich bei Dock-Manager Bereiche im Modus für OLE-Container ausgeblendet.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert auf `FALSE` , wenn alle Bereiche, die in der Dockingstation zum Hauptframe sichtbar bleiben sollen die Anwendung wird im Modus für OLE-Container. Standardmäßig ist dieser Wert `TRUE`.  
  
##  <a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal  
 Gibt die globalen Andockmodus an.  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig verwendet jedes andockbaren Bereich dieser Andockmodus. Weitere Informationen zu den Werten, die in diesem Feld festgelegt werden kann, finden Sie unter [cbasepane:: Getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode).  
  
##  <a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity  
 Gibt die andockbare Vertraulichkeit.  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die andockbaren Sensitivität definiert, wie weit Gleitkommazahl im Bereich kann einen andockbaren Bereich, eine andockbare Website oder einem anderen Bereich annähern, bevor das Framework seinen Zustand zu angedockt ändert.  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock  
 Gibt die Zeit in Millisekunden, bevor Sie ein andockbarer Bereich im unmittelbaren Andockmodus angedockt ist.  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Hinweise  
 Bevor Sie ein Bereich angedockt ist, wartet das Framework die angegebene Zeitdauer. Dadurch wird verhindert, dass der Bereich angedockt versehentlich an einem Speicherort, während der Benutzer, ist es immer noch ziehen.  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock  
 Gibt die Zeit in Millisekunden, bevor eine Symbolleiste an das Hauptrahmenfenster angedockt ist.  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Hinweise  
 Bevor eine Symbolleiste angedockt ist, wartet das Framework die angegebene Zeitdauer. Dadurch wird verhindert, dass die Symbolleiste wird versehentlich an eine Position angedockt, während der Benutzer, ist es immer noch ziehen.  
  
##  <a name="onactivateframe"></a>CDockingManager::OnActivateFrame  
 Vom Framework aufgerufen, wenn das Rahmenfenster verfügbar ist, oder ist deaktiviert.  
  
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
 Das Framework sendet eine WM_DESTROY-Meldung an, bei das aktuellen Hauptfenster zu schließen. Überschreiben Sie diese Methode zum Behandeln von Benachrichtigungen von `CMFCPopupMenu` Objekte, die zum Rahmenfenster gehören bei einer `CMFCPopupMenu` -Objekt Prozesse eine `WM_DESTROY` Nachricht.  
  
##  <a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame  
 Wird aufgerufen, durch das Framework ein Minirahmenfenster zu verschieben.  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFrame`  
 Ein Zeiger auf ein Minirahmenfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist. andernfalls `FALSE`.  
  
##  <a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu  
 Vom Framework aufgerufen, wenn sie ein Menü erstellt, das eine Liste von Bereichen verfügt.  
  
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
 Der Wert, um das fensterrechtecke jedes aktivierte Bereichs vergrößert werden soll. Ein Bereich erfüllt die Suchkriterien entsprechen, wenn der angegebene Punkt in dieser Region vergrößerte ist.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht der `NULL`, sucht die Methode nur die Bereiche des angegebenen Typs.  
  
 [in] `bCheckVisibility`  
 `TRUE`Um nur die sichtbaren Bereiche zu überprüfen. andernfalls `FALSE`.  
  
 [out] `dwAlignment`  
 Wenn Sie ein Bereich am angegebenen Punkt gefunden wird, enthält dieser Parameter den Rand des Bereichs, der den angegebenen Punkt am nächsten gelegenen war. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `pBarToIgnore`  
 Wenn dies nicht der `NULL`, die-Methode ignoriert die Bereiche, die mit diesem Parameter angegebenen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [CBasePane](../../mfc/reference/cbasepane-class.md)-Objekt, das den angegebenen Punkt enthält abgeleitet oder `NULL` Wenn kein Bereich gefunden wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Funktion zurückgibt und ein Bereich gefunden wurde, `dwAlignment` die Ausrichtung des angegebenen Punkt enthält. Beispielsweise war der Punkt am Anfang des Bereichs am nächsten gelegenen `dwAlignment` festgelegt ist, um `CBRS_ALIGN_TOP`.  
  
##  <a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand  
 Wird aufgerufen, durch das Framework aktivieren oder deaktivieren Sie das Kontrollkästchen für den angegebenen Befehl und neu berechnet das Layout eines gezeigt angezeigt.  
  
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
 Ein Zeiger auf, die "void" ist die Typumwandlung in einen Zeiger auf `CCmdUI` Wenn `nCode` aufgerufen wird.  
  
 [in] `pHandlerInfo`  
 Ein Zeiger auf eine Informationsstruktur. Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pEXtra` ist nicht NULL und `nCode` gleich aufgerufen, oder es ist eine Steuerleiste mit dem angegebenen `nID`.  
  
##  <a name="recalclayout"></a>CDockingManager::RecalcLayout  
 Berechnet das interne Layout der Steuerelemente in der Liste der Steuerelemente vorhanden.  
  
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
 Entfernt das angegebene Strich Bereich ausgeblendet ist.  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf eine Leiste Bereich zu entfernen.  
  
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
 Hebt die Registrierung auf einen Bereich, und entfernt es aus der Liste im Dock-Manager.  
  
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
 Wenn `TRUE`, passen Sie das Layout des Docks sofort.  
  
 [in] `bAutoHide`  
 Wenn `TRUE`, der Bereich aus der Liste von leisten zum automatischen Ausblenden entfernt wird. Wenn `FALSE`, der Bereich aus der Liste der regulären Bereiche entfernt wird.  
  
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
 Fällt die Frames in der Liste der Mini-Frames zurück.  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>CDockingManager::SaveState  
 Dock-Manager-Status in der Registrierung gespeichert.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Ein Pfad zu einem Registrierungsschlüssel.  
  
 [in] `uiID`  
 Die Dock-Manager-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dock-Manager-Status in der Registrierung gespeichert werden die Zustände der Steuerleisten, die Zustände der Balken zum automatischen Ausblenden und die Zustände der kurzen Frames im Dock-Manager vorhanden.  
  
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
 Die zu sendende Meldung.  
  
 [in] `wParam`  
 Zusätzliche Meldung abhängige Informationen.  
  
 [in] `lParam`  
 Zusätzliche Meldung abhängige Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`immer.  
  
##  <a name="serialize"></a>CDockingManager::Serialize  
 Schreibt die Dock-Manager in ein Archiv.  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
 Ein Verweis auf ein Archivobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Schreiben in ein Archiv von Dock-Manager umfasst das Bestimmen der Anzahl von andocken, Steuerleisten und Schieberegler, und schreiben den Steuerleisten, die Mini-Frames, die Leisten zum automatischen Ausblenden und die Balken im Registerkartenformat MDI in das Archiv.  
  
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
 Gibt das Design für den intelligenten andockmarkern verwendet werden soll. Es kann eine der folgenden Enumerationswerte: AFX_SDT_DEFAULT AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese statische Methode, um den Andockmodus festzulegen.  
  
 `dockMode`einer der folgenden Werte ist möglich:  
  
- `DT_STANDARD`-Standard-Modus andocken, wie in Visual Studio .NET 2003 implementiert. Bereiche werden ohne eine ziehen Kontext gezogen.  
  
- `DT_IMMEDIATE`-In Microsoft Visio sofortige Andockmodus als implementiert wurde. Bereiche werden mit einem ziehen Kontext gezogen, aber kein Marker angezeigt werden.  
  
- `DT_SMART`-Intelligente Andockmodus wie in Visual Studio 2005 implementiert. Bereiche werden mit einem ziehen Kontext gezogen und intelligenten Marker angezeigt werden, die anzeigen, in dem der Bereich angedockt werden kann.  
  
##  <a name="setdockstate"></a>CDockingManager::SetDockState  
 Legt den andockzustand den Steuerleisten, die kurzen Frames und die Leisten zum automatischen Ausblenden fest.  
  
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
 `TRUE`Wenn der Seitenansichtmodus festgelegt ist; `FALSE` andernfalls.  
  
 [in] `pState`  
 Ein Zeiger auf einem vorschauzustand. Dieser Parameter wird nicht verwendet.  
  
##  <a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams  
 Die Parameter, die das Verhalten des intelligentes Andocken definieren festgelegt.  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `params`  
 Definiert die Parameter für intelligentes Andocken.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, wenn Sie die Darstellung, die Farbe oder die Form von intelligenten andockmarkern anpassen möchten.  
  
 Um das standardmäßige Aussehen für intelligenten andockmarkern verwenden, übergeben Sie eine nicht initialisierte Instanz des [CSmartDockingInfo Klasse](../../mfc/reference/csmartdockinginfo-class.md) auf `params`.  
  
##  <a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniFrames  
 Anzeigen oder Ausblenden der Windows Mini Frames.  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`um das Fenster des angezeigten Frames zu aktivieren; `FALSE to` Ausblenden des Fensters des Frames.  
  
##  <a name="showpanes"></a>CDockingManager::ShowPanes  
 Zeigt an, oder blendet Sie aus den Bereichen der Balken Steuerelement und automatisches ausblenden.  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`um die Bereiche anzuzeigen; `FALSE to` Bereiche ausblenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
##  <a name="startsdocking"></a>CDockingManager::StartSDocking  
 Startet die intelligentes Andocken des angegebenen Fensters gemäß die Ausrichtung des intelligenten Dock-Manager.  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockingWnd`  
 Ein Zeiger auf ein Fenster zu verankern.  
  
##  <a name="stopsdocking"></a>CDockingManager::StopSDocking  
 Beendet für intelligente andocken.  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme  
 Eine statische Methode, die ein Design verwendet, um die Anzeige von intelligenter andockmarkern zurückgibt.  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen der folgenden Enumerationswerte: AFX_SDT_DEFAULT AFX_SDT_VS2005, AFX_SDT_VS2008.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx-Klasse](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd-Klasse](../../mfc/reference/cpaneframewnd-class.md)
