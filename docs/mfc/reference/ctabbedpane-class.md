---
title: "CTabbedPane Class"
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
  - "CTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabbedPane class"
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: 27
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CTabbedPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktionalität eines Bereichs mit abtrennbaren Registerkarten.  
  
## Syntax  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CTabbedPane::CTabbedPane`|Standardkonstruktor|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CTabbedPane::DetachPane](../Topic/CTabbedPane::DetachPane.md)|\(Überschreibt [CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md).\)|  
|[CTabbedPane::EnableTabAutoColor](../Topic/CTabbedPane::EnableTabAutoColor.md)|Aktiviert oder deaktiviert die automatische Registerkartenfärbung.|  
|[CTabbedPane::FloatTab](../Topic/CTabbedPane::FloatTab.md)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet.  \(Überschreibt [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md).\)|  
|[CTabbedPane::GetTabArea](../Topic/CTabbedPane::GetTabArea.md)|Gibt die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zurück.|  
|[CTabbedPane::GetTabWnd](../Topic/CTabbedPane::GetTabWnd.md)||  
|[CTabbedPane::HasAutoHideMode](../Topic/CTabbedPane::HasAutoHideMode.md)|Bestimmt, ob der Bereich im Registerkartenformat automatisch in den Hintergrundmodus gewechselt werden kann.  \(Überschreibt [CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md).\)|  
|[CTabbedPane::IsTabLocationBottom](../Topic/CTabbedPane::IsTabLocationBottom.md)|Bestimmt, ob sich die Registerkarten am unteren Rand des Fensters befinden.|  
|[CTabbedPane::ResetTabs](../Topic/CTabbedPane::ResetTabs.md)|Setzt alle Bereiche im Registerkartenformat auf den Standardstatus zurück.|  
|[CTabbedPane::SetTabAutoColors](../Topic/CTabbedPane::SetTabAutoColors.md)|Legt eine Liste benutzerdefinierter Farben fest, die verwendet werden kann, wenn die Funktion für automatische Farben aktiviert ist.|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CTabbedPane::m\_bTabsAlwaysTop](../Topic/CTabbedPane::m_bTabsAlwaysTop.md)|Die Standardposition für Registerkarten in der Anwendung.|  
|[CTabbedPane::m\_pTabWndRTC](../Topic/CTabbedPane::m_pTabWndRTC.md)|Laufzeitklasseninformationen für ein benutzerdefiniertes `CMFCTabCtrl`\-abgeleitetes Objekt.|  
  
## Hinweise  
 Das Framework erstellt automatisch eine Instanz dieser Klasse, wenn ein Benutzer einen Bereich an einen anderen anfügt, indem es auf die Beschriftung des zweiten Bereichs verweist.  Alle der vom Framework erstellten Bereiche im Registerkartenformat besitzen eine ID von "\-1".  
  
 Um normale Registerkarten anstatt von Registerkarten im Outlook\-Stil anzugeben, übergeben Sie den `AFX_CBRS_REGULAR_TABS`\-Stil an die [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md)\-Methode.  
  
 Wenn Sie einen Bereich im Registerkartenformat mit abtrennbaren Registerkarten erstellen, kann der Bereich automatisch durch das Framework zerstört werden. Speichern Sie daher nicht den Zeiger.  Um einen Zeiger zum Bereich im Registerkartenformat zu erhalten, rufen Sie die `CBasePane::GetParentTabbedPane`\-Methode auf.  
  
## Beispiel  
 In diesem Beispiel erstellen wir ein `CTabbedPane`\-Objekt.  Als Nächstes verwenden wir [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md), um  zusätzliche Registerkarten anzufügen.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);  
if (!pTabbededBar->Create (_T(""), this, CRect (0, 0, 200, 200),  
                           TRUE,   
                           (UINT) -1,  
                           WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
                           WS_CLIPCHILDREN | CBRS_LEFT |    
                           CBRS_FLOAT_MULTI))  
{  
    TRACE0("Failed to create Solution Explorer bar\n");  
    return FALSE;      // fail to create  
}  
  
pTabbededBar->AddTab (&m_wndClassView);  
pTabbededBar->AddTab (&m_wndResourceView);  
pTabbededBar->AddTab (&m_wndFileView);  
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);  
DockPane(pTabbededBar);  
```  
  
## Beispiel  
 Alternativ können Sie ein Steuerleistenobjekt im Registerkartenformat mit [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) erstellen.  Die `AttachToTabWnd`\-Methode erstellt dynamisch ein Bereichsobjekt im Registerformat mithilfe der durch [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md) festgelegten Laufzeitklasseninformationen.  
  
 In diesem Beispiel erstellen wir einen dynamischen Bereich im Registerkartenformat, fügen zwei Registerkarten an und legen die zweite Registerkarte als nicht entfernbar fest.  
  
```  
DockPane(&m_wndClassView);  
CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView, DM_SHOW, TRUE,  
                                  (CDockablePane**) &pTabbedBar);  
m_wndFileView.AttachToTabWnd (pTabbedBar, DM_SHOW, TRUE,  
                              (CDockablePane**) &pTabbedBar);  
pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1, FALSE);  
```  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## Anforderungen  
 **Header:** afxTabbedPane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CBaseTabbedPane\-Klasse](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)