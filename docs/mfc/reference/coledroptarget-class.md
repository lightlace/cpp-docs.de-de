---
title: "COleDropTarget Class"
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
  - "COleDropTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropTarget class"
  - "Drag & Drop, drop target"
  - "drop commands"
  - "drop commands, Annehmen"
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# COleDropTarget Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt den Kommunikationsmechanismus zwischen einem Fenster und der OLE\-Bibliotheken bereit.  
  
## Syntax  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](../Topic/COleDropTarget::COleDropTarget.md)|Erstellt ein `COleDropTarget`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](../Topic/COleDropTarget::OnDragEnter.md)|Aufgerufen, wenn der Cursor zuerst das Fenster eingibt.|  
|[COleDropTarget::OnDragLeave](../Topic/COleDropTarget::OnDragLeave.md)|Aufgerufen, wenn der Cursor aus dem Fenster gezogen wird.|  
|[COleDropTarget::OnDragOver](../Topic/COleDropTarget::OnDragOver.md)|Wiederholt aufgerufen, wenn der Cursor über das Fenster gezogen wird.|  
|[COleDropTarget::OnDragScroll](../Topic/COleDropTarget::OnDragScroll.md)|Aufgerufen, um zu bestimmen, ob der Cursor im Bildlaufbereich des Fensters gezogen wird.|  
|[COleDropTarget::OnDrop](../Topic/COleDropTarget::OnDrop.md)|Aufgerufen, wenn Daten in das Fenster abgelegt werden, Standardhandler.|  
|[COleDropTarget::OnDropEx](../Topic/COleDropTarget::OnDropEx.md)|Aufgerufen, wenn Daten in das Fenster abgelegt werden, ursprünglicher Handler.|  
|[COleDropTarget::Register](../Topic/COleDropTarget::Register.md)|Registriert das Fenster als gültiges Ablageziel.|  
|[COleDropTarget::Revoke](../Topic/COleDropTarget::Revoke.md)|Veranlasst das Fenster beenden, ein gültiges Ablageziel sein.|  
  
## Hinweise  
 Das Erstellen eines Objekts dieser Klasse ermöglicht einem Fenster, um Daten über den OLE\-Drag & Drop\-Mechanismus zu akzeptieren.  
  
 Um ein Fenster um abzurufen Ablagenbefehle zu akzeptieren, müssen Sie ein Objekt der Klasse `COleDropTarget` zuerst erstellen und dann die [Register](../Topic/COleDropTarget::Register.md)\-Funktion mit einem Zeiger auf den gewünschten `CWnd`\-Objekt als einziger Parameter auf.  
  
 Weitere Informationen über Drag & Drop\-Operationen mit OLE, finden Sie im Artikel [Drag & Drop \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC\-Beispiel HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleDropSource Class](../../mfc/reference/coledropsource-class.md)