---
title: "COleResizeBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleResizeBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleResizeBar class"
  - "control bars, Größenänderung"
  - "in-place items"
  - "in-place items, Größenänderung"
  - "OLE items, Größenänderung"
  - "resizing in-place OLE items"
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleResizeBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Typ Steuerleiste, die Größenanpassung von direkten OLE\-Elementen unterstützt.  
  
## Syntax  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](../Topic/COleResizeBar::COleResizeBar.md)|Erstellt ein `COleResizeBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleResizeBar::Create](../Topic/COleResizeBar::Create.md)|Erstellt und initialisiert ein Windows\-untergeordnetesFenster und weist dieses dem `COleResizeBar`\-Objekt zu.|  
  
## Hinweise  
 `COleResizeBar`\-Objekte werden als [CRectTracker](../../mfc/reference/crecttracker-class.md) ein schraffierter Rahmen und äußeren Ziehpunkten.  
  
 `COleResizeBar`\-Objekte sind normalerweise eingebettete Member von den Rahmenfensterobjekten, die von der [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)\-Klasse abgeleitet werden.  
  
 Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC Sampling SUPERPAD](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)