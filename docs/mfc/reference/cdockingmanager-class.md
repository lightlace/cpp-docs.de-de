---
title: "CDockingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockingManager class"
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
caps.latest.revision: 37
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 39
---
# CDockingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Kernfunktionen, die Andockes Layout in einem Hauptrahmenfenster steuert.  
  
## Syntax  
  
```  
class CDockingManager : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](../Topic/CDockingManager::AddDockSite.md)|Stellt einen Dockbereich erstellt und fügt es der Liste der Steuerleisten hinzu.|  
|[CDockingManager::AddHiddenMDITabbedBar](../Topic/CDockingManager::AddHiddenMDITabbedBar.md)|Fügt ein Handle einem Leistebereich der Liste ausgeblendeter MDI mit den versehenen Leistebereichen hinzu.|  
|[CDockingManager::AddMiniFrame](../Topic/CDockingManager::AddMiniFrame.md)|Fügt der Liste der Frame Miniframen hinzu.|  
|[CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md)|Registriert einen Bereich mit dem Andocken Manager.|  
|[CDockingManager::AdjustDockingLayout](../Topic/CDockingManager::AdjustDockingLayout.md)|Berechnet neu und passt das Layout aller Bereiche in einem Rahmenfenster.|  
|[CDockingManager::AdjustPaneFrames](../Topic/CDockingManager::AdjustPaneFrames.md)|Bewirkt die `WM_NCCALCSIZE` Meldung, zu allen Bereichen und zu `CPaneFrameWnd` Fenstern gesendet werden.|  
|[CDockingManager::AdjustRectToClientArea](../Topic/CDockingManager::AdjustRectToClientArea.md)|Passt die Ausrichtung eines Rechtecks.|  
|[CDockingManager::AlignAutoHidePane](../Topic/CDockingManager::AlignAutoHidePane.md)|Ändert einen Hauptandockbereich im Modus "Automatisches Ausblenden" Größe um die normale Breite und die Höhe des Clientbereichs des Frames akzeptiert, der durch Docksites umgeben ist.|  
|[CDockingManager::AutoHidePane](../Topic/CDockingManager::AutoHidePane.md)|Stellt eine Symbolleiste der automatischen Ausblenden erstellt.|  
|[CDockingManager::BringBarsToTop](../Topic/CDockingManager::BringBarsToTop.md)|Setzt die Formulargröße Balken, die die angegebene Ausrichtung an der oberen haben.|  
|[CDockingManager::BuildPanesMenu](../Topic/CDockingManager::BuildPanesMenu.md)|Fügt Namen Andocken von Bereichen und Symbolleisten einem Menü hinzu.|  
|[CDockingManager::CalcExpectedDockedRect](../Topic/CDockingManager::CalcExpectedDockedRect.md)|Berechnet das erwartete Rechteck eines angedockten Fenster.|  
|[CDockingManager::Create](../Topic/CDockingManager::Create.md)|Stellt einen Andocken Manager erstellt.|  
|[CDockingManager::DeterminePaneAndStatus](../Topic/CDockingManager::DeterminePaneAndStatus.md)|Bestimmt den Bereich, der einen angegebenen Punkt und ihren Status Andocken enthält.|  
|[CDockingManager::DisableRestoreDockState](../Topic/CDockingManager::DisableRestoreDockState.md)|Aktiviert oder deaktiviert Laden des Andocken Layouts aus der Registrierung.|  
|[CDockingManager::DockPane](../Topic/CDockingManager::DockPane.md)|Dockt einen Bereich zu einem anderen Bereich oder einem Rahmenfenster an.|  
|[CDockingManager::DockPaneLeftOf](../Topic/CDockingManager::DockPaneLeftOf.md)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[CDockingManager::EnableAutoHidePanes](../Topic/CDockingManager::EnableAutoHidePanes.md)|Aktiviert Andocken des Bereichs zum Hauptframes, stellt einen Dockbereich erstellt und fügt es der Liste der Steuerleisten hinzu.|  
|[CDockingManager::EnableDocking](../Topic/CDockingManager::EnableDocking.md)|Stellt einen Dockbereich erstellt und aktiviert Andocken des Bereichs zum Großrechner.|  
|[CDockingManager::EnableDockSiteMenu](../Topic/CDockingManager::EnableDockSiteMenu.md)|Zeigt eine weitere Schaltfläche an, die ein Popupmenü auf den Beschriftungen aller Andocken Bereiche öffnen.|  
|[CDockingManager::EnablePaneContextMenu](../Topic/CDockingManager::EnablePaneContextMenu.md)|Teilt die Bibliothek mit, um ein bestimmtes Kontextmenü anzuzeigen, das eine Liste von Anwendungssymbolleisten und Andocken von Bereichen an, wenn der Benutzer auf die rechte Maustaste klickt und die Bibliothek die WM\_CONTEXTMENU\-Meldung verarbeitet.|  
|[CDockingManager::FindDockSite](../Topic/CDockingManager::FindDockSite.md)|Ruft den Leistebereich ab, der an der angegebenen Position ist und die angegebene Ausrichtung hat.|  
|[CDockingManager::FindDockSiteByPane](../Topic/CDockingManager::FindDockSiteByPane.md)|Gibt den Leistebereich zurück, der die ID des Zielleistebereichs verfügt.|  
|[CDockingManager::FindPaneByID](../Topic/CDockingManager::FindPaneByID.md)|Sucht einen Bereich von der angegebenen Steuerelement\-ID|  
|[CDockingManager::FixupVirtualRects](../Topic/CDockingManager::FixupVirtualRects.md)|Führt alle aktuellen Symbolleistenpositionen auf virtuellen Rechtecken einen Commit.|  
|[CDockingManager::FrameFromPoint](../Topic/CDockingManager::FrameFromPoint.md)|Gibt die Frames zurück, die den angegebenen Punkt enthält.|  
|[CDockingManager::GetClientAreaBounds](../Topic/CDockingManager::GetClientAreaBounds.md)|Ruft das Rechteck ab, das die Grenzen des Clientbereichs enthält.|  
|[CDockingManager::GetDockingMode](../Topic/CDockingManager::GetDockingMode.md)|Gibt den aktuellen Andockmodus zurück.|  
|[CDockingManager::GetDockSiteFrameWnd](../Topic/CDockingManager::GetDockSiteFrameWnd.md)|Ruft einen Zeiger auf den Rahmen des übergeordneten Fensters.|  
|[CDockingManager::GetEnabledAutoHideAlignment](../Topic/CDockingManager::GetEnabledAutoHideAlignment.md)|Gibt die aktivierte Ausrichtung der Bereiche zurück.|  
|[CDockingManager::GetMiniFrames](../Topic/CDockingManager::GetMiniFrames.md)|Ruft eine Liste von Minirahmen ab.|  
|[CDockingManager::GetOuterEdgeBounds](../Topic/CDockingManager::GetOuterEdgeBounds.md)|Ruft ein Rechteck ab, das die Außenkanten des Frames.|  
|[CDockingManager::GetPaneList](../Topic/CDockingManager::GetPaneList.md)|Gibt eine Liste von Bereichen zurück, die dem Andocken Manager gehören.  Dies schließt alle beweglichen Bereiche ein.|  
|[CDockingManager::GetSmartDockingManager](../Topic/CDockingManager::GetSmartDockingManager.md)|Ruft einen Zeiger auf das Andocken intelligenten Manager ab.|  
|[CDockingManager::GetSmartDockingManagerPermanent](../Topic/CDockingManager::GetSmartDockingManagerPermanent.md)|Ruft einen Zeiger auf das Andocken intelligenten Manager ab.|  
|[CDockingManager::GetSmartDockingParams](../Topic/CDockingManager::GetSmartDockingParams.md)|Gibt die intelligenten Andocken Parameter für den Andocken Manager zurück.|  
|[CDockingManager::GetSmartDockingTheme](../Topic/CDockingManager::GetSmartDockingTheme.md)|Eine statische Methode, die ein Design zurückgibt, das verwendet wird, um intelligente andockbare Markierung anzuzeigen.|  
|[CDockingManager::HideAutoHidePanes](../Topic/CDockingManager::HideAutoHidePanes.md)|Blendet einen Bereich aus, der im Modus "Automatisches Ausblenden" ist.|  
|[CDockingManager::InsertDockSite](../Topic/CDockingManager::InsertDockSite.md)|Stellt einen Dockbereich erstellt und fügt es in die Liste der Steuerleisten ein.|  
|[CDockingManager::InsertPane](../Topic/CDockingManager::InsertPane.md)|Fügt einen Steuerbereich in die Liste der Steuerleisten ein.|  
|[CDockingManager::IsDockSiteMenu](../Topic/CDockingManager::IsDockSiteMenu.md)|Gibt an, ob ein Popupmenü auf den Beschriftungen aller Bereiche angezeigt wird.|  
|[CDockingManager::IsInAdjustLayout](../Topic/CDockingManager::IsInAdjustLayout.md)|Bestimmt, ob die Layouts aller Bereiche angepasst werden.|  
|[CDockingManager::IsOLEContainerMode](../Topic/CDockingManager::IsOLEContainerMode.md)|Gibt an, ob der andockbare Manager im OLE\-Containermodus ist.|  
|[CDockingManager::IsPointNearDockSite](../Topic/CDockingManager::IsPointNearDockSite.md)|Bestimmt, ob ein bestimmter Punkt neben der Docksite ist.|  
|[CDockingManager::IsPrintPreviewValid](../Topic/CDockingManager::IsPrintPreviewValid.md)|Bestimmt, ob der Seitenansichtsmodus festgelegt ist.|  
|[CDockingManager::LoadState](../Topic/CDockingManager::LoadState.md)|Lädt den Andocken Zustand des Managers aus der Registrierung.|  
|[CDockingManager::LockUpdate](../Topic/CDockingManager::LockUpdate.md)|Sperrt das angegebene Fenster.|  
|[CDockingManager::OnActivateFrame](../Topic/CDockingManager::OnActivateFrame.md)|Aufgerufen vom Framework, wenn das Rahmenfenster aktiv hergestellt wird oder deaktiviert wird.|  
|[CDockingManager::OnClosePopupMenu](../Topic/CDockingManager::OnClosePopupMenu.md)|Aufgerufen vom Framework ausgelöst, wenn ein aktives Popupmenü eine WM\_DESTROY\-Meldung verarbeitet.|  
|[CDockingManager::OnMoveMiniFrame](../Topic/CDockingManager::OnMoveMiniFrame.md)|Aufgerufen vom Framework, um ein Minirahmenfenster zu verschieben.|  
|[CDockingManager::OnPaneContextMenu](../Topic/CDockingManager::OnPaneContextMenu.md)|Aufgerufen vom Framework, wenn ein Menü erstellt, das eine Liste von Bereichen umfasst.|  
|[CDockingManager::PaneFromPoint](../Topic/CDockingManager::PaneFromPoint.md)|Gibt den Bereich zurück, der den angegebenen Punkt enthält.|  
|[CDockingManager::ProcessPaneContextMenuCommand](../Topic/CDockingManager::ProcessPaneContextMenuCommand.md)|Aufgerufen durch das Framework, um ein Kontrollkästchen für den angegebenen Befehl auswählen oder löschen und das Layout eines angezeigten Bereichs neu zu berechnen.|  
|[CDockingManager::RecalcLayout](../Topic/CDockingManager::RecalcLayout.md)|Berechnet das interne Layout der Steuerelemente neu in der Liste der Steuerelemente vorhanden sind.|  
|[CDockingManager::ReleaseEmptyPaneContainers](../Topic/CDockingManager::ReleaseEmptyPaneContainers.md)|Gibt die leeren Bereichscontainer frei.|  
|[CDockingManager::RemoveHiddenMDITabbedBar](../Topic/CDockingManager::RemoveHiddenMDITabbedBar.md)|Entfernt den angegebenen ausgeblendeten Leistebereich.|  
|[CDockingManager::RemoveMiniFrame](../Topic/CDockingManager::RemoveMiniFrame.md)|Entfernt angegebene Frame aus der Liste der Miniframen.|  
|[CDockingManager::RemovePaneFromDockManager](../Topic/CDockingManager::RemovePaneFromDockManager.md)|Hebt einen Bereich Registrierung auf und entfernt sie aus der Liste im Andocken Manager.|  
|[CDockingManager::ReplacePane](../Topic/CDockingManager::ReplacePane.md)|Ersetzt einen Bereich von anderen.|  
|[CDockingManager::ResortMiniFramesForZOrder](../Topic/CDockingManager::ResortMiniFramesForZOrder.md)|Sortieren der Frame in der Liste der Miniframen neu.|  
|[CDockingManager::SaveState](../Topic/CDockingManager::SaveState.md)|Rettet Andocken den Zustand des Managers in die Registrierung.|  
|[CDockingManager::SendMessageToMiniFrames](../Topic/CDockingManager::SendMessageToMiniFrames.md)|Sendet die angegebene Meldung auf alle Miniframen.|  
|[CDockingManager::Serialize](../Topic/CDockingManager::Serialize.md)|Schreibt den Andocken Manager zu einem Archiv.  \(Überschreibungen [CObject::Serialize](../Topic/CObject::Serialize.md).\)|  
|[CDockingManager::SetAutohideZOrder](../Topic/CDockingManager::SetAutohideZOrder.md)|Legt die Größe, die Breite und Höhe der Steuerleisten und des angegebenen Bereichs fest.|  
|[CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md)|Legt den Andockmodus fest.|  
|[CDockingManager::SetDockState](../Topic/CDockingManager::SetDockState.md)|Legt den angedockten Zustand der Steuerleisten, der Miniframe und der Balken der automatischen Ausblenden fest.|  
|[CDockingManager::SetPrintPreviewMode](../Topic/CDockingManager::SetPrintPreviewMode.md)|Legt den Seitenansichtsmodus der Balken fest, die in der Seitenansicht angezeigt werden.|  
|[CDockingManager::SetSmartDockingParams](../Topic/CDockingManager::SetSmartDockingParams.md)|Legt die Parameter fest, die das Verhalten des intelligenten durch Andocken definieren.|  
|[CDockingManager::ShowDelayShowMiniFrames](../Topic/CDockingManager::ShowDelayShowMiniFrames.md)|In oder aus die Fenster der Miniframe.|  
|[CDockingManager::ShowPanes](../Topic/CDockingManager::ShowPanes.md)|In oder aus die Bereiche der Steuerelement\- und der automatischen Ausblendenleisten.|  
|[CDockingManager::StartSDocking](../Topic/CDockingManager::StartSDocking.md)|Startet das intelligente Andocken des angegebenen Fensters entsprechend der Ausrichtung des intelligenten Andocken Managers.|  
|[CDockingManager::StopSDocking](../Topic/CDockingManager::StopSDocking.md)|Beendet intelligente Andocken.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDockingManager::m\_bHideDockingBarsInContainerMode](../Topic/CDockingManager::m_bHideDockingBarsInContainerMode.md)|Gibt an, ob der andockbare Manager Bereiche im OLE\-Containermodus ausblendet.|  
|[CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md)|Gibt den globalen Andockmodus an.|  
|[CDockingManager::m\_nDockSensitivity](../Topic/CDockingManager::m_nDockSensitivity.md)|Gibt die andockbare Empfindlichkeit an.|  
|[CDockingManager::m\_nTimeOutBeforeDockingBarDock](../Topic/CDockingManager::m_nTimeOutBeforeDockingBarDock.md)|Gibt die Zeit, in Millisekunden, bevor ein Andocker Bereich in unmittelbaren Andockmodus angedockt ist.|  
|[CDockingManager::m\_nTimeOutBeforeToolBarDock](../Topic/CDockingManager::m_nTimeOutBeforeToolBarDock.md)|Gibt die Zeit, in Millisekunden, bevor eine Symbolleiste an das Hauptrahmenfenster angedockt ist.|  
  
## Hinweise  
 Das Hauptrahmenfenster erstellt und initialisiert diese Klasse automatisch.  
  
 Das andockbare Managerobjekt enthält eine Liste aller Bereiche, die im Andocken Layout sind, sowie eine Liste aller [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md) Fenster an, die dem Hauptrahmenfenster gehören.  
  
 Die `CDockingManager`\-Klasse implementiert einige Dienste, die Sie verwenden können, um einen Bereich oder ein `CPaneFrameWnd` Fenster zu suchen.  Sie rufen diese Dienste normalerweise nicht direkt auf, da sie im Hauptrahmenfensterobjekt umschlossen werden.  Weitere Informationen finden Sie unter [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  
  
## Anpassungs\-Tipps  
 Die folgenden Tipps gelten für `CDockingManager`\-Objekte:  
  
-   [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) unterstützt diese Andocken Modi:  
  
    -   `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    -   `AFX_DOCK_TYPE::DT_STANDARD`  
  
    -   `AFX_DOCK_TYPE::DT_SMART`  
  
     Diese Andocken Modi werden durch [CDockingManager::m\_dockModeGlobal](../Topic/CDockingManager::m_dockModeGlobal.md) definiert und festgelegt, indem [CDockingManager::SetDockingMode](../Topic/CDockingManager::SetDockingMode.md) aufruft.  
  
-   Wenn Sie einen nicht\-unverankerten, nicht\-inder Größe veränderbaren Bereich erstellen möchten, rufen Sie die [CDockingManager::AddPane](../Topic/CDockingManager::AddPane.md)\-Methode auf.  Diese Methode registriert den Bereich mit dem Andocken Manager, der für das Layout des Bereichs zuständig ist.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der `CDockingManager`\-Klasse verwendet, um ein `CDockingManager`\-Objekt zu konfigurieren.  Im Beispiel wird gezeigt, wie eine weitere Schaltfläche anzeigt, die ein Popupmenü auf den Beschriftungen aller Andocken Bereiche geöffnet und wie den Andockmodus des Objekts festgelegt.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#24](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#24)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## Anforderungen  
 **Header:** afxDockingManager.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)