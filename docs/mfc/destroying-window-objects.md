---
title: "Zerst&#246;ren von Fensterobjekten"
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
  - "Rahmenfenster, Zerstören"
  - "Fensterobjekte, Löschen"
  - "Fensterobjekte, Zerstören"
  - "Fensterobjekte, Entfernen"
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Zerst&#246;ren von Fensterobjekten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie müssen mit eigenen untergeordneten Fenstern verwendet werden, um das C\+\+\-Fensterobjekt zu zerstören, wenn der Benutzer mit dem Fenster beendet wird.  Wenn diese Objekte nicht zerstört werden, stellt die Anwendung nicht den Speicher wieder her.  Glücklicherweise verwaltet das Framework Fensterzerstörung sowie für \-Erstellung Rahmenfenster, Ansichten und Dialogfelder.  Wenn Sie zusätzliche Fenster erstellen, sind Sie das Zerstören sie verantwortlich.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Fensterarbeitsspeicher zuordnen und Freigeben](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Trennen von CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Allgemeine Fenster\-Erstellungs\-Sequenz](../mfc/general-window-creation-sequence.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)