---
title: "Funktionsweise von Rahmenfenstern"
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
  - "Rahmenfenster, Information über Rahmenfenster"
  - "Rahmenfenster, Aufgaben"
  - "MFC, Rahmenfenster"
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsweise von Rahmenfenstern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Neben eine Ansicht einfach gestalten Rahmenfenster, sind für die zahlreichen Aufgaben verantwortlich, die sobald der Frame in seine Ansicht und in der Anwendung gehören, koordinieren.  [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) erben von [CFrameWnd](../mfc/reference/cframewnd-class.md), sodass sie `CFrameWnd`\-Funktionen sowie über neue Funktionen, die sie hinzufügen.  Beispiele des gehören der untergeordneten Fenster zeigt, Steuerelemente wie Schaltflächen und Listenfelder und Steuerleisten, einschließlich Symbolleisten, Statusleisten und Dialogleisten an.  
  
 Das Rahmenfenster ist für die Verwaltung des Layouts der untergeordneten Fenster zuständig.  Im MFC\-Framework positioniert ein Rahmenfenster Steuerleisten alle, Ansichten und untergeordnete Fenster innerhalb des Clientbereichs.  
  
 Das auch Rahmenfenster werden Befehle an die Ansichten weitergegeben und kann auf Benachrichtigungsmeldungen von den Steuerfenstern reagieren.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Steuerleisten \(wie in das Rahmenfenster dort\)](../mfc/control-bars.md)  
  
-   [Menüs, Steuerleisten und Zugriffstasten verwalten \(wie in das Rahmenfenster dort\)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Befehls\-Routing \(vom Rahmenfenster zu seiner Ansicht und anderen Befehlszielen\)](../mfc/command-routing.md)  
  
-   [Dokument\/View\- Architektur](../mfc/document-view-architecture.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
-   [Steuerelemente](../mfc/controls-mfc.md)  
  
## Siehe auch  
 [Rahmenfenster](../mfc/frame-windows.md)