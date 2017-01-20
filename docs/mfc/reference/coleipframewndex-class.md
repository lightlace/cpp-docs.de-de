---
title: "COleIPFrameWndEx Class"
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
  - "COleIPFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWndEx class"
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# COleIPFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse `COleIPFrameWndEx` implementiert einen OLE\-Container, der MFC unterstützt. Sie müssen die Klasse für das direkte Rahmenfenster der Anwendung von der `COleIPFrameWndEx`\-Klasse ableiten und nicht von der [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)\-Klasse.  
  
## Syntax  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[COleIPFrameWndEx::AddDockSite](../Topic/COleIPFrameWndEx::AddDockSite.md)||  
|[COleIPFrameWndEx::AddPane](../Topic/COleIPFrameWndEx::AddPane.md)||  
|[COleIPFrameWndEx::AdjustDockingLayout](../Topic/COleIPFrameWndEx::AdjustDockingLayout.md)||  
|[COleIPFrameWndEx::DockPane](../Topic/COleIPFrameWndEx::DockPane.md)||  
|[COleIPFrameWndEx::DockPaneLeftOf](../Topic/COleIPFrameWndEx::DockPaneLeftOf.md)|Dockt einen Bereich auf der linken Seite eines anderen Bereichs an.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](../Topic/COleIPFrameWndEx::EnableAutoHidePanes.md)||  
|[COleIPFrameWndEx::EnableDocking](../Topic/COleIPFrameWndEx::EnableDocking.md)||  
|[COleIPFrameWndEx::EnablePaneMenu](../Topic/COleIPFrameWndEx::EnablePaneMenu.md)||  
|[COleIPFrameWndEx::GetActivePopup](../Topic/COleIPFrameWndEx::GetActivePopup.md)|Gibt einen Zeiger auf das aktuell angezeigte Popupmenü zurück.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](../Topic/COleIPFrameWndEx::GetContainerFrameWindow.md)||  
|[COleIPFrameWndEx::GetDefaultResId](../Topic/COleIPFrameWndEx::GetDefaultResId.md)|Gibt die Ressourcen\-ID des Rahmenfensters zurück, die Sie beim Laden des Fensters angegeben haben.|  
|[COleIPFrameWndEx::GetDockFrame](../Topic/COleIPFrameWndEx::GetDockFrame.md)||  
|[COleIPFrameWndEx::GetDockingManager](../Topic/COleIPFrameWndEx::GetDockingManager.md)||  
|[COleIPFrameWndEx::GetMainFrame](../Topic/COleIPFrameWndEx::GetMainFrame.md)||  
|[COleIPFrameWndEx::GetMenuBar](../Topic/COleIPFrameWndEx::GetMenuBar.md)|Gibt einen Zeiger auf das Menüleistenobjekt zurück, das an das Rahmenfenster angefügt ist.|  
|[COleIPFrameWndEx::GetPane](../Topic/COleIPFrameWndEx::GetPane.md)||  
|[COleIPFrameWndEx::GetTearOffBars](../Topic/COleIPFrameWndEx::GetTearOffBars.md)|Gibt eine Liste von Bereichsobjekten zurück, die sich in einem abtrennbaren Zustand befinden.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](../Topic/COleIPFrameWndEx::GetToolbarButtonToolTipText.md)|Wird vom Framework aufgerufen, bevor die QuickInfo für die Schaltfläche angezeigt wird.|  
|[COleIPFrameWndEx::InsertPane](../Topic/COleIPFrameWndEx::InsertPane.md)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](../Topic/COleIPFrameWndEx::IsMenuBarAvailable.md)|Ermittelt, ob der Zeiger auf das Menüleistenobjekt nicht `NULL` ist.|  
|[COleIPFrameWndEx::IsPointNearDockSite](../Topic/COleIPFrameWndEx::IsPointNearDockSite.md)||  
|[COleIPFrameWndEx::LoadFrame](../Topic/COleIPFrameWndEx::LoadFrame.md)|\(Überschreibt `COleIPFrameWnd::LoadFrame`.\)|  
|[COleIPFrameWndEx::OnCloseDockingPane](../Topic/COleIPFrameWndEx::OnCloseDockingPane.md)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](../Topic/COleIPFrameWndEx::OnCloseMiniFrame.md)||  
|[COleIPFrameWndEx::OnClosePopupMenu](../Topic/COleIPFrameWndEx::OnClosePopupMenu.md)|Wird vom Framework aufgerufen, wenn ein aktives Popupmenü eine WM\_DESTROY\-Meldung verarbeitet.|  
|[COleIPFrameWndEx::OnCmdMsg](../Topic/COleIPFrameWndEx::OnCmdMsg.md)|\(Überschreibt `CFrameWnd::OnCmdMsg`.\)|  
|[COleIPFrameWndEx::OnDrawMenuImage](../Topic/COleIPFrameWndEx::OnDrawMenuImage.md)|Wird vom Framework aufgerufen, wenn das einem Menüelement zugeordnete Bild gezeichnet wird.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](../Topic/COleIPFrameWndEx::OnDrawMenuLogo.md)|Wird von Framework aufgerufen, wenn ein [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)\-Objekt eine WM\_PAINT\-Meldung verarbeitet.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](../Topic/COleIPFrameWndEx::OnMenuButtonToolHitTest.md)|Wird von Framework aufgerufen, wenn ein [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)\-Objekt eine WM\_NCHITTEST\-Meldung verarbeitet.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](../Topic/COleIPFrameWndEx::OnMoveMiniFrame.md)||  
|[COleIPFrameWndEx::OnSetPreviewMode](../Topic/COleIPFrameWndEx::OnSetPreviewMode.md)|Rufen Sie diese Memberfunktion auf, um für das Hauptrahmenfenster den Seitenansichtmodus zu aktivieren oder zu deaktivieren. \(Überschreibt [CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md).\)|  
|[COleIPFrameWndEx::OnShowCustomizePane](../Topic/COleIPFrameWndEx::OnShowCustomizePane.md)||  
|[COleIPFrameWndEx::OnShowPanes](../Topic/COleIPFrameWndEx::OnShowPanes.md)||  
|[COleIPFrameWndEx::OnShowPopupMenu](../Topic/COleIPFrameWndEx::OnShowPopupMenu.md)|Wird vom Framework aufgerufen, wenn ein Popupmenü aktiviert wird.|  
|[COleIPFrameWndEx::OnTearOffMenu](../Topic/COleIPFrameWndEx::OnTearOffMenu.md)|Wird vom Framework aufgerufen, wenn ein Menü mit abtrennbarer Leiste aktiviert wird.|  
|[COleIPFrameWndEx::PaneFromPoint](../Topic/COleIPFrameWndEx::PaneFromPoint.md)||  
|[COleIPFrameWndEx::PreTranslateMessage](../Topic/COleIPFrameWndEx::PreTranslateMessage.md)|\(Überschreibt `COleIPFrameWnd::PreTranslateMessage`.\)|  
|[COleIPFrameWndEx::RecalcLayout](../Topic/COleIPFrameWndEx::RecalcLayout.md)|\(Überschreibt `COleIPFrameWnd::RecalcLayout`.\)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](../Topic/COleIPFrameWndEx::RemovePaneFromDockManager.md)||  
|[COleIPFrameWndEx::SetDockState](../Topic/COleIPFrameWndEx::SetDockState.md)|Wendet den angegebenen Andockstatus auf Bereiche an, die zum Rahmenfenster gehören.|  
|[COleIPFrameWndEx::SetupToolbarMenu](../Topic/COleIPFrameWndEx::SetupToolbarMenu.md)|Ändert ein Symbolleistenobjekt durch die Suche nach Dummy\-Elementen und durch das anschließende Ersetzen dieser Dummy\-Elemente durch die angegebenen benutzerdefinierten Elemente.|  
|[COleIPFrameWndEx::ShowPane](../Topic/COleIPFrameWndEx::ShowPane.md)||  
|[COleIPFrameWndEx::WinHelp](../Topic/COleIPFrameWndEx::WinHelp.md)|Wird vom Framework aufgerufen, um die WinHelp\-Anwendung oder die Kontexthilfe zu initiieren.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[COleIPFrameWndEx::InitUserToobars](../Topic/COleIPFrameWndEx::InitUserToobars.md)|Weist das Framework an, einen Bereich von Steuerelement\-IDs zu initialisieren, die benutzerdefinierten Symbolleisten zugeordnet sind.|  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie für eine Instanz der `COleIPFrameWndEx`\-Klasse eine Unterklasse erstellen und deren Methoden außer Kraft setzen. Das Beispiel veranschaulicht, wie die Methoden `OnDestory`, `RepositionFrame`, `RecalcLayout` und `CalcWindowRect` außer Kraft gesetzt werden. Dieser Codeausschnitt ist Teil des [WordPad\-Beispiels](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#1)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## Anforderungen  
 **Header:** afxoleipframewndex.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx\-Klasse](../../mfc/reference/cmdiframewndex-class.md)