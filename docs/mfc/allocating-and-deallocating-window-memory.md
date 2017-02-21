---
title: "Reservieren und Freigeben von Fensterspeicher | Microsoft Docs"
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
  - "Speicherreservierung, Fensterobjekte"
  - "Speicherfreigabe"
  - "Speicherfreigabe, Arbeitsspeicher (Fenster)"
  - "Speicher für Windows-Objekte"
  - "Speicher für Windows-Objekte, Reservieren"
  - "Fensterobjekte, Freigeben von Speicher für"
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Reservieren und Freigeben von Fensterspeicher
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie den Operator **löschen** C\+\+, um ein Rahmenfenster oder Ansicht zu zerstören.  Stattdessen rufen Sie die `CWnd`\-Memberfunktion `DestroyWindow` auf.  Rahmenfenster sollten auf dem Heap mit Operator **neu** daher zugeordnet werden.  Seien Sie vorsichtig, wenn Sie Rahmenfenstern auf dem Stapelrahmen oder global zuordnen.  Andere Fenster sollten im Stapelrahmen zugeordnet werden, wenn immer möglich.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Trennen von CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## Siehe auch  
 [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)