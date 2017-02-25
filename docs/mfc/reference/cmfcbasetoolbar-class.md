---
title: "CMFCBaseToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseToolBar::CreateObject"
  - "~CMFCBaseToolBar"
  - "CMFCBaseToolBar"
  - "CMFCBaseToolBar::CMFCBaseToolBar"
  - "CMFCBaseToolBar::~CMFCBaseToolBar"
  - "CMFCBaseToolBar.~CMFCBaseToolBar"
  - "CreateObject"
  - "CMFCBaseToolBar.CMFCBaseToolBar"
  - "CMFCBaseToolBar.CreateObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseToolBar destructor"
  - "CMFCBaseToolBar class"
  - "CMFCBaseToolBar class, Konstruktor"
  - "CMFCBaseToolBar class, Destruktor"
  - "CreateObject method"
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CMFCBaseToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Basisklasse für Symbolleisten.  
  
## Syntax  
  
```  
class CMFCBaseToolBar : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCBaseToolBar::CMFCBaseToolBar`|Standardkonstruktor.|  
|`CMFCBaseToolBar::~CMFCBaseToolBar`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCBaseToolBar::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCBaseToolBar::GetDockingMode](../Topic/CMFCBaseToolBar::GetDockingMode.md)|Gibt den Andockmodus zurück.  \(Überschreibungen [CBasePane::GetDockingMode](../Topic/CBasePane::GetDockingMode.md).\)|  
|[CMFCBaseToolBar::GetMinSize](../Topic/CMFCBaseToolBar::GetMinSize.md)|Gibt die minimale Größe einer Symbolleiste zurück.  \(Überschreibungen [CPane::GetMinSize](../Topic/CPane::GetMinSize.md).\)|  
|[CMFCBaseToolBar::OnAfterChangeParent](../Topic/CMFCBaseToolBar::OnAfterChangeParent.md)|Aufgerufen durch das Framework nach dem übergeordneten Element des Bereichs ändert.  \(Überschreibungen [CBasePane::OnAfterChangeParent](../Topic/CBasePane::OnAfterChangeParent.md).\)|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
## Anforderungen  
 **Header:** afxbasetoolbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)