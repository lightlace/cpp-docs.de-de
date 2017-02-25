---
title: "CMultiPaneFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiPaneFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPaneFrameWnd class"
ms.assetid: 989a548e-0d70-46b7-a513-8cf740e1be3e
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMultiPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMultiPaneFrameWnd`\-Klasse erweitert [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md).  Sie kann mehrere Bereiche unterstützen.  Anstelle eines einzelnen eingebetteten Handles zu einer Steuerleiste, enthält `CMultiPaneFrameWnd`[CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md) ein Objekt, das den Benutzer ermöglicht, ein `CMultiPaneFrameWnd` zu anderen anzudocken und das mehrere unverankert dynamisch erstellen, Fenster im Registerkartenformat.  
  
## Syntax  
  
```  
class CMultiPaneFrameWnd : public CPaneFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMultiPaneFrameWnd::AddPane](../Topic/CMultiPaneFrameWnd::AddPane.md)|Fügt einen Bereich hinzu.  \(Überschreibungen [CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md).\)|  
|[CMultiPaneFrameWnd::AddRecentPane](../Topic/CMultiPaneFrameWnd::AddRecentPane.md)||  
|[CMultiPaneFrameWnd::AdjustLayout](../Topic/CMultiPaneFrameWnd::AdjustLayout.md)|Passt das Layout des Minirahmenfensters.  \(Überschreibungen [CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md).\)|  
|[CMultiPaneFrameWnd::AdjustPaneFrames](../Topic/CMultiPaneFrameWnd::AdjustPaneFrames.md)|\(Überschreibungen [CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md).\)|  
|[CMultiPaneFrameWnd::CalcExpectedDockedRect](../Topic/CMultiPaneFrameWnd::CalcExpectedDockedRect.md)|Berechnet das erwartete Rechteck eines angedockten Fenster.  \(Überschreibungen [CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md).\)|  
|[CMultiPaneFrameWnd::CanBeAttached](../Topic/CMultiPaneFrameWnd::CanBeAttached.md)|Bestimmt, ob der aktuelle Bereich zu einem anderen Bereich oder zu Rahmenfenster andocken kann.  \(Überschreibungen [CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md).\)|  
|[CMultiPaneFrameWnd::CanBeDockedToPane](../Topic/CMultiPaneFrameWnd::CanBeDockedToPane.md)|Bestimmt, ob das Minirahmenfenster auf einen Bereich andocken kann.  \(Überschreibungen [CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md).\)|  
|[CMultiPaneFrameWnd::CheckGripperVisibility](../Topic/CMultiPaneFrameWnd::CheckGripperVisibility.md)|\(Überschreibungen [CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md).\)|  
|[CMultiPaneFrameWnd::CloseMiniFrame](../Topic/CMultiPaneFrameWnd::CloseMiniFrame.md)|\(Überschreibungen `CPaneFrameWnd::CloseMiniFrame`.\)|  
|[CMultiPaneFrameWnd::ConvertToTabbedDocument](../Topic/CMultiPaneFrameWnd::ConvertToTabbedDocument.md)|Konvertiert den Bereich zu einem Dokument im Registerkartenformat.  \(Überschreibungen [CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md).\)|  
|[CMultiPaneFrameWnd::DockFrame](../Topic/CMultiPaneFrameWnd::DockFrame.md)||  
|[CMultiPaneFrameWnd::DockPane](../Topic/CMultiPaneFrameWnd::DockPane.md)|Dockt den Bereich an.  \(Überschreibungen [CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md).\)|  
|[CMultiPaneFrameWnd::DockRecentPaneToMainFrame](../Topic/CMultiPaneFrameWnd::DockRecentPaneToMainFrame.md)||  
|[CMultiPaneFrameWnd::GetCaptionText](../Topic/CMultiPaneFrameWnd::GetCaptionText.md)|Gibt den Beschriftungstext zurück.  \(Überschreibungen [CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md).\)|  
|[CMultiPaneFrameWnd::GetPaneContainerManager](../Topic/CMultiPaneFrameWnd::GetPaneContainerManager.md)|Gibt einen Verweis auf den internen Containermanagerobjekt zurück.|  
|[CMultiPaneFrameWnd::GetFirstVisiblePane](../Topic/CMultiPaneFrameWnd::GetFirstVisiblePane.md)|Gibt den ersten sichtbaren Bereich zurück, der in einem Minirahmenfenster enthalten ist.  \(Überschreibungen [CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md).\)|  
|[CMultiPaneFrameWnd::GetPane](../Topic/CMultiPaneFrameWnd::GetPane.md)|Gibt einen Bereich zurück, der im Minirahmenfenster enthalten ist.  \(Überschreibungen [CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md).\)|  
|[CMultiPaneFrameWnd::GetPaneCount](../Topic/CMultiPaneFrameWnd::GetPaneCount.md)|Gibt die Anzahl von Bereichen zurück, die in einem Minirahmenfenster enthalten sind.  \(Überschreibungen [CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md).\)|  
|[CMultiPaneFrameWnd::GetVisiblePaneCount](../Topic/CMultiPaneFrameWnd::GetVisiblePaneCount.md)|Gibt die Anzahl der sichtbaren Bereichen zurück, die in einem Minirahmenfenster enthalten sind.  \(Überschreibungen [CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md).\)|  
|[CMultiPaneFrameWnd::InsertPane](../Topic/CMultiPaneFrameWnd::InsertPane.md)||  
|[CMultiPaneFrameWnd::LoadState](../Topic/CMultiPaneFrameWnd::LoadState.md)|Lädt den Zustand des Bereichs aus der Registrierung.  \(Überschreibungen [CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md).\)|  
|[CMultiPaneFrameWnd::OnDockToRecentPos](../Topic/CMultiPaneFrameWnd::OnDockToRecentPos.md)|Dockt das Minirahmenfenster in seiner letzten Speicherort an.  \(Überschreibungen [CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md).\)|  
|[CMultiPaneFrameWnd::OnKillRollUpTimer](../Topic/CMultiPaneFrameWnd::OnKillRollUpTimer.md)|Beendet den Rollupzeitgeber.  \(Überschreibungen [CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md).\)|  
|[CMultiPaneFrameWnd::OnPaneRecalcLayout](../Topic/CMultiPaneFrameWnd::OnPaneRecalcLayout.md)|Passt das Layout eines Bereichs innerhalb eines Minirahmenfensters.  \(Überschreibungen [CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md).\)|  
|[CMultiPaneFrameWnd::OnSetRollUpTimer](../Topic/CMultiPaneFrameWnd::OnSetRollUpTimer.md)|Legt den Rollupzeitgeber fest.  \(Überschreibungen [CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md).\)|  
|[CMultiPaneFrameWnd::OnShowPane](../Topic/CMultiPaneFrameWnd::OnShowPane.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereich im Minirahmenfenster ausgeblendet oder angezeigt wird.  \(Überschreibungen [CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md).\)|  
|[CMultiPaneFrameWnd::PaneFromPoint](../Topic/CMultiPaneFrameWnd::PaneFromPoint.md)|Gibt einen Bereich zurück, wenn er einen vom Benutzer angegebenen Punkt innerhalb eines Minirahmenfensters enthält.  \(Überschreibungen [CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md).\)|  
|[CMultiPaneFrameWnd::RemoveNonValidPanes](../Topic/CMultiPaneFrameWnd::RemoveNonValidPanes.md)|Aufgerufen durch das Framework, um nicht\-gültige Bereiche zu entfernen.  \(Überschreibungen [CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md).\)|  
|[CMultiPaneFrameWnd::RemovePane](../Topic/CMultiPaneFrameWnd::RemovePane.md)|Entfernt einen Bereich von Minirahmenfenster.  \(Überschreibungen [CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md).\)|  
|[CMultiPaneFrameWnd::ReplacePane](../Topic/CMultiPaneFrameWnd::ReplacePane.md)|Ersetzt einen Bereich von anderen.  \(Überschreibungen [CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md).\)|  
|[CMultiPaneFrameWnd::SaveState](../Topic/CMultiPaneFrameWnd::SaveState.md)|Rettet den Zustand des Bereichs in die Registrierung.  \(Überschreibungen [CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md).\)|  
|[CMultiPaneFrameWnd::Serialize](../Topic/CMultiPaneFrameWnd::Serialize.md)|\(Überschreibungen `CPaneFrameWnd::Serialize`.\)|  
|[CMultiPaneFrameWnd::SetDockState](../Topic/CMultiPaneFrameWnd::SetDockState.md)|Legt den angedockten Zustand.  \(Überschreibungen [CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md).\)|  
|[CMultiPaneFrameWnd::SetLastFocusedPane](../Topic/CMultiPaneFrameWnd::SetLastFocusedPane.md)||  
|[CMultiPaneFrameWnd::SetPreDockState](../Topic/CMultiPaneFrameWnd::SetPreDockState.md)|Legt den predocking Zustand.  \(Überschreibungen [CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md).\)|  
|[CMultiPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CMultiPaneFrameWnd::StoreRecentDockSiteInfo.md)|\(Überschreibungen [CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md).\)|  
|[CMultiPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CMultiPaneFrameWnd::StoreRecentTabRelatedInfo.md)|\(Überschreibungen [CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md).\)|  
  
## Hinweise  
 Die meisten Methoden in den Methoden dieser betreffende Klasse überschreibt in der [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)\-Klasse.  
  
 Wenn ein Bereich `AFX_CBRS_AUTO_ROLLUP` das Format und die Benutzerdocks verwendet, die Bereich zu einem Rahmenfenster mit mehreren Bereichen, der Benutzer das Fenster unabhängig von der Stileinstellungen der anderen angedockten Bereiche oben bewegen kann.  
  
 Das Framework erstellt automatisch ein Objekt `CMultiPaneFrameWnd`, wenn der Benutzer einen Bereich an, der das `CBRS_FLOAT_MULTI` Format verwendet.  
  
 Informationen über eine Klasse von der Klasse `CPaneFrameWnd` dynamisch berechnen und diese erstellen, finden Sie unter [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Zeiger auf einen `CMultiPaneFrameWnd`\-Objekt abrufen.  Dieser Codeausschnitt ist Teil [Legen Sie Bereichs\-Größenbeispiel fest](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_SetPaneSize#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_SetPaneSize#4)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
 [CMultiPaneFrameWnd](../../mfc/reference/cmultipaneframewnd-class.md)  
  
## Anforderungen  
 **Header:** afxMultiPaneFrameWnd.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)