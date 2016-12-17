---
title: "Ein Portrait der Dokument-/Ansichtarchitektur"
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
  - "Dokument-/Ansichtsarchitektur"
  - "Dokument-/Ansichtsarchitektur, Informationen über Dokument-/Ansichtsarchitektur"
  - "Dokument-/Ansichtsarchitektur, Zugriff auf Daten aus der Ansicht"
  - "Dokumente, Zugriff auf Daten aus der Ansicht"
  - "Dokumente, Mehrere Ansichten"
  - "Dokumente, Ansichten"
  - "Eingabe, view-Klasse"
  - "Mehrere Ansichten, Aktualisieren aus Dokumenten"
  - "Ansichten, Zugriff auf Dokumentdaten aus"
  - "Ansichten, und Benutzereingabe"
  - "Ansichten, Aktualisieren"
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Ein Portrait der Dokument-/Ansichtarchitektur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dokumente und Ansichten werden in einer normalen MFC\-Anwendung zugeordnet.  Daten werden im Dokument gespeichert, und die Ansicht enthält privilegierten Zugriff auf die Daten.  Die Trennung des Dokuments von der Ansicht werden die Speicherung und Verwaltung von Daten von der Anzeige.  
  
## erhalten, um Daten von der Ansicht zu dokumentieren  
 Die Ansicht greift auf die Daten des Dokuments entweder mit der [GetDocument](../Topic/CView::GetDocument.md)\-Funktion, die einen Zeiger auf das Dokument zurückgibt, oder indem Sie den Ansichtsklassenwechselstrom \+\+ `friend` der Dokumentklasse macht.  Die Ansicht verwendet dann den Zugriff auf die Daten, um die Daten abzurufen, wenn es bereit ist, ihn zu zeichnen oder anderweitig zu bearbeiten.  
  
 Von der [OnDraw](../Topic/CView::OnDraw.md)\-Memberfunktion der Ansicht, wird die Ansicht **GetDocument**, um einen Dokumentzeiger zu erhalten.  Anschließend verwendet dieser Zeiger, um einen `CString` Datenmember im Dokument zuzugreifen.  Die Ansicht führt die Zeichenfolge der `TextOut`\-Funktion.  Um den Code für dieses Beispiel angezeigt wird, finden Sie unter [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md).  
  
## Benutzereingaben in der Ansicht  
 Die Ansicht interpretierte auch einen Mausklick innerhalb \- entweder als Auswahl oder Bearbeitung von Daten.  Entsprechend interpretierte sie möglicherweise Tastatureingaben als Dateneingabe oder Bearbeitung.  Nehmen Sie die Benutzer eine Zeichenfolge in einer Ansicht an, die Text verwaltet.  Die Ansicht ruft einen Zeiger auf das Dokument und verwendet den Zeiger, um die neuen Daten an Dokument zu übergeben, das ihn in einer Datenstruktur gespeichert.  
  
## Aktualisieren mehrerer Ansichten des gleichen Dokuments  
 In einer Anwendung mit mehreren Ansichten des gleichen Dokuments \- beispielsweise einem unterteilten in einem Text\-Editor die \- Ansicht werden zunächst die neuen Daten in das Dokument.  Anschließend ruft sie die [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)\-Memberfunktion des Dokuments, die alle Ansichten des Dokuments überprüfen, um zu aktualisieren und gibt die neuen Daten.  Dies synchronisiert die Ansichten.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Vorteile der Dokument\-\/Ansichtarchitektur](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Alternativen zur Dokument\-\/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)