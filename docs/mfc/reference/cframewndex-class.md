---
title: "CFrameWndEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFrameWndEx class"
ms.assetid: 5830aca8-4a21-4f31-91f1-dd5477ffcc8d
caps.latest.revision: 39
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 41
---
# CFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktion eines Windows\-SingleDocument Interface \(SDI\) nicht überschnitt oder von Popups Rahmenfenster und Bereitstellen Member zum Verwalten des Fensters.  Es [CFrameWnd](../../mfc/reference/cframewnd-class.md) erweitert die Klasse.  
  
## Syntax  
  
```  
class CFrameWndEx : public CFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFrameWndEx::ActiveItemRecalcLayout](../Topic/CFrameWndEx::ActiveItemRecalcLayout.md)|Passt das Layout des OLE\-Clientelements und des Clientbereichs des Frames.|  
|`CFrameWndEx::AddDockSite`|Diese Methode wird nicht verwendet.|  
|[CFrameWndEx::AddPane](../Topic/CFrameWndEx::AddPane.md)|Registriert eine Steuerleiste mit dem Andocken Manager.|  
|[CFrameWndEx::AdjustDockingLayout](../Topic/CFrameWndEx::AdjustDockingLayout.md)|Berechnet das Layout aller Bereiche neu die im Rahmenfenster angedockt werden.|  
|[CFrameWndEx::DelayUpdateFrameMenu](../Topic/CFrameWndEx::DelayUpdateFrameMenu.md)|Legt das Framemenü und dann \-Updates es fest, wenn das Befehlsverarbeiten im Leerlauf befindet.|  
|[CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md)|Dockt den angegebenen Bereich an das Rahmenfenster an.|  
|[CFrameWndEx::DockPaneLeftOf](../Topic/CFrameWndEx::DockPaneLeftOf.md)|wird ein Bereich auf der linken Seite eines anderen Bereichs.|  
|[CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md)|Aktiviert den Modus "Automatisches Ausblenden" für die Bereiche, wenn sie angegebenen Seiten des Hauptrahmenfensters angedockt werden.|  
|[CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md)|Ermöglicht das Andocken der Bereiche, die dem Rahmenfenster gehören.|  
|[CFrameWndEx::EnableFullScreenMainMenu](../Topic/CFrameWndEx::EnableFullScreenMainMenu.md)|In oder aus dem Hauptmenü in einem Ganzseitenmodus.|  
|[CFrameWndEx::EnableFullScreenMode](../Topic/CFrameWndEx::EnableFullScreenMode.md)|Aktiviert den Ganzseitenmodus für das Rahmenfenster.|  
|[CFrameWndEx::EnableLoadDockState](../Topic/CFrameWndEx::EnableLoadDockState.md)|Aktiviert oder deaktiviert das Laden des angedockten Zustand.|  
|[CFrameWndEx::EnablePaneMenu](../Topic/CFrameWndEx::EnablePaneMenu.md)|Aktiviert oder deaktiviert die automatische Behandlung des Bereichsmenü.|  
|[CFrameWndEx::GetActivePopup](../Topic/CFrameWndEx::GetActivePopup.md)|Gibt einen Zeiger auf aktuell angezeigten Popupmenü zurück.|  
|[CFrameWndEx::GetDefaultResId](../Topic/CFrameWndEx::GetDefaultResId.md)|Gibt das diese Ressourcen\-ID Sie zurück, als das Framework Rahmenfenster geladen wurde.|  
|[CFrameWndEx::GetDockingManager](../Topic/CFrameWndEx::GetDockingManager.md)|Ruft das Objekt [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md) für das Rahmenfenster ab.|  
|[CFrameWndEx::GetMenuBar](../Topic/CFrameWndEx::GetMenuBar.md)|Gibt einen Zeiger auf Menüleistenobjekt zurück, das an das Rahmenfenster angefügt wird.|  
|[CFrameWndEx::GetPane](../Topic/CFrameWndEx::GetPane.md)|Gibt einen Zeiger auf Bereich zurück, der die angegebene ID besitzt|  
|[CFrameWndEx::GetRibbonBar](../Topic/CFrameWndEx::GetRibbonBar.md)|Ruft das Menübandleistesteuerelement für die Frames ab.|  
|[CFrameWndEx::GetTearOffBars](../Topic/CFrameWndEx::GetTearOffBars.md)|Gibt eine Liste von Bereichsobjekten zurück, die in einem Tearoffen Zustand sind.|  
|[CFrameWndEx::GetToolbarButtonToolTipText](../Topic/CFrameWndEx::GetToolbarButtonToolTipText.md)|Aufgerufen vom Framework, wenn die Anwendung die QuickInfo für eine Symbolleisten\-Schaltfläche anzeigt.|  
|[CFrameWndEx::InsertPane](../Topic/CFrameWndEx::InsertPane.md)|Registriert einen Bereich mit dem Andocken Manager.|  
|[CFrameWndEx::IsFullScreen](../Topic/CFrameWndEx::IsFullScreen.md)|Bestimmt, ob das Rahmenfenster im Ganzseitenmodus ist.|  
|[CFrameWndEx::IsMenuBarAvailable](../Topic/CFrameWndEx::IsMenuBarAvailable.md)|Bestimmt, ob der Zeiger auf Menüleistenobjekt gültig ist.|  
|[CFrameWndEx::IsPointNearDockSite](../Topic/CFrameWndEx::IsPointNearDockSite.md)|Gibt an, ob der Punkt in einer Ausrichtungszone ist.|  
|[CFrameWndEx::IsPrintPreview](../Topic/CFrameWndEx::IsPrintPreview.md)|Gibt an, ob das Rahmenfenster in der Seitenansicht ist.|  
|[CFrameWndEx::LoadFrame](../Topic/CFrameWndEx::LoadFrame.md)|Diese Methode wird nach Konstruktion aufgerufen, um das Rahmenfenster zu erstellen und seine Ressourcen zu laden.|  
|[CFrameWndEx::NegotiateBorderSpace](../Topic/CFrameWndEx::NegotiateBorderSpace.md)|Client\-Rahmenaushandlung implementiert der OLE.|  
|[CFrameWndEx::OnActivate](../Topic/CFrameWndEx::OnActivate.md)|Das Framework ruft diese Methode auf, wenn Benutzereingaben oder vom auf Frames gewechselt wird.|  
|[CFrameWndEx::OnActivateApp](../Topic/CFrameWndEx::OnActivateApp.md)|Aufgerufen vom Framework, wenn die Anwendung entweder aktiviert oder deaktiviert wird.|  
|[CFrameWndEx::OnChangeVisualManager](../Topic/CFrameWndEx::OnChangeVisualManager.md)|Aufgerufen vom Framework, wenn eine Änderung an den Frames eine Änderung am visuellen Manager erfordert.|  
|[CFrameWndEx::OnClose](../Topic/CFrameWndEx::OnClose.md)|Das Framework ruft diese Methode auf, um die Frames zu schließen.|  
|[CFrameWndEx::OnCloseDockingPane](../Topic/CFrameWndEx::OnCloseDockingPane.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Schließen** auf einem Hauptandockbereich klickt.|  
|[CFrameWndEx::OnCloseMiniFrame](../Topic/CFrameWndEx::OnCloseMiniFrame.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Schließen** auf einem beweglichen Minirahmenfenster klickt.|  
|[CFrameWndEx::OnClosePopupMenu](../Topic/CFrameWndEx::OnClosePopupMenu.md)|Aufgerufen vom Framework ausgelöst, wenn ein aktives Popupmenü eine WM\_DESTROY\-Meldung verarbeitet.|  
|[CFrameWndEx::OnCmdMsg](../Topic/CFrameWndEx::OnCmdMsg.md)|Dispatchbefehlsmeldungen.|  
|[CFrameWndEx::OnContextHelp](../Topic/CFrameWndEx::OnContextHelp.md)|Aufgerufen vom Framework dem Anzeigekontext verknüpfte Hilfe.|  
|[CFrameWndEx::OnCreate](../Topic/CFrameWndEx::OnCreate.md)|Aufgerufen durch das Framework nach dem Frame wird erstellt.|  
|[CFrameWndEx::OnDestroy](../Topic/CFrameWndEx::OnDestroy.md)|Aufgerufen vom Framework, wenn der Frame zerstört werden.|  
|[CFrameWndEx::OnDrawMenuImage](../Topic/CFrameWndEx::OnDrawMenuImage.md)|Aufgerufen vom Framework, wenn die Anwendung das Bild zeichnet, das einem Menüelement zugeordnet ist.|  
|[CFrameWndEx::OnDrawMenuLogo](../Topic/CFrameWndEx::OnDrawMenuLogo.md)|Aufgerufen vom Framework ausgelöst, wenn ein `CMFCPopupMenu`\-Objekt eine [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Meldung verarbeitet.|  
|[CFrameWndEx::OnDWMCompositionChanged](../Topic/CFrameWndEx::OnDWMCompositionChanged.md)|Aufgerufen vom Framework, wenn Komposition des Desktopfenster\-Managers \(DWM\) aktiviert oder deaktiviert wurde.|  
|[CFrameWndEx::OnExitSizeMove](../Topic/CFrameWndEx::OnExitSizeMove.md)|Aufgerufen vom Framework, wenn der Frame verschoben beenden oder Größe zu ändern.|  
|[CFrameWndEx::OnGetMinMaxInfo](../Topic/CFrameWndEx::OnGetMinMaxInfo.md)|Aufgerufen vom Framework, wenn der Frame angepasst werden, um Fensterdimensionsgrenzen bewerten.|  
|[CFrameWndEx::OnIdleUpdateCmdUI](../Topic/CFrameWndEx::OnIdleUpdateCmdUI.md)|Aufgerufen vom Framework, um die Frameanzeige, wenn das Befehlsverarbeiten aktualisieren im Leerlauf befindet.|  
|[CFrameWndEx::OnLButtonDown](../Topic/CFrameWndEx::OnLButtonDown.md)|Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste drückt.|  
|[CFrameWndEx::OnLButtonUp](../Topic/CFrameWndEx::OnLButtonUp.md)|Das Framework ruft diese Methode auf, wenn der Benutzer die linke Maustaste los.|  
|[CFrameWndEx::OnMenuButtonToolHitTest](../Topic/CFrameWndEx::OnMenuButtonToolHitTest.md)|Aufgerufen vom Framework ausgelöst, wenn ein `CMFCToolBarButton`\-Objekt eine `WM_NCHITTEST` Meldung verarbeitet.|  
|[CFrameWndEx::OnMenuChar](../Topic/CFrameWndEx::OnMenuChar.md)|Aufgerufen vom Framework ausgelöst, wenn ein Menü angezeigt wird und der Benutzer Drücken einer Taste, die nicht zu einem Befehl entspricht.|  
|[CFrameWndEx::OnMouseMove](../Topic/CFrameWndEx::OnMouseMove.md)|Das Framework ruft diese Methode auf, wenn der Mauszeiger bewegt.|  
|[CFrameWndEx::OnMoveMiniFrame](../Topic/CFrameWndEx::OnMoveMiniFrame.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereichsfenster bewegt.|  
|[CFrameWndEx::OnNcActivate](../Topic/CFrameWndEx::OnNcActivate.md)|Aufgerufen vom Framework, wenn der Nicht\-Clientbereich der Rahmen neu gezeichnet werden muss, um eine Änderung im aktiven Zustand anzugeben.|  
|[CFrameWndEx::OnNcCalcSize](../Topic/CFrameWndEx::OnNcCalcSize.md)|Aufgerufen vom Framework, wenn die Größe und die Position des Clientbereichs abgeleitet werden müssen.|  
|[CFrameWndEx::OnNcHitTest](../Topic/CFrameWndEx::OnNcHitTest.md)|Aufgerufen vom Framework, wenn der Mauszeiger bewegt wird, oder wenn eine Maustaste gedrückt wird oder nicht.|  
|[CFrameWndEx::OnNcMouseMove](../Topic/CFrameWndEx::OnNcMouseMove.md)|Aufgerufen vom Framework, wenn der Zeiger in einen Nicht\-Clientbereich bewegt.|  
|[CFrameWndEx::OnNcPaint](../Topic/CFrameWndEx::OnNcPaint.md)|Aufgerufen vom Framework, wenn der Nicht\-Clientbereich gezeichnet werden muss.|  
|[CFrameWndEx::OnPaneCheck](../Topic/CFrameWndEx::OnPaneCheck.md)|Aufgerufen vom Framework, um die Sichtbarkeit eines Bereichs zu steuern.|  
|[CFrameWndEx::OnPostPreviewFrame](../Topic/CFrameWndEx::OnPostPreviewFrame.md)|Aufgerufen vom Framework, wenn der Benutzer den Seitenansichtsmodus geändert hat.|  
|[CFrameWndEx::OnPowerBroadcast](../Topic/CFrameWndEx::OnPowerBroadcast.md)|Aufgerufen vom Framework ausgelöst, wenn ein Energieverwaltungsereignis auftritt.|  
|[CFrameWndEx::OnSetMenu](../Topic/CFrameWndEx::OnSetMenu.md)|Aufgerufen vom Framework, um das Rahmenfenstermenü zu ersetzen.|  
|[CFrameWndEx::OnSetPreviewMode](../Topic/CFrameWndEx::OnSetPreviewMode.md)|Aufgerufen vom Framework, um den Seitenansichtsmodus für den Frame festzulegen.|  
|[CFrameWndEx::OnSetText](../Topic/CFrameWndEx::OnSetText.md)|Aufgerufen vom Framework, um den Text eines Fensters festzulegen.|  
|[CFrameWndEx::OnShowCustomizePane](../Topic/CFrameWndEx::OnShowCustomizePane.md)|Aufgerufen vom Framework ausgelöst, wenn ein schnelles anpassen, wird Bereich aktiviert.|  
|[CFrameWndEx::OnShowPanes](../Topic/CFrameWndEx::OnShowPanes.md)|Aufgerufen durch das Framework, um Bereiche anzuzeigen oder auszublenden.|  
|[CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md)|Aufgerufen vom Framework ausgelöst, wenn ein Popupmenü aktiviert ist.|  
|[CFrameWndEx::OnSize](../Topic/CFrameWndEx::OnSize.md)|Das Framework ruft diese Methode auf, nachdem die Größe der Rahmen ändert.|  
|[CFrameWndEx::OnSizing](../Topic/CFrameWndEx::OnSizing.md)|Das Framework ruft diese Methode auf, wenn der Benutzer die Frames Größe ändert.|  
|[CFrameWndEx::OnSysColorChange](../Topic/CFrameWndEx::OnSysColorChange.md)|Aufgerufen vom Framework, wenn die Systemfarben ändern.|  
|[CFrameWndEx::OnTearOffMenu](../Topic/CFrameWndEx::OnTearOffMenu.md)|Aufgerufen vom Framework ausgelöst, wenn ein Menü, das eine Tearoffe Leiste hat, aktiviert ist.|  
|[CFrameWndEx::OnToolbarContextMenu](../Topic/CFrameWndEx::OnToolbarContextMenu.md)|Aufgerufen vom Framework, um ein Symbolleistenkontextmenü zu erstellen.|  
|[CFrameWndEx::OnToolbarCreateNew](../Topic/CFrameWndEx::OnToolbarCreateNew.md)|Das Framework ruft diese Methode auf, um eine neue Symbolleiste zu erstellen.|  
|[CFrameWndEx::OnToolbarDelete](../Topic/CFrameWndEx::OnToolbarDelete.md)|Aufgerufen vom Framework, wenn eine Symbolleiste gelöscht wird.|  
|[CFrameWndEx::OnUpdateFrameMenu](../Topic/CFrameWndEx::OnUpdateFrameMenu.md)|Aufgerufen vom Framework, um das Framemenü festzulegen.|  
|[CFrameWndEx::OnUpdateFrameTitle](../Topic/CFrameWndEx::OnUpdateFrameTitle.md)|Das Framework ruft diese Methode auf, um die Titelleiste des Rahmenfensters zu aktualisieren.|  
|[CFrameWndEx::OnUpdatePaneMenu](../Topic/CFrameWndEx::OnUpdatePaneMenu.md)|Aufgerufen vom Framework, um das Bereichsmenü zu aktualisieren.|  
|[CFrameWndEx::OnWindowPosChanged](../Topic/CFrameWndEx::OnWindowPosChanged.md)|Aufgerufen vom Framework, wenn die Framegröße, die Position oder die Z\-Reihenfolge aufgrund eines Anrufs einer Fensterverwaltungsmethode geändert hat.|  
|[CFrameWndEx::PaneFromPoint](../Topic/CFrameWndEx::PaneFromPoint.md)|Gibt den Hauptandockbereich zurück, der den angegebenen Punkt enthält.|  
|[CFrameWndEx::PreTranslateMessage](../Topic/CFrameWndEx::PreTranslateMessage.md)|Bestimmte Fenstermeldungen der Handles, bevor sie weitergeleitet werden.|  
|[CFrameWndEx::RecalcLayout](../Topic/CFrameWndEx::RecalcLayout.md)|Passt das Layout der Rahmen und der untergeordneten Fenster.|  
|[CFrameWndEx::RemovePaneFromDockManager](../Topic/CFrameWndEx::RemovePaneFromDockManager.md)|Hebt einen Bereich Registrierung auf und entfernt sie aus der internen Liste im Andocken Manager.|  
|[CFrameWndEx::SetDockState](../Topic/CFrameWndEx::SetDockState.md)|Stellt das andockbare Layout im angedockten Zustand zurück, der in der Registrierung gespeichert wird.|  
|[CFrameWndEx::SetPrintPreviewFrame](../Topic/CFrameWndEx::SetPrintPreviewFrame.md)|Legt das Seitenansichtsrahmenfenster fest.|  
|[CFrameWndEx::SetupToolbarMenu](../Topic/CFrameWndEx::SetupToolbarMenu.md)|Fügt benutzerdefinierte Befehle in ein Symbolleistenmenü ein.|  
|[CFrameWndEx::ShowFullScreen](../Topic/CFrameWndEx::ShowFullScreen.md)|Schaltet den Hauptframes zwischen dem Bildschirm und reguläre Modi um.|  
|[CFrameWndEx::ShowPane](../Topic/CFrameWndEx::ShowPane.md)|In oder aus der angegebene Bereich.|  
|[CFrameWndEx::UpdateCaption](../Topic/CFrameWndEx::UpdateCaption.md)|Aufgerufen vom Framework, um die Fensterrahmenbeschriftung zu aktualisieren.|  
|[CFrameWndEx::WinHelp](../Topic/CFrameWndEx::WinHelp.md)|Ruft entweder die `WinHelp` Anwendung oder Kontext verknüpfte Hilfe zu.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Klasse von der `CFrameWndEx`\-Klasse erbt.  Das Beispiel veranschaulicht die Methodensignaturen in der Unterklasse und wie die `OnShowPopupMenu`\-Methode überschreibt.  Dieser Codeausschnitt ist Teil [Word\-Auflagenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#3)]  
[!CODE [NVC_MFC_WordPad#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#4)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CFrameWndEx](../../mfc/reference/cframewndex-class.md)  
  
## Anforderungen  
 **Header:** afxframewndex.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)