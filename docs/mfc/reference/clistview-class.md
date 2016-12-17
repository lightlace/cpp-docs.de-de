---
title: "CListView Class"
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
  - "CListView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListView class"
  - "Ansichten, and common controls"
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CListView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vereinfacht Verwendung des Listensteuerelements und des [Verwendung](../../mfc/reference/clistctrl-class.md), die Klasse, die Listensteuerelementfunktionalität kapselt, mit Dokument\-\/Ansichtarchitektur MFC.  
  
## Syntax  
  
```  
class CListView : public CCtrlView  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CListView::CListView](../Topic/CListView::CListView.md)|Erstellt ein `CListView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CListView::GetListCtrl](../Topic/CListView::GetListCtrl.md)|Gibt das Listensteuerelement zurück, das mit der Ansicht zugeordnet ist.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CListView::RemoveImageList](../Topic/CListView::RemoveImageList.md)|Entfernt die angegebene Bildliste aus der Listenansicht.|  
  
## Hinweise  
 Weitere Informationen über diese Architektur, finden Sie in der Übersicht für die Klasse und die [CView](../../mfc/reference/cview-class.md) Querverweise, die hier genannt werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CListView`  
  
## Anforderungen  
 **Header:**  afxcview.h  
  
## Siehe auch  
 [MFC\-Beispiel ROWLIST](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)