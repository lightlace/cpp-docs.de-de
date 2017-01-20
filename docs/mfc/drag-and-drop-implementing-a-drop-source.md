---
title: "Drag&#160;&amp;&#160;Drop: Implementieren einer Drag&#160;&amp;&#160;Drop-Quelle"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Drag & Drop, DoDragDrop aufrufen"
  - "Drag & Drop, Ablagequelle"
  - "Drag & Drop, Initiieren von Ziehvorgängen"
  - "Drag & Drop (OLE), DoDragDrop aufrufen"
  - "Drag & Drop (OLE), Ablagequelle"
  - "Drag & Drop (OLE), Initiieren von Ziehvorgängen"
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Drag&#160;&amp;&#160;Drop: Implementieren einer Drag&#160;&amp;&#160;Drop-Quelle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie die Anwendung Daten abruft, zu einem Drag & Drop\-Vorgangs bereitzustellen.  
  
 Grundlegende Implementierung einer Ablagequelle ist relativ einfach.  Der erste Schritt besteht darin, zu bestimmen, welche Ereignisse einen Ziehvorgang beginnen.  Empfohlene Benutzeroberflächenrichtlinien definieren den Beginn eines Ziehvorgangs als die Auswahl der Daten und `WM_LBUTTONDOWN`\-Ereignis, das auf einem Punktinnere die ausgewählten Daten fungiert.  Die Beispiele [OCLIENT](../top/visual-cpp-samples.md) und [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE führen diesen Richtlinien.  
  
 Wenn die Anwendung ein Container ist und die ausgewählten Daten verknüpft oder ein eingebettetes Objekt vom Typ `COleClientItem` sind, rufen Sie seine `DoDragDrop`\-Memberfunktion auf.  Erstellen Sie andernfalls ein `COleDataSource`\-Objekt, initialisieren Sie es mit der Auswahl, und rufen Sie die `DoDragDrop`\-Memberfunktion des Datenquellenobjekts auf.  Wenn die Anwendung ein Server ist, verwenden Sie `COleServerItem::DoDragDrop`.  Informationen zum Anpassen des Standard\-Drag & Drop\-Verhaltens, finden Sie im Artikel [Drag & Drop: Anpassen](../mfc/drag-and-drop-customizing.md).  
  
 Wenn `DoDragDrop``DROPEFFECT_MOVE` zurückgibt, Sie löschen die Quelldaten des Quelldokuments sofort.  Kein anderer Rückgabewert von `DoDragDrop` hat keinerlei Auswirkungen auf eine Ablagequelle.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Implementieren eines Ablageziels](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Anpassen von Drag & Drop](../mfc/drag-and-drop-customizing.md)  
  
-   [OLE\-Datenobjekte und \-Datenquellen Erstellen und Löschen eines Auflistungsobjekts](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Bearbeiten von OLE\-Datenobjekten und \-Datenquellen](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## Siehe auch  
 [Drag & Drop \(OLE\)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)   
 [CView::OnDragLeave](../Topic/CView::OnDragLeave.md)