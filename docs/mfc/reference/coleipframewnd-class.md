---
title: "COleIPFrameWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleIPFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWnd class"
  - "in-place editing"
  - "OLE, Bearbeiten"
  - "OLE, in-place activation"
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleIPFrameWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basis für Fenster der direkten Bearbeitung der Anwendung.  
  
## Syntax  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](../Topic/COleIPFrameWnd::COleIPFrameWnd.md)|Erstellt ein `COleIPFrameWnd`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](../Topic/COleIPFrameWnd::OnCreateControlBars.md)|Aufgerufen vom Framework, wenn ein Element für die direkte Bearbeitung aktiviert ist.|  
|[COleIPFrameWnd::RepositionFrame](../Topic/COleIPFrameWnd::RepositionFrame.md)|Aufgerufen vom Framework, um das Fenster der direkten Bearbeitung neu anzuordnen.|  
  
## Hinweise  
 Diese Klasse erstellt und positioniert Steuerleisten innerhalb des Dokumentfensters mithilfe der Containeranwendung.  Es behandelt auch die Benachrichtigungen, die durch ein eingebettetes [COleResizeBar](../../mfc/reference/coleresizebar-class.md)\-Objekt generiert werden, wenn der Benutzer das Fenster der direkten Bearbeitung Größe ändert.  
  
 Weitere Informationen zur Verwendung von `COleIPFrameWnd`, finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC Sampling HIERSVR](../../top/visual-cpp-samples.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)