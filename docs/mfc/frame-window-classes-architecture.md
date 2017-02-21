---
title: "Rahmenfensterklassen (Architektur) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rahmenfensterklassen, Dokument-/Ansichtsarchitektur"
ms.assetid: 5da01fb4-f531-46cc-914f-e422e4f07f5d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Rahmenfensterklassen (Architektur)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Dokument\-\/Ansichtarchitektur Rahmenfenster sind Fenster, die ein Ansichtsfenster enthalten.  Sie unterstützen auch Haben von den Steuerleisten, die an die Fenster angefügt werden.  
  
 In \(Multiple Document Interface \(MDI\)\- Anwendungen wird das Hauptfenster von `CMDIFrameWnd` abgeleitet.  Es enthält indirekt die Frames der Dokumente, die `CMDIChildWnd`\-Objekte sind.  `CMDIChildWnd`\-Objekte enthalten wiederum die Ansichten der Dokumente ein.  
  
 In \(Single Document Interface \(SDI\)\- Anwendungen enthält das Hauptfenster, abgeleitet von `CFrameWnd`, die Ansicht des aktuellen Dokuments.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Die Basisklasse für das Hauptrahmenfenster einer SDI\-Anwendung.  Auch die Basisklasse für weitere gesamten Rahmenfenster klassifiziert.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Die Basisklasse für das Hauptrahmenfenster einer MDI\-Anwendung.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Die Basisklasse für die Dokumentrahmenfenster einer MDI\-Anwendung.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Stellt das Rahmenfenster für eine Ansicht bereit, wenn ein Serverdokument direkt bearbeitet wird.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)