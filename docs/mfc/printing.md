---
title: "Drucken"
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
  - "Dokumente, Drucken"
  - "Drucken [MFC]"
  - "Drucken [MFC], aus Framework"
  - "Ansichtsklassen, Druckvorgänge"
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Drucken
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Geräteunabhängige Anzeige Microsoft Windows\-Werkzeuge.  In MFC bedeutet dies, dass die gleichen Zeichnungsaufrufe, in der Memberfunktion `OnDraw` der Ansichtsklasse, zum Zeichnen auf der Anzeige und auf anderen Geräten zuständig sind, wie Drucker.  Die Seitenansicht ist das Zielgerät eine simulierte Druckerausgabe die Anzeige.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Ihrer Rolle im Drucken für die Rolle des Frameworks  
 die Ansichtsklasse hat folgende Aufgaben:  
  
-   Informieren Sie das Framework, wie viele Seiten im Dokument befinden.  
  
-   Wenn Sie aufgefordert werden, eine bestimmte Seite gedruckt, zeichnen Sie diesen Teil des Dokuments.  
  
-   Zuordnen zu und geben Sie alle Schriftarten oder anderen Graphics Device Interface \(GDI\)\- Ressourcen frei, die zum Drucken benötigt werden.  
  
-   Falls notwendig senden Sie alle Umschaltcodes, die erforderlich sind, um den Druckermodus zu ändern, bevor Sie eine angegebene Seite beispielsweise drucken um die Druckrichtung pro Seite zu ändern.  
  
 Die Aufgaben des Framework ist, wie folgt:  
  
-   Zeigen Sie das Dialogfeld **Drucken** an.  
  
-   Erstellen Sie ein [CDC](../mfc/reference/cdc-class.md)\-Objekt für den Drucker.  
  
-   Rufen Sie die [StartDoc](../Topic/CDC::StartDoc.md) und [EndDoc](../Topic/CDC::EndDoc.md)`CDC`\-Memberfunktionen des Objekts auf.  
  
-   Rufen Sie überprüft die Memberfunktion [StartPage](../Topic/CDC::StartPage.md) des Objekts `CDC`, informieren die Ansichtsklasse, welche Seite gedruckt werden soll, und rufen Sie die [EndPage](../Topic/CDC::EndPage.md)`CDC`\-Memberfunktion des Objekts auf.  
  
-   Rufen Sie überschreibbare Funktionen in der Ansicht mit den entsprechenden Situationen auf.  
  
 Die folgenden Elemente werden, wie das Framework Drucken und Druckvorschau unterstützt:  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Wie Standarddruck ausgeführt wurde](../mfc/how-default-printing-is-done.md)  
  
-   [mehrseitige Dokumente](../mfc/multipage-documents.md)  
  
-   [Kopf\- und Fußzeilen](../mfc/headers-and-footers.md)  
  
-   [Zuordnen von GDI\-Ressourcen für Druck](../mfc/allocating-gdi-resources.md)  
  
-   [Druckvorschau](../mfc/print-preview-architecture.md)  
  
## Siehe auch  
 [Drucken und Druckvorschau](../mfc/printing-and-print-preview.md)