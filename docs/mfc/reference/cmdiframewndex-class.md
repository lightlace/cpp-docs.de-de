---
title: "CMDIFrameWndEx-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIFrameWndEx.AddDockSite"
  - "CMDIFrameWndEx"
  - "CMDIFrameWndEx::AddDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIFrameWndEx-Klasse"
ms.assetid: dbcafcb3-9a7a-4f11-9dfe-ba57565c81d0
caps.latest.revision: 42
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 44
---
# CMDIFrameWndEx-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erweitert die Funktionalität von [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md), ein Rahmenfenster Windows\-MultipleDocument Interface\).  
  
## Syntax  
  
```  
class CMDIFrameWndEx : public CMDIFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMDIFrameWndEx::ActiveItemRecalcLayout](../Topic/CMDIFrameWndEx::ActiveItemRecalcLayout.md)|Berechnet das Layout des aktiven Elements neu.|  
|`CMDIFrameWndEx::AddDockSite`|Diese Methode wird nicht verwendet.|  
|[CMDIFrameWndEx::AddPane](../Topic/CMDIFrameWndEx::AddPane.md)|Registriert einen Bereich mit dem Andocken Manager.|  
|[CMDIFrameWndEx::AdjustClientArea](../Topic/CMDIFrameWndEx::AdjustClientArea.md)|Reduziert den Clientbereich, um einen Rahmen zu ermöglichen.|  
|[CMDIFrameWndEx::AdjustDockingLayout](../Topic/CMDIFrameWndEx::AdjustDockingLayout.md)|Berechnet das Layout aller angedockten Bereiche neu.|  
|[CMDIFrameWndEx::AreMDITabs](../Topic/CMDIFrameWndEx::AreMDITabs.md)|Bestimmt, ob die MDI\-Registerkarten kennzeichnen, oder die MDI mit den versehene Gruppenfunktion aktiviert ist.|  
|[CMDIFrameWndEx::CanCovertControlBarToMDIChild](../Topic/CMDIFrameWndEx::CanCovertControlBarToMDIChild.md)|Aufgerufen vom Framework, um zu bestimmen, ob das Rahmenfenster andockbare Bereiche Dokumenten konvertieren kann zu den im Registerkartenformat.|  
|[CMDIFrameWndEx::ControlBarToTabbedDocument](../Topic/CMDIFrameWndEx::ControlBarToTabbedDocument.md)|Konvertiert den angegebenen Hauptandockbereich zu einem Dokument im Registerkartenformat.|  
|[CMDIFrameWndEx::CreateDocumentWindow](../Topic/CMDIFrameWndEx::CreateDocumentWindow.md)|Stellt ein untergeordnetes Dokumentfenster erstellt.|  
|[CMDIFrameWndEx::CreateNewWindow](../Topic/CMDIFrameWndEx::CreateNewWindow.md)|Aufgerufen vom Framework, um ein neues Fenster zu erstellen.|  
|`CMDIFrameWndEx::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMDIFrameWndEx::DockPane](../Topic/CMDIFrameWndEx::DockPane.md)|Dockt den angegebenen Bereich an das Rahmenfenster an.|  
|[CMDIFrameWndEx::DockPaneLeftOf](../Topic/CMDIFrameWndEx::DockPaneLeftOf.md)|wird ein Bereich auf der linken Seite eines anderen Bereichs.|  
|[CMDIFrameWndEx::EnableAutoHidePanes](../Topic/CMDIFrameWndEx::EnableAutoHidePanes.md)|Aktiviert Modus "Automatisches Ausblenden" für Bereiche, wenn sie mit den angegebenen Seiten des Hauptrahmenfensters angedockt werden.|  
|[CMDIFrameWndEx::EnableDocking](../Topic/CMDIFrameWndEx::EnableDocking.md)|Aktiviert Andocken der Bereiche, die dem MDI\-Rahmenfenster gehören.|  
|[CMDIFrameWndEx::EnableFullScreenMainMenu](../Topic/CMDIFrameWndEx::EnableFullScreenMainMenu.md)|In oder aus dem Hauptmenü im Ganzseitenmodus.|  
|[CMDIFrameWndEx::EnableFullScreenMode](../Topic/CMDIFrameWndEx::EnableFullScreenMode.md)|Aktiviert Ganzseitenmodus für das Rahmenfenster.|  
|[CMDIFrameWndEx::EnableLoadDockState](../Topic/CMDIFrameWndEx::EnableLoadDockState.md)|Aktiviert oder deaktiviert das Laden des angedockten Zustand.|  
|[CMDIFrameWndEx::EnableMDITabbedGroups](../Topic/CMDIFrameWndEx::EnableMDITabbedGroups.md)|Aktiviert oder deaktiviert die MDI mit den versehene Gruppenfunktion.|  
|[CMDIFrameWndEx::EnableMDITabs](../Topic/CMDIFrameWndEx::EnableMDITabs.md)|Aktiviert oder deaktiviert die MDI\-Registerkartenfunktion.  Wenn die Option aktiviert ist, zeigt das Rahmenfenster eine Registerkarte für jedes untergeordnete MDI\-Fenster an.|  
|[CMDIFrameWndEx::EnableMDITabsLastActiveActivation](../Topic/CMDIFrameWndEx::EnableMDITabsLastActiveActivation.md)|Gibt an, ob die letzte aktive Registerkarte aktiviert werden soll, wenn der Benutzer die aktuelle Registerkarte enthält.|  
|[CMDIFrameWndEx::EnablePaneMenu](../Topic/CMDIFrameWndEx::EnablePaneMenu.md)|Aktiviert oder deaktiviert die automatische Erstellung und Verwaltung von Popupbereichsmenüs, das eine Liste von Anwendungsbereichen anzeigt.  .|  
|[CMDIFrameWndEx::EnableWindowsDialog](../Topic/CMDIFrameWndEx::EnableWindowsDialog.md)|Fügt ein Menüelement ein, dessen Befehls\-ID ein [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) Dialogfeld aufruft.|  
|[CMDIFrameWndEx::GetActivePopup](../Topic/CMDIFrameWndEx::GetActivePopup.md)|Gibt einen Zeiger auf aktuell angezeigten Popupmenü zurück.|  
|[CMDIFrameWndEx::GetPane](../Topic/CMDIFrameWndEx::GetPane.md)|Gibt einen Zeiger auf Bereich zurück, der die angegebene Steuerelement\-ID hat|  
|[CMDIFrameWndEx::GetDefaultResId](../Topic/CMDIFrameWndEx::GetDefaultResId.md)|Gibt die ID von freigegebene Ressourcen des MDI\-Rahmenfensters zurück.|  
|[CMDIFrameWndEx::GetMDITabGroups](../Topic/CMDIFrameWndEx::GetMDITabGroups.md)|Gibt eine Liste von MDI mit den versehenen Fenstern zurück.|  
|[CMDIFrameWndEx::GetMDITabs](../Topic/CMDIFrameWndEx::GetMDITabs.md)|Gibt einen Verweis auf den unterstrichenen Fenster im Registerkartenformat zurück.|  
|[CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems](../Topic/CMDIFrameWndEx::GetMDITabsContextMenuAllowedItems.md)|Gibt eine Kombination von Flags zurück, die bestimmt, welche Kontextmenüelemente gültig sind, wenn die MDI mit den versehene Gruppenfunktion aktiviert ist.|  
|[CMDIFrameWndEx::GetMenuBar](../Topic/CMDIFrameWndEx::GetMenuBar.md)|Gibt einen Zeiger auf einen Menüleistenobjekt zurück, das an das Rahmenfenster angefügt wird.|  
|[CMDIFrameWndEx::GetRibbonBar](../Topic/CMDIFrameWndEx::GetRibbonBar.md)|Ruft das Menübandleistesteuerelement für die Frames ab.|  
|[CMDIFrameWndEx::GetTearOffBars](../Topic/CMDIFrameWndEx::GetTearOffBars.md)|Gibt eine Liste von [CPane](../../mfc/reference/cpane-class.md) abgeleitete Objekte zurück, die in einem Tearoffen Zustand sind.|  
|`CMDIFrameWndEx::GetThisClass`|Aufgerufen vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMDIFrameWndEx::GetToolbarButtonToolTipText](../Topic/CMDIFrameWndEx::GetToolbarButtonToolTipText.md)|Aufgerufen vom Framework, wenn die Anwendung die QuickInfo für eine Symbolleisten\-Schaltfläche anzeigt.|  
|[CMDIFrameWndEx::InsertPane](../Topic/CMDIFrameWndEx::InsertPane.md)|Registriert den angegebenen Bereich mit dem Andocken Manager.|  
|[CMDIFrameWndEx::IsFullScreen](../Topic/CMDIFrameWndEx::IsFullScreen.md)|Bestimmt, ob das Rahmenfenster im Ganzseitenmodus ist.|  
|[CMDIFrameWndEx::IsMDITabbedGroup](../Topic/CMDIFrameWndEx::IsMDITabbedGroup.md)|Bestimmt, ob die MDI mit den versehene Gruppenfunktion aktiviert ist.|  
|[CMDIFrameWndEx::IsMemberOfMDITabGroup](../Topic/CMDIFrameWndEx::IsMemberOfMDITabGroup.md)|Bestimmt, ob das angegebene Fenster im Registerkartenformat in der Liste der Fenster ist, die in MDI mit den versehenen Gruppen befinden.|  
|[CMDIFrameWndEx::IsMenuBarAvailable](../Topic/CMDIFrameWndEx::IsMenuBarAvailable.md)|Bestimmt, ob das Rahmenfenster eine Menüleiste verfügt.|  
|[CMDIFrameWndEx::IsPointNearDockSite](../Topic/CMDIFrameWndEx::IsPointNearDockSite.md)|Bestimmt, ob ein bestimmter Punkt neben der Docksite ist.|  
|[CMDIFrameWndEx::IsPrintPreview](../Topic/CMDIFrameWndEx::IsPrintPreview.md)|Bestimmt, ob das Rahmenfenster in der Seitenansicht ist.|  
|[CMDIFrameWndEx::LoadFrame](../Topic/CMDIFrameWndEx::LoadFrame.md)|Stellt ein Rahmenfenster von den Ressourceninformationen erstellt.  \(Überschreibungen `CMDIFrameWnd::LoadFrame`.\)|  
|[CMDIFrameWndEx::LoadMDIState](../Topic/CMDIFrameWndEx::LoadMDIState.md)|Lädt das angegebene Layout von MDI mit den versehenen Gruppen und eine Liste der zuvor geöffneten Dokumenten.|  
|[CMDIFrameWndEx::MDITabMoveToNextGroup](../Topic/CMDIFrameWndEx::MDITabMoveToNextGroup.md)|Verschiebt die aktive Registerkarte vom aktuell aktiven Fenster im Registerkartenformat zur nächsten oder vorherigen Gruppe im Registerkartenformat.|  
|[CMDIFrameWndEx::MDITabNewGroup](../Topic/CMDIFrameWndEx::MDITabNewGroup.md)|Erstellt eine neue Gruppe im Registerkartenformat, die ein einzelnes Fenster verfügt.|  
|[CMDIFrameWndEx::NegotiateBorderSpace](../Topic/CMDIFrameWndEx::NegotiateBorderSpace.md)|Verhandelt über Rahmenleerzeichen in einem Rahmenfenster während OLE\-direkter Aktivierung.|  
|[CMDIFrameWndEx::OnCloseDockingPane](../Topic/CMDIFrameWndEx::OnCloseDockingPane.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Schließen** auf einem andockbare Fenster klicken.|  
|[CMDIFrameWndEx::OnCloseMiniFrame](../Topic/CMDIFrameWndEx::OnCloseMiniFrame.md)|Aufgerufen vom Framework, wenn der Benutzer auf die Schaltfläche **Schließen** auf einem beweglichen Minirahmenfenster klickt.|  
|[CMDIFrameWndEx::OnClosePopupMenu](../Topic/CMDIFrameWndEx::OnClosePopupMenu.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein aktives Popupmenü eine `WM_DESTROY` Meldung verarbeitet.|  
|[CMDIFrameWndEx::OnCmdMsg](../Topic/CMDIFrameWndEx::OnCmdMsg.md)|Aufgerufen durch das Framework, um Befehlsmeldungen weiterzuleiten und Weiterleiten und zu aktualisieren Befehlsbenutzeroberfläche Objekte ein.|  
|[CMDIFrameWndEx::OnDrawMenuImage](../Topic/CMDIFrameWndEx::OnDrawMenuImage.md)|Aufgerufen vom Framework, wenn das Bild, das einem Menüelement zugeordnet ist, gezeichnet wird.|  
|[CMDIFrameWndEx::OnDrawMenuLogo](../Topic/CMDIFrameWndEx::OnDrawMenuLogo.md)|Aufgerufen vom Framework, wenn [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) eine `WM_PAINT` Meldung verarbeitet.|  
|[CMDIFrameWndEx::OnEraseMDIClientBackground](../Topic/CMDIFrameWndEx::OnEraseMDIClientBackground.md)|Aufgerufen vom Framework, wenn das MDI\-Rahmenfenster eine `WM_ERASEBKGND` Meldung verarbeitet.|  
|[CMDIFrameWndEx::OnMenuButtonToolHitTest](../Topic/CMDIFrameWndEx::OnMenuButtonToolHitTest.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)\-Objekt eine `WM_NCHITTEST` Meldung verarbeitet.|  
|[CMDIFrameWndEx::OnMoveMiniFrame](../Topic/CMDIFrameWndEx::OnMoveMiniFrame.md)|Aufgerufen vom Framework, um ein Minirahmenfenster zu verschieben.|  
|[CMDIFrameWndEx::OnSetPreviewMode](../Topic/CMDIFrameWndEx::OnSetPreviewMode.md)|Legt den Hauptrahmenfenster\-Seitenansichtsmodus der Anwendung fest.  \(Überschreibungen [CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md).\)|  
|[CMDIFrameWndEx::OnShowCustomizePane](../Topic/CMDIFrameWndEx::OnShowCustomizePane.md)|Aufgerufen vom Framework, wenn Quick anpassen, Bereich aktiviert ist.|  
|[CMDIFrameWndEx::OnShowMDITabContextMenu](../Topic/CMDIFrameWndEx::OnShowMDITabContextMenu.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein Kontextmenü auf einer der Registerkarten angezeigt werden soll.  \(Gültig für MDI mit den versehene nur Gruppen.\)|  
|[CMDIFrameWndEx::OnShowPanes](../Topic/CMDIFrameWndEx::OnShowPanes.md)|Aufgerufen durch das Framework, um Bereiche anzuzeigen oder auszublenden.|  
|[CMDIFrameWndEx::OnShowPopupMenu](../Topic/CMDIFrameWndEx::OnShowPopupMenu.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein Popupmenü aktiviert ist.|  
|[CMDIFrameWndEx::OnSizeMDIClient](../Topic/CMDIFrameWndEx::OnSizeMDIClient.md)|Aufgerufen vom Framework, wenn die Größe des Fensters des Client MDI ändert.|  
|[CMDIFrameWndEx::OnTearOffMenu](../Topic/CMDIFrameWndEx::OnTearOffMenu.md)|Aufgerufen vom \- Framework ausgelöst, wenn ein Menü, das eine Tearoffe Leiste hat, aktiviert ist.|  
|[CMDIFrameWndEx::OnUpdateFrameMenu](../Topic/CMDIFrameWndEx::OnUpdateFrameMenu.md)|Aufgerufen vom Framework, um das Framemenü zu aktualisieren.  \(Überschreibungen `CMDIFrameWnd::OnUpdateFrameMenu`.\)|  
|[CMDIFrameWndEx::PaneFromPoint](../Topic/CMDIFrameWndEx::PaneFromPoint.md)|Gibt den Hauptandockbereich zurück, der den angegebenen Punkt enthält.|  
|`CMDIFrameWndEx::PreTranslateMessage`|Wird von Klasse [CWinApp](../../mfc/reference/cwinapp-class.md), um Fenstermeldungen zu übersetzen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  \(Überschreibungen `CMDIFrameWnd::PreTranslateMessage`.\)|  
|[CMDIFrameWndEx::RecalcLayout](../Topic/CMDIFrameWndEx::RecalcLayout.md)|Aufgerufen vom Framework, um das Layout des Rahmenfensters neu zu berechnen.  \(Überschreibungen [CFrameWnd::RecalcLayout](../Topic/CFrameWnd::RecalcLayout.md).\)|  
|[CMDIFrameWndEx::RemovePaneFromDockManager](../Topic/CMDIFrameWndEx::RemovePaneFromDockManager.md)|Hebt einen Bereich Registrierung auf und entfernt sie aus dem Andocken Manager.|  
|[CMDIFrameWndEx::SaveMDIState](../Topic/CMDIFrameWndEx::SaveMDIState.md)|Speichert das aktuelle Layout von MDI mit den versehenen Gruppen und eine Liste der zuvor geöffneten Dokumenten.|  
|[CMDIFrameWndEx::SetPrintPreviewFrame](../Topic/CMDIFrameWndEx::SetPrintPreviewFrame.md)|Legt das Seitenansichtsrahmenfenster fest.|  
|[CMDIFrameWndEx::SetupToolbarMenu](../Topic/CMDIFrameWndEx::SetupToolbarMenu.md)|Ändert ein Symbolleistenobjekt durch Suchen für blinde Elemente und Ersetzen sie mit den angegebenen benutzerdefinierten Elementen.|  
|[CMDIFrameWndEx::ShowFullScreen](../Topic/CMDIFrameWndEx::ShowFullScreen.md)|Schaltet den Hauptframes des regulären Modus zum Ganzseitenmodus um.|  
|[CMDIFrameWndEx::ShowPane](../Topic/CMDIFrameWndEx::ShowPane.md)|In oder aus der angegebene Bereich.|  
|[CMDIFrameWndEx::ShowWindowsDialog](../Topic/CMDIFrameWndEx::ShowWindowsDialog.md)|Stellt ein Feld [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) erstellt und öffnet es.|  
|[CMDIFrameWndEx::TabbedDocumentToControlBar](../Topic/CMDIFrameWndEx::TabbedDocumentToControlBar.md)|Konvertiert das angegebene Dokument im Registerkartenformat zu einem Hauptandockbereich.|  
|[CMDIFrameWndEx::UpdateCaption](../Topic/CMDIFrameWndEx::UpdateCaption.md)|Aufgerufen vom Framework, um die Fensterrahmenbeschriftung zu aktualisieren.|  
|[CMDIFrameWndEx::UpdateMDITabbedBarsIcons](../Topic/CMDIFrameWndEx::UpdateMDITabbedBarsIcons.md)|Legt das Symbol für jede MDI\-Seite im Registerformat fest.|  
|[CMDIFrameWndEx::WinHelp](../Topic/CMDIFrameWndEx::WinHelp.md)|Aufgerufen vom Framework, um die WinHelp\-Anwendungs\- oder \-Kontexthilfe zu initiieren.  \(Überschreibungen [CWnd::WinHelp](../Topic/CWnd::WinHelp.md).\)|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMDIFrameWndEx::m\_bCanCovertControlBarToMDIChild](../Topic/CMDIFrameWndEx::m_bCanCovertControlBarToMDIChild.md)|Bestimmt, ob Andockbereiche den untergeordneten MDI\-Fenstern konvertiert werden können.|  
|[CMDIFrameWndEx::m\_bDisableSetRedraw](../Topic/CMDIFrameWndEx::m_bDisableSetRedraw.md)|Aktiviert oder deaktiviert die entwerfen, Optimierung für untergeordnete MDI\-Fenster neu.|  
  
## Hinweise  
 Um erweiterte Verwendung in der MDI\-Anwendung zu nutzen, berechnen Sie die MDI\-Rahmenfensterklasse der Anwendung von `CMDIFrameWndEx` anstelle `CMDIFrameWnd`.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Klasse von `CMDIFrameWndEx`.  Dieser Codeausschnitt stammt [DrawClient\-Beispiel: Menübandbasierte MFC\-Anwendung zum Zeichnen von](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_DrawClient#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_DrawClient#1)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)  
  
 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)  
  
## Anforderungen  
 **Header:** afxMDIFrameWndEx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWnd](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWndEx\-Klasse](../../mfc/reference/cmdichildwndex-class.md)