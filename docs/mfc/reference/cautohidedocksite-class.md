---
title: "CAutoHideDockSite Class"
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
  - "CAutoHideDockSite"
  - "AllowShowOnPaneMenu"
  - "CAutoHideDockSite::AllowShowOnPaneMenu"
  - "CAutoHideDockSite.AllowShowOnPaneMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AllowShowOnPaneMenu method"
  - "CAutoHideDockSite class"
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoHideDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CAutoHideDockSite` erweitert [CDockSite Class](../../mfc/reference/cdocksite-class.md), um Dockbereiche der automatische Ausblendenen automatische Ausblenden zu implementieren.  
  
## Syntax  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CAutoHideDockSite::CAutoHideDockSite`|Erstellt ein `CAutoHideDockSite`\-Objekt.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|Destruktor.|  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|Gibt an, ob `CAutoHideDockSite` auf dem Bereichsmenü angezeigt wird.|  
|[CAutoHideDockSite::CanAcceptPane](../Topic/CAutoHideDockSite::CanAcceptPane.md)|Bestimmt, ob ein niedriges Bereichsobjekt von [CMFCAutoHideBar Class](../../mfc/reference/cmfcautohidebar-class.md) abgeleitet wird.|  
|[CAutoHideDockSite::DockPane](../Topic/CAutoHideDockSite::DockPane.md)|Dockt einen Bereich zu diesem `CAuotHideDockSite`\-Objekt.|  
|[CAutoHideDockSite::GetAlignRect](../Topic/CAutoHideDockSite::GetAlignRect.md)|Ruft die Größe der Docksite in Bildschirmkoordinaten ab.|  
|[CAutoHideDockSite::RepositionPanes](../Topic/CAutoHideDockSite::RepositionPanes.md)|Aktualisiert den Bereich auf `CAutoHideDockSite` mit den globalen Rändern und dem Schaltflächenabstand neu.|  
|[CAutoHideDockSite::SetOffsetLeft](../Topic/CAutoHideDockSite::SetOffsetLeft.md)|Legt den Rand auf der linken Seite der Andocken Leiste fest.|  
|[CAutoHideDockSite::SetOffsetRight](../Topic/CAutoHideDockSite::SetOffsetRight.md)|Legt den Rand auf der rechten Seite der Andocken Leiste fest.|  
|[CAutoHideDockSite::UnSetAutoHideMode](../Topic/CAutoHideDockSite::UnSetAutoHideMode.md)|Aufrufe [CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md) für Objekte auf `CAutoHideDockSite`.|  
  
### Datenmember  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CAutoHideDockSite::m\_nExtraSpace](../Topic/CAutoHideDockSite::m_nExtraSpace.md)|Definiert die Größe des Abstands zwischen den Symbolleisten und dem Rand der Andocken Leiste.  Dadurch wird Speicherplatz entweder vom linken Rand oder vom oberen Rand, abhängig von der Ausrichtung für das Dockleerzeichen gemessen.|  
  
## Hinweise  
 Wenn Sie [CFrameWndEx::EnableAutoHidePanes](../Topic/CFrameWndEx::EnableAutoHidePanes.md) aufrufen, erstellt das Framework automatisch ein `CAutoHideDockSite`\-Objekt.  In den meisten Fällen sollten Sie diese Klasse direkt instanziieren oder verwenden müssen.  
  
 Die andockbare Leiste ist die Lücke zwischen der linken Seite des Dockbereichs und der linken Seite [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein `CAutoHideDockSite`\-Objekt von einem `CMFCAutoHideBar`\-Objekt abgerufen wird und wie die linken und rechten Randes der Andocken Leiste festgelegt wird.  
  
 [!CODE [NVC_MFC_RibbonApp#29](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#29)]  
  
## Anforderungen  
 **Header:** afxautohidedocksite.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockSite Class](../../mfc/reference/cdocksite-class.md)