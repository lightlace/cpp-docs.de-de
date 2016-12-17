---
title: "Die Rolle der Ansicht beim Drucken"
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
  - "CView-Klasse, Rolle beim Drucken"
  - "OnDraw-Methode, und Drucken"
  - "Drucken [MFC], OnDraw-Methode"
  - "Drucken [MFC], Ansichten"
  - "Druckansichten"
  - "Ansichten, Drucken"
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Die Rolle der Ansicht beim Drucken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Ansicht gibt auch zwei wichtigen Rollen erneut, wenn das zugeordnete Dokument druckt.  
  
 Die Ansicht:  
  
-   Verwendet den gleichen [OnDraw](../Topic/CView::OnDraw.md) Code, auf dem Drucker hinsichtlich Videofunktionen auf dem Bildschirm zeichnen.  
  
-   Verwaltet das Unterteilen des Dokuments Seiten für das Drucken.  
  
 Weitere Informationen über das Drucken und über die Rolle der Ansicht im Druck, finden Sie unter [Drucken und Druckvorschau](../mfc/printing-and-print-preview.md).  
  
## Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)