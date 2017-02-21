---
title: "Drucken und Druckvorschau | Microsoft Docs"
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
  - "Druckvorschau"
  - "Seitenansicht"
  - "Drucken [C++]"
  - "Drucken [C++], Seitenansicht"
  - "Drucken [MFC]"
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Drucken und Druckvorschau
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC unterstützt Drucken und Druckvorschau für die Dokumente des Programms zur Klasse [CView](../mfc/reference/cview-class.md).  In grundlegenden Drucken und Druckvorschau überschreiben Sie [OnDraw](../Topic/CView::OnDraw.md) einfach Memberfunktion der Ansichtsklasse, die Sie rückgängig vornehmen müssen.  Diese Funktion kann zur Ansicht auf den Bildschirm, zu einem Druckergerätekontext für einen tatsächlichen Drucker oder einem Gerätekontext zeichnen, der den Drucker auf dem Bildschirm simuliert.  
  
 Sie können auch Code hinzufügen, um paginierten Dokumentdruck und \-Vorschau zu verwalten, der gedruckten Dokumente zum Paginieren, und ihnen Kopf\- und Fußzeilen hinzuzufügen.  
  
 Diese Gruppe von Artikeln erläutert, wie das Drucken in der Microsoft Foundation Class\-Bibliothek " \(MFC\-Bibliothek\) implementiert wird und wie die Druckarchitektur nutzt, die bereits in das Framework erstellt wird.  Die Artikel beschrieben, wie MFC einfache Implementierung der Seitenansichtsfunktionalität unterstützt und wie Sie diese Funktionalität verwenden und ändern können.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Drucken](../mfc/printing.md)  
  
-   [Seitenansichtsarchitektur](../mfc/print-preview-architecture.md)  
  
-   [Beispiel](../top/visual-cpp-samples.md)  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)