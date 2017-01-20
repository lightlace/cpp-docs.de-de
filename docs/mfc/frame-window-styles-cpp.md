---
title: "Rahmenfensterstile (C++)"
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
  - "Rahmenfenster [C++], Stile"
  - "MFC [C++], Rahmenfenster"
  - "PreCreateWindow-Methode, Festlegen von Fensterstilen"
  - "Stile, Fenster"
  - "Fensterstile [C++]"
  - "Fenster [C++], MFC"
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
caps.latest.revision: 8
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Rahmenfensterstile (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Rahmenfenster, die Sie mit dem Framework erhalten, sind für die meisten Programme an, Sie können jedoch zusätzliche Flexibilität erhalten, indem Sie den erweiterten Funktionen [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) und die globale Funktion [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) MFC verwenden.  `PreCreateWindow` ist eine Memberfunktion von `CWnd`.  
  
 Wenn Sie **WS\_HSCROLL** anwenden und **WS\_VSCROLL** das Hauptrahmenfenster formatiert, werden sie stattdessen zum **MDICLIENT** Fenster angewendet, sodass Benutzer den Bereich **MDICLIENT** wechseln.  
  
 Wenn das **FWS\_ADDTOTITLE** Stilbit des Fensters festgelegt wird \(die sie standardmäßig ist\), wird die Ansicht im Rahmenfenster mit, welchem in der Titelleiste angezeigt Titel, sich des Fensters auf Grundlage den Dokumentnamen der Ansicht.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Untergeordnete MDI\-Fenster \(MDICLIENT\) verwalten](../mfc/managing-mdi-child-windows.md), das Fenster in MDI\-Frame, die die untergeordneten MDI\-Fenster enthält  
  
-   [Die Formate eines Fensters geändert wird, erstellt von MFC](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
-   [Fensterstile](../mfc/reference/window-styles.md)  
  
## Siehe auch  
 [Rahmenfenster](../mfc/frame-windows.md)