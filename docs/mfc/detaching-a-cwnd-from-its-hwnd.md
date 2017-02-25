---
title: "Trennen eines CWnd von seinem HWND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd-Objekte, Trennen vom HWND"
  - "Detach-Methode (CWnd class)"
  - "Trennen von CWnds von HWNDs"
  - "HWND, Trennen von CWnd von"
  - "Entfernen von HWNDs von CWnds"
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Trennen eines CWnd von seinem HWND
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie die Objekte `HWND` Beziehung umgehen müssen, MFC stellt eine andere `CWnd`\-Memberfunktion, [Trennen](../Topic/CWnd::Detach.md), die das vom C\+\+\-Fensterobjekt Windows\-Fenster trennt.  Dies verhindert, dass der Destruktor das Windows\-Fenster zerstört, wenn das Objekt zerstört wird.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Fensterarbeitsspeicher zuordnen und Freigeben](../mfc/allocating-and-deallocating-window-memory.md)  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)