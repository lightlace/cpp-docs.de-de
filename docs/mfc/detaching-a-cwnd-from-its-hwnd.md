---
title: "Trennen eines CWnd von seinem HWND"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
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