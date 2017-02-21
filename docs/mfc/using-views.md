---
title: "Verwenden von Ansichten | Microsoft Docs"
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
  - "CView-Klasse, view-Architektur"
  - "Zeichnung, Daten"
  - "Interagieren mit Benutzer und Rollen von view-Klassen"
  - "MFC, Ansichten"
  - "Pixelbilddaten"
  - "Rendering von Daten"
  - "Benutzereingabe, Interpretieren durch view-Klasse"
  - "Ansichtsklassen, Rolle beim Anzeigen von Anwendungsdaten"
  - "Ansichtsklassen, Rolle beim Verwalten von Benutzerinteraktion"
  - "Ansichten, Verwenden"
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Verwenden von Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Aufgaben der Ansicht ist, die Daten des Dokuments für den Benutzer anzuzeigen grafisch und Benutzereingaben als Operationen im Dokument zu akzeptieren und interpretieren.  Aufgaben, die, falls diese die Ansichtsklasse schreiben, sind:  
  
-   Schreiben Sie [OnDraw](../Topic/CView::OnDraw.md)\-Memberfunktion der Ansichtsklasse, die die Daten des Dokuments rendert.  
  
-   Schließen Sie entsprechende Windows\-Meldungen und Benutzeroberflächen\-Objekte wie Menüelemente an Meldungshandlermemberfunktionen in der Ansichtsklasse an.  
  
-   Implementieren Sie die Handler, um Benutzereingaben zu interpretieren.  
  
 Außerdem müssen Sie möglicherweise andere `CView`\-Memberfunktionen in der abgeleiteten Ansichtsklasse überschreiben.  Insbesondere sollten Sie [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) überschreiben, um spezielle Initialisierung auszuführen, sodass die Ansicht und [OnUpdate](../Topic/CView::OnUpdate.md) Specialverarbeiten erfordert alle das ausführt, bevor die Ansicht selbst neu zeichnet.  Eine mehrseitige Dokumente müssen Sie auch [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) überschreiben, um das Drucken mit der Anzahl vonseiten, um zu drucken und andere Informationen zu initialisieren.  Weitere Informationen zum Überschreiben von `CView`\-Memberfunktionen, Klasse finden Sie unter [CView](../mfc/reference/cview-class.md) in der *MFC\-Referenz*.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Abgeleitete Ansichtsklassen verfügbar in MFC](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
-   [Interpretieren der Benutzereingaben über eine Ansicht](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Die Rolle der Ansicht im Drucken](../mfc/role-of-the-view-in-printing.md)  
  
-   [Bildlauf\- und Skalierungsansichten](../mfc/scrolling-and-scaling-views.md)  
  
-   [Dokumente und Ansichten initialisieren und Objects](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## Siehe auch  
 [Dokument\-\/Ansichtsarchitektur](../mfc/document-view-architecture.md)   
 [CFormView Class](../mfc/reference/cformview-class.md)   
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)