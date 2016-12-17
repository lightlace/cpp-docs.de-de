---
title: "Fensterzerst&#246;rungssequenz"
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
  - "CWnd-Objekte, Zerstörungssequenz"
  - "Zerstören von Fenstern"
  - "Zerstörung, Fenster"
  - "Reihenfolge [C++]"
  - "Reihenfolge [C++], Fensterzerstörung"
  - "Fenster [C++], Zerstören"
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Fensterzerst&#246;rungssequenz
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im MFC\-Framework wenn der Benutzer das Rahmenfenster enthält, wird der Standard\- [OnClose](../Topic/CWnd::OnClose.md)\-Handler des Fensters [DestroyWindow](../Topic/CWnd::DestroyWindow.md) auf.  Die letzte aufgerufene Memberfunktion, wenn das Windows\-Fenster zerstört wird, ist [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), die eine Bereinigung durchführt, Aufrufe die Memberfunktion [Standard](../Topic/CWnd::Default.md), um Windows\-Bereinigung auszuführen und zuletzt wird die virtuelle Memberfunktion [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md) auf.  Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung von `PostNcDestroy` löscht das C\+\+\-Fensterobjekt.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Fensterarbeitsspeicher zuordnen und Freigeben](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Trennen von CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## Siehe auch  
 [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)