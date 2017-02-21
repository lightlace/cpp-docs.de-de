---
title: "Vorteile der Dokument-/Ansichtarchitektur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dokument-/Ansichtsarchitektur, Vorteile von"
  - "Ansichten, Vorteile"
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Vorteile der Dokument-/Ansichtarchitektur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der wichtigste Vorteil der MFC\-Dokument\-\/Ansichtsarchitektur ist, dass die Architekturstützmehreren Ansichten des gleichen Dokuments besonders zufrieden stellend ausgeführt wird. \(Wenn Sie nicht mehrere Ansichten benötigen und der kleine Mehraufwand der Dokument\/Ansicht in der Anwendung übertrieben ist, können Sie die Architektur vermeiden.  [Alternativen zur Dokument\-\/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md).\)  
  
 Angenommen, die Anwendung numerische Daten der Benutzer entweder in der Arbeitsblattform oder der in Diagrammform können.  Ein Benutzer die Rohdaten, in der Arbeitsblattform und ein Diagramm gleichzeitig finden, das aus Daten entsteht.  Sie zeigen diese getrennten Ansichten in separate Rahmenfenster oder in Splitterbereiche innerhalb eines einzelnen Fensters an.  Angenommen, die der Benutzer die Daten in einem Arbeitsblatt bearbeiten und die Änderungen finden kann, die sofort im Diagramm angezeigt werden.  
  
 In MFC werden die Arbeitsblattansicht und die Diagrammansicht auf der Grundlage verschiedener Klassen sein, die von Vorlagen CView abgeleitet wurden.  Beide Ansichten werden mit einem einzelnen Dokumentobjekt zugeordnet.  Die \- Archive die Daten \(bzw. wird möglicherweise aus einer Datenbank\).  Beide Ansichten greifen auf das Dokument zu und die Daten an, die sie daraus abrufen.  
  
 Wenn ein Benutzer eine der Ansichten aktualisiert, ruft dieses Ansichtsobjekt `CDocument::UpdateAllViews` auf.  Dieses Feature die Ansichten alles Dokuments und Aktualisierungen jeder Ansicht selbst mithilfe der neuesten Daten vom Dokument benachrichtigt.  Der einzelne Aufruf `UpdateAllViews` synchronisiert die verschiedenen Ansichten.  
  
 Dieses Szenario wäre schwer, ohne die Trennung von Daten aus der Ansicht zu codieren sein, insbesondere wenn die Ansichten die Daten selbst gespeichert haben.  Mit Dokument\/Ansicht ist es einfach.  Das Framework übernimmt die meisten der Koordinationsarbeit für Sie.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Alternativen zur Dokument\-\/Ansichtarchitektur Dokument](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)  
  
-   [CView::GetDocument](../Topic/CView::GetDocument.md)  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)