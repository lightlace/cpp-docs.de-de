---
title: "CTreeView Class"
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
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeView class"
  - "CTreeView class, Allgemeine Steuerelemente"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vereinfacht Verwendung der Strukturansicht und des [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), die Klasse, die Strukturansicht\-Steuerelement\-Funktionalität kapselt, mit Dokument\-\/Ansichtarchitektur MFC.  
  
## Syntax  
  
```  
class CTreeView : public CCtrlView  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CTreeView::CTreeView](../Topic/CTreeView::CTreeView.md)|Erstellt ein `CTreeView`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md)|Gibt das Struktursteuerelement zurück, das mit der Ansicht zugeordnet ist.|  
  
## Hinweise  
 Weitere Informationen über diese Architektur, finden Sie in der Übersicht für die Klasse und die [CView](../../mfc/reference/cview-class.md) Querverweise, die hier genannt werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CTreeView`  
  
## Anforderungen  
 **Header:**  afxcview.h  
  
## Siehe auch  
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)