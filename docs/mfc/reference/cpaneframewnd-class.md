---
title: "CPaneFrameWnd Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CPaneFrameWnd.Serialize"
  - "CPaneFrameWnd.PreTranslateMessage"
  - "CPaneFrameWnd"
  - "CPaneFrameWnd::Serialize"
  - "PreTranslateMessage"
  - "CPaneFrameWnd::PreTranslateMessage"
  - "Serialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneFrameWnd class"
  - "PreTranslateMessage method"
  - "Serialize method"
ms.assetid: ea3423a3-2763-482e-b763-817036ded10d
caps.latest.revision: 28
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Implementiert ein Minirahmenfenster, das einen Bereich enthält.  Der Bereich füllt den Clientbereich des Fensters aus.  
  
## Syntax  
  
```  
class CPaneFrameWnd : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CPaneFrameWnd::AddPane](../Topic/CPaneFrameWnd::AddPane.md)|Fügt einen Bereich hinzu.|  
|[CPaneFrameWnd::AddRemovePaneFromGlobalList](../Topic/CPaneFrameWnd::AddRemovePaneFromGlobalList.md)|Fügt einen Bereich zur globalen Liste hinzu oder entfernt ihn daraus.|  
|[CPaneFrameWnd::AdjustLayout](../Topic/CPaneFrameWnd::AdjustLayout.md)|Passt das Layout des Minirahmenfensters an.|  
|[CPaneFrameWnd::AdjustPaneFrames](../Topic/CPaneFrameWnd::AdjustPaneFrames.md)||  
|[CPaneFrameWnd::CalcBorderSize](../Topic/CPaneFrameWnd::CalcBorderSize.md)|Berechnet die Größe der Rahmen für ein Minirahmenfenster.|  
|[CPaneFrameWnd::CalcExpectedDockedRect](../Topic/CPaneFrameWnd::CalcExpectedDockedRect.md)|Berechnet das erwartete Rechteck eines angedockten Fensters.|  
|[CPaneFrameWnd::CanBeAttached](../Topic/CPaneFrameWnd::CanBeAttached.md)|Bestimmt, ob der aktuelle Bereich an einen anderen Bereich oder an ein Framefenster angedockt werden kann.|  
|[CPaneFrameWnd::CanBeDockedToPane](../Topic/CPaneFrameWnd::CanBeDockedToPane.md)|Bestimmt, ob das Minirahmenfenster an einen Bereich angedockt werden kann.|  
|[CPaneFrameWnd::CheckGripperVisibility](../Topic/CPaneFrameWnd::CheckGripperVisibility.md)||  
|[CPaneFrameWnd::ConvertToTabbedDocument](../Topic/CPaneFrameWnd::ConvertToTabbedDocument.md)|Konvertiert den Bereich in ein Dokument mit Registerkarten.|  
|[CPaneFrameWnd::Create](../Topic/CPaneFrameWnd::Create.md)|Erstellt ein Minirahmenfenster und fügt es dem `CPaneFrameWnd`\-Objekt an.|  
|[CPaneFrameWnd::CreateEx](../Topic/CPaneFrameWnd::CreateEx.md)|Erstellt ein Minirahmenfenster und fügt es dem `CPaneFrameWnd`\-Objekt an.|  
|[CPaneFrameWnd::DockPane](../Topic/CPaneFrameWnd::DockPane.md)|Dockt den Bereich an.|  
|[CPaneFrameWnd::FindFloatingPaneByID](../Topic/CPaneFrameWnd::FindFloatingPaneByID.md)|Sucht einen Bereich mit der angegebenen Steuerelement\-ID in der globalen Liste unverankerter Bereiche.|  
|[CPaneFrameWnd::FrameFromPoint](../Topic/CPaneFrameWnd::FrameFromPoint.md)|Sucht das Minirahmenfenster mit einem vom Benutzer angegebenen Punkt.|  
|[CPaneFrameWnd::GetCaptionHeight](../Topic/CPaneFrameWnd::GetCaptionHeight.md)|Gibt die Höhe der Beschriftung des Minirahmenfensters zurück.|  
|[CPaneFrameWnd::GetCaptionRect](../Topic/CPaneFrameWnd::GetCaptionRect.md)|Berechnet das umschließende Rechteck der Beschriftung eines Minirahmenfensters.|  
|[CPaneFrameWnd::GetCaptionText](../Topic/CPaneFrameWnd::GetCaptionText.md)|Gibt den Beschriftungstext zurück.|  
|[CPaneFrameWnd::GetDockingManager](../Topic/CPaneFrameWnd::GetDockingManager.md)||  
|[CPaneFrameWnd::GetDockingMode](../Topic/CPaneFrameWnd::GetDockingMode.md)|Gibt den Andockmodus zurück.|  
|[CPaneFrameWnd::GetFirstVisiblePane](../Topic/CPaneFrameWnd::GetFirstVisiblePane.md)|Gibt den ersten sichtbaren Bereich zurück, der in einem Minirahmenfenster enthalten ist.|  
|[CPaneFrameWnd::GetHotPoint](../Topic/CPaneFrameWnd::GetHotPoint.md)||  
|[CPaneFrameWnd::GetPane](../Topic/CPaneFrameWnd::GetPane.md)|Gibt einen Bereich zurück, der im Minirahmenfenster enthalten ist.|  
|[CPaneFrameWnd::GetPaneCount](../Topic/CPaneFrameWnd::GetPaneCount.md)|Gibt die Anzahl der Bereiche zurück, die im Minirahmenfenster enthalten sind.|  
|[CPaneFrameWnd::GetParent](../Topic/CPaneFrameWnd::GetParent.md)||  
|[CPaneFrameWnd::GetPinState](../Topic/CPaneFrameWnd::GetPinState.md)||  
|[CPaneFrameWnd::GetRecentFloatingRect](../Topic/CPaneFrameWnd::GetRecentFloatingRect.md)||  
|[CPaneFrameWnd::GetVisiblePaneCount](../Topic/CPaneFrameWnd::GetVisiblePaneCount.md)|Gibt die Anzahl der sichtbaren Bereiche zurück, die im Minirahmenfenster enthalten sind.|  
|[CPaneFrameWnd::HitTest](../Topic/CPaneFrameWnd::HitTest.md)|Bestimmt, welcher Teil eines Minirahmenfensters sich an einem bestimmten Punkt befindet.|  
|[CPaneFrameWnd::IsCaptured](../Topic/CPaneFrameWnd::IsCaptured.md)||  
|[CPaneFrameWnd::IsDelayShow](../Topic/CPaneFrameWnd::IsDelayShow.md)||  
|[CPaneFrameWnd::IsRollDown](../Topic/CPaneFrameWnd::IsRollDown.md)|Bestimmt, ob ein Minirahmenfenster abwärts zugeordnet werden soll.|  
|[CPaneFrameWnd::IsRollUp](../Topic/CPaneFrameWnd::IsRollUp.md)|Bestimmt, ob ein Minirahmenfenster aufwärts zugeordnet werden soll.|  
|[CPaneFrameWnd::KillDockingTimer](../Topic/CPaneFrameWnd::KillDockingTimer.md)|Hält den Andocktimer an.|  
|[CPaneFrameWnd::LoadState](../Topic/CPaneFrameWnd::LoadState.md)|Lädt den Zustand des Bereichs aus der Registrierung.|  
|[CPaneFrameWnd::OnBeforeDock](../Topic/CPaneFrameWnd::OnBeforeDock.md)|Bestimmt, ob Andocken möglich ist.|  
|[CPaneFrameWnd::OnDockToRecentPos](../Topic/CPaneFrameWnd::OnDockToRecentPos.md)|Dockt das Minirahmenfenster an der letzten Position an.|  
|[CPaneFrameWnd::OnKillRollUpTimer](../Topic/CPaneFrameWnd::OnKillRollUpTimer.md)|Hält den Rolluptimer an.|  
|[CPaneFrameWnd::OnMovePane](../Topic/CPaneFrameWnd::OnMovePane.md)|Verschiebt das Minirahmenfenster anhand eines angegebenen Offsets.|  
|[CPaneFrameWnd::OnPaneRecalcLayout](../Topic/CPaneFrameWnd::OnPaneRecalcLayout.md)|Passt das Layout eines enthaltenen Bereichs an.|  
|[CPaneFrameWnd::OnSetRollUpTimer](../Topic/CPaneFrameWnd::OnSetRollUpTimer.md)|Richtet den Rolluptimer ein.|  
|[CPaneFrameWnd::OnShowPane](../Topic/CPaneFrameWnd::OnShowPane.md)|Wird vom Framework aufgerufen, wenn ein Bereich im Minirahmenfenster angezeigt oder ausgeblendet wird.|  
|[CPaneFrameWnd::PaneFromPoint](../Topic/CPaneFrameWnd::PaneFromPoint.md)|Gibt einen Bereich zurück, wenn er einen vom Benutzer angegebenen Punkt innerhalb einer Minirahmenfensters enthält.|  
|[CPaneFrameWnd::Pin](../Topic/CPaneFrameWnd::Pin.md)||  
|`CPaneFrameWnd::PreTranslateMessage`|Wird von der Klasse [CWinApp](../../mfc/reference/cwinapp-class.md) verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows\-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden.|  
|[CPaneFrameWnd::RedrawAll](../Topic/CPaneFrameWnd::RedrawAll.md)|Zeichnet alle Minirahmenfenster neu.|  
|[CPaneFrameWnd::RemoveNonValidPanes](../Topic/CPaneFrameWnd::RemoveNonValidPanes.md)|Wird vom Framework aufgerufen, um ungültige Bereiche zu entfernen.|  
|[CPaneFrameWnd::RemovePane](../Topic/CPaneFrameWnd::RemovePane.md)|Entfernt einen Bereich aus dem Minirahmenfenster.|  
|[CPaneFrameWnd::ReplacePane](../Topic/CPaneFrameWnd::ReplacePane.md)|Ersetzt einen Bereich durch einen anderen.|  
|[CPaneFrameWnd::SaveState](../Topic/CPaneFrameWnd::SaveState.md)|Speichert den Zustand des Bereichs in der Registrierung.|  
|`CPaneFrameWnd::Serialize`|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv.|  
|[CPaneFrameWnd::SetCaptionButtons](../Topic/CPaneFrameWnd::SetCaptionButtons.md)|Legt Beschriftungsschaltflächen fest.|  
|[CPaneFrameWnd::SetDelayShow](../Topic/CPaneFrameWnd::SetDelayShow.md)||  
|[CPaneFrameWnd::SetDockingManager](../Topic/CPaneFrameWnd::SetDockingManager.md)||  
|[CPaneFrameWnd::SetDockingTimer](../Topic/CPaneFrameWnd::SetDockingTimer.md)|Legt den Andocktimer fest.|  
|[CPaneFrameWnd::SetDockState](../Topic/CPaneFrameWnd::SetDockState.md)|Legt den Andockzustand fest.|  
|[CPaneFrameWnd::SetHotPoint](../Topic/CPaneFrameWnd::SetHotPoint.md)||  
|[CPaneFrameWnd::SetPreDockState](../Topic/CPaneFrameWnd::SetPreDockState.md)|Wird vom Framework aufgerufen, um den Zustand vor dem Andocken festzulegen.|  
|[CPaneFrameWnd::SizeToContent](../Topic/CPaneFrameWnd::SizeToContent.md)|Passt die Größe eines Minirahmenfensters an, damit es in der Größe einem enthaltenen Bereich entspricht.|  
|[CPaneFrameWnd::StartTearOff](../Topic/CPaneFrameWnd::StartTearOff.md)|Schneidet ein Menü ab.|  
|[CPaneFrameWnd::StoreRecentDockSiteInfo](../Topic/CPaneFrameWnd::StoreRecentDockSiteInfo.md)||  
|[CPaneFrameWnd::StoreRecentTabRelatedInfo](../Topic/CPaneFrameWnd::StoreRecentTabRelatedInfo.md)||  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CPaneFrameWnd::OnCheckRollState](../Topic/CPaneFrameWnd::OnCheckRollState.md)|Bestimmt, ob ein Minirahmenfenster aufwärts oder abwärts zugeordnet werden soll.|  
|[CPaneFrameWnd::OnDrawBorder](../Topic/CPaneFrameWnd::OnDrawBorder.md)|Zeichnet die Rahmen eines Minirahmenfensters.|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CPaneFrameWnd::m\_bUseSaveBits](../Topic/CPaneFrameWnd::m_bUseSaveBits.md)|Gibt an, ob die Fensterklasse mit dem `CS_SAVEBITS`\-Klassenformat registriert werden soll.|  
  
## Hinweise  
 Das Framework erstellt automatisch ein `CPaneFrameWnd`\-Objekt, wenn ein Bereich aus einem angedockten Zustand in einen unverankerten Zustand wechselt.  
  
 Ein Minirahmenfenster kann mit sichtbarem Inhalt \(sofortiges Andocken\) oder mit einem Rechteck \(standardmäßiges Andocken\) gezogen werden.  Der Andockmodus des Containerbereichs des Minirahmenfensters bestimmt das Ziehverhalten des Minirahmens.  Weitere Informationen finden Sie unter [CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md).  
  
 Ein Minirahmenfenster zeigt Schaltflächen auf der Beschriftung in Übereinstimmung mit den enthaltenen Bereichsformat an.  Wenn der Bereich geschlossen werden kann \([CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md)\), wird eine Schaltfläche "Schließen" angezeigt.  Wenn der Bereich das `AFX_CBRS_AUTO_ROLLUP`\-Format aufweist, wird ein Pin angezeigt.  
  
 Wenn Sie eine Klasse von `CPaneFrameWnd` ableiten, müssen Sie dem Framework die Erstellung erläutern.  Erstellen Sie die Klasse durch Überschreiben von [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md), oder legen Sie den `CPane::m_pMiniFrameRTC`\-Member so fest, dass er auf die Laufzeit\-Klasseninformationen für die Klasse verweist.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)  
  
## Anforderungen  
 **Header:** afxPaneFrameWnd.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)