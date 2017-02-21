---
title: "CCtrlView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCtrlView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCtrlView class"
  - "Steuerelemente [MFC], common"
  - "Ansichten, and common controls"
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CCtrlView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Passt die Dokument\-\/Ansichtarchitektur den allgemeinen Steuerelemente an, die von Windows 98 und Windows NT\-Versionen 3,51 und höher unterstützt werden.  
  
## Syntax  
  
```  
class CCtrlView : public CView  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](../Topic/CCtrlView::CCtrlView.md)|Erstellt ein `CCtrlView`\-Objekt.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCtrlView::OnDraw](../Topic/CCtrlView::OnDraw.md)|Aufgerufen durch das Framework, um mithilfe des angegebenen Gerätekontexts zu zeichnen.|  
|[CCtrlView::PreCreateWindow](../Topic/CCtrlView::PreCreateWindow.md)|Aufgerufen vor der Erstellung des Windows\-Fensters angefügt `CCtrlView` zu diesem Objekt.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CCtrlView::m\_dwDefaultStyle](../Topic/CCtrlView::m_dwDefaultStyle.md)|Enthält den Standardstil für die Ansichtsklasse.|  
|[CCtrlView::m\_strClass](../Topic/CCtrlView::m_strClass.md)|Enthält den Windows\-Klassennamen für die Ansichtsklasse.|  
  
## Hinweise  
 Die Klasse `CCtrlView` und ihre Ableitungen, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md) und [CRichEditView](../../mfc/reference/cricheditview-class.md), passen die Dokument\-\/Ansichtarchitektur den neuen allgemeinen Steuerelemente an, die von Windows 95\/98\- und Windows NT\-Versionen 3,51 und höher unterstützt werden.  Weitere Informationen über die Dokument\-\/Ansichtarchitektur, finden Sie unter [Dokument\-\/Ansichtarchitektur](../../mfc/document-view-architecture.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [CView Class](../../mfc/reference/cview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CTreeView Class](../../mfc/reference/ctreeview-class.md)   
 [CListView Class](../../mfc/reference/clistview-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)