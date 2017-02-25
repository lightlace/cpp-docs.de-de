---
title: "CDockablePaneAdapter Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockablePaneAdapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePaneAdapter class"
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDockablePaneAdapter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bietet Andockunterstützung für von `CWnd` abgeleitete Bereiche.  
  
## Syntax  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDockablePaneAdapter::GetWrappedWnd](../Topic/CDockablePaneAdapter::GetWrappedWnd.md)|Gibt das umschlossene Fenster zurück.|  
|[CDockablePaneAdapter::LoadState](../Topic/CDockablePaneAdapter::LoadState.md)|\(Überschreibt [CDockablePane::LoadState](assetId:///96110136-4f46-4764-8a76-3b4abaf77917).\)|  
|[CDockablePaneAdapter::SaveState](../Topic/CDockablePaneAdapter::SaveState.md)|\(Überschreibt [CDockablePane::SaveState](assetId:///c5c24249-8d0d-46cb-96d9-9f5c6dc191db).\)|  
|[CDockablePaneAdapter::SetWrappedWnd](../Topic/CDockablePaneAdapter::SetWrappedWnd.md)||  
  
## Hinweise  
 Das Framework instanziiert in der Regel bei Verwendung der [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md)\- oder [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md)\-Methoden Objekte dieser Klasse  
  
 Wenn Sie das `CDockablePaneAdapter`\-Verhalten anpassen möchten, können Sie einfach eine neue Klasse davon ableiten und mit [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md) die Laufzeitklasseninformationen für ein Fenster im Registerkartenformat festlegen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## Anforderungen  
 **Header:** afxDockablePaneAdapter.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)