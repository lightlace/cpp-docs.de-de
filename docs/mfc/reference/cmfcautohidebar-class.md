---
title: "CMFCAutoHideBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCAutoHideBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideToolBar class"
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCAutoHideBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCAutoHideBar`\-Klasse ist eine besondere Symbolleistenklasse, die die Funktion „Automatisch im Hintergrund“ implementiert.  
  
## Syntax  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](../Topic/CMFCAutoHideBar::CMFCAutoHideBar.md)||  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](../Topic/CMFCAutoHideBar::AddAutoHideWindow.md)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](../Topic/CMFCAutoHideBar::AllowShowOnPaneMenu.md)|\(Überschreibt `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCAutoHideBar::CalcFixedLayout](../Topic/CMFCAutoHideBar::CalcFixedLayout.md)|\(Überschreibt [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCAutoHideBar::Create](../Topic/CMFCAutoHideBar::Create.md)|Erstellt eine Steuerleiste und fügt sie an das [CPane](../../mfc/reference/cpane-class.md)\-Objekt an.  \(Überschreibt [CPane::Create](../Topic/CPane::Create.md).\)|  
|[CMFCAutoHideBar::GetFirstAHWindow](../Topic/CMFCAutoHideBar::GetFirstAHWindow.md)||  
|[CMFCAutoHideBar::GetVisibleCount](../Topic/CMFCAutoHideBar::GetVisibleCount.md)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](../Topic/CMFCAutoHideBar::OnShowControlBarMenu.md)|Wird von Framework aufgerufen, kurz bevor ein spezielles Bereichsmenü angezeigt wird.  \(Überschreibt [CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md).\)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](../Topic/CMFCAutoHideBar::RemoveAutoHideWindow.md)||  
|[CMFCAutoHideBar::SetActiveInGroup](../Topic/CMFCAutoHideBar::SetActiveInGroup.md)|\(Überschreibt [CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md).\)|  
|[CMFCAutoHideBar::SetRecentVisibleState](../Topic/CMFCAutoHideBar::SetRecentVisibleState.md)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](../Topic/CMFCAutoHideBar::ShowAutoHideWindow.md)||  
|[CMFCAutoHideBar::StretchPane](../Topic/CMFCAutoHideBar::StretchPane.md)|Streckt einen Bereich vertikal oder horizontal.  \(Überschreibt [CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md).\)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md)||  
|[CMFCAutoHideBar::UpdateVisibleState](../Topic/CMFCAutoHideBar::UpdateVisibleState.md)||  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCAutoHideBar::m\_nShowAHWndDelay](../Topic/CMFCAutoHideBar::m_nShowAHWndDelay.md)|Die zeitliche Verzögerung zwischen dem Zeitpunkt, wenn der Benutzer den Mauszeiger über eine [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md) platziert und dem Zeitpunkt, wenn das Framework das zugeordnete Fenster anzeigt.|  
  
## Hinweise  
 Wenn der Benutzer für einen Dockbereich den Modus „Automatisches Ausblenden“ auswählt, erstellt das Framework automatisch ein `CMFCAutoHideBar`\-Objekt.  Es erstellt außerdem die erforderlichen [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)\- und [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)\-Objekte.  Jedes `CAutoHideDockSite`\-Objekt bezieht sich auf ein einzelne `CMFCAutoHideButton`.  
  
 Die `CMFCAutoHideBar`\-Klasse implementiert die Anzeige einer `CAutoHideDockSite`, wenn ein Benutzer die Maus über eine `CMFCAutoHideButton` bewegt.  Wenn die Symbolleiste eine WM\_MOUSEMOVE\-Meldung empfängt, startet `CMFCAutoHideBar` einen Zeitgeber.  Wenn der Zeitgeber fertig ist, sendet er eine WM\_TIMER\-Ereignisbenachrichtigung an die Symbolleiste.  Die Symbolleiste verarbeitet dieses Ereignis, indem geprüft wird, ob sich der Mauszeiger über der gleichen automatisch ausblendbaren Schaltfläche befindet, über der er sich befand, als der Zeitgeber gestartet wurde.  Wenn dies der Fall ist, wird die angehängte `CAutoHideDockSite` angezeigt.  
  
 Sie können die Länge der Verzögerung für den Zeitgeber durch Festlegen von `m_nShowAHWndDelay` steuern.  Der Standardwert ist 400 ms.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAutoHideBar`\-Objekts und die Verwendung der `GetDockSiteRow`\-Methode.  
  
 [!CODE [NVC_MFC_RibbonApp#26](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#26)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## Anforderungen  
 **Header:** afxautohidebar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md)