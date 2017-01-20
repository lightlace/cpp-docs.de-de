---
title: "Rahmenfensterklassen (Windows)"
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
  - "vc.classes.frame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rahmenfensterklassen, Referenz"
ms.assetid: 6342ec5f-f922-4da8-a78e-2f5f994c7142
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Rahmenfensterklassen (Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rahmenfenster sind Fenster, die eine Anwendung oder einen Teil einer Anwendung gestalten.  Rahmenfenster enthalten normalerweise weitere Fenster, wie Ansichten, Symbolleisten und Statusleisten.  Bei `CMDIFrameWnd` enthalten sie `CMDIChildWnd` kann Objekte indirekt.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Die Basisklasse für das Hauptrahmenfenster einer SDI\-Anwendung.  Auch die Basisklasse für weitere gesamten Rahmenfenster klassifiziert.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Die Basisklasse für das Hauptrahmenfenster einer MDI\-Anwendung.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Die Basisklasse für die Dokumentrahmenfenster einer MDI\-Anwendung.  
  
 [CMiniFrameWnd](../mfc/reference/cminiframewnd-class.md)  
 Ein Rahmenfenster mit halber Höhe in der Regel angezeigt um unverankerte Symbolleisten.  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 Stellt das Rahmenfenster für eine Ansicht bereit, wenn ein Serverdokument direkt bearbeitet wird.  
  
## Verwandte Klasse  
 `CMenu`\-Klasse bietet eine Schnittstelle, über die auf die Menüs der Anwendung zugreifen.  Es ist für Menüs dynamisch zur Laufzeit bearbeiten nützlich; wenn beispielsweise Menüelemente entsprechend Kontext hinzugefügt oder gelöscht werden.  Obwohl Menüs mit Rahmenfenstern meist sind, können sie mit anderen Dialogfeldern und Fenstern nonchild auch verwendet werden.  
  
 [CMenu](../mfc/reference/cmenu-class.md)  
 Kapselt `HMENU` ein Handle für die der Menüleiste und der Anwendung Popupmenüs.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)