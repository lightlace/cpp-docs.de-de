---
title: "COleDropSource Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDropSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDropSource class"
  - "Drag & Drop, drop source"
  - "Ziehvorgänge"
  - "drop target, dragging data to"
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleDropSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht die einem Ablageziel gezogen werden Daten.  
  
## Syntax  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](../Topic/COleDropSource::COleDropSource.md)|Erstellt ein `COleDropSource`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](../Topic/COleDropSource::GiveFeedback.md)|Ändert den Cursor während eines Drag & Drop\-Vorgangs.|  
|[COleDropSource::OnBeginDrag](../Topic/COleDropSource::OnBeginDrag.md)|Behandelt Mausauswahl während eines Drag & Drop\-Vorgangs.|  
|[COleDropSource::QueryContinueDrag](../Topic/COleDropSource::QueryContinueDrag.md)|Überprüft, ob das zum Ziehen zu finden, fortgesetzt werden soll.|  
  
## Hinweise  
 Die [COleDropTarget](../../mfc/reference/coledroptarget-class.md)\-Klasse behandelt den empfangenden Teil des Drag & Drop\-Vorgangs.  Das `COleDropSource`\-Objekt ist für das Bestimmen, wann ein Ziehvorgang startet, die Feedback bereitzustellen backs während des Ziehvorgangs und das Bestimmen zuständig, wenn der Ziehvorgang beendet.  
  
 Um ein `COleDropSource`\-Objekt zu verwenden, rufen Sie einfach den Konstruktor auf.  Dies vereinfacht den Prozess zum Bestimmen, welche Ereignisse, wie ein Mausklick, einen Ziehvorgang mithilfe [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md), [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md) oder [COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md)\-Funktion starten.  Diese Funktionen erstellen `COleDropSource` ein Objekt.  Sie sollten das Standardverhalten der überschreibbaren Funktionen `COleDropSource` ändern.  Diese Memberfunktionen werden den entsprechenden Zeiten vom Framework aufgerufen.  
  
 Weitere Informationen über Drag & Drop\-Operationen mit OLE, finden Sie im Artikel [Drag & Drop \(OLE\)](../../mfc/drag-and-drop-ole.md).  
  
 Weitere Informationen finden Sie unter [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## Anforderungen  
 **Header:**  afxole.h  
  
## Siehe auch  
 [MFC Sampling HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel OCLIENT](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)