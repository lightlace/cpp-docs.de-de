---
title: "Befehlsroutingklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlsrouting, Klassen"
  - "MFC, Befehlsrouting"
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Befehlsroutingklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während der Benutzer auf die Anwendung, indem er interagiert Menüs oder Steuerleistenschaltflächen mit der Maus auswählt, sendet die Anwendung Meldungen des betroffenen Benutzeroberflächeobjekt zu einem entsprechenden BefehlZielobjekt.  die Befehl\-Zielklassen, die von `CCmdTarget` abgeleitet werden, enthalten [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md) und die Klassen, die von ihnen abgeleitet werden.  Das Framework unterstützt das automatische Befehlsrouting, sodass die Befehle von der meisten nur behandelt werden können entsprechendes Objekt \- aktiv in der Anwendung.  
  
 Ein Objekt der Klasse `CCmdUI` wird der Update\-Befehlsbenutzeroberfläche der Befehlsziele an Handler \([ON\_UPDATE\_COMMAND\_UI](../Topic/ON_UPDATE_COMMAND_UI.md)\) übergeben, die es Ihnen ermöglichen, den Zustand der Benutzeroberfläche für einen bestimmten Befehl zu aktualisieren \(beispielsweise, die Überprüfung der Menüelemente überprüfen oder entfernen\).  Sie rufen `CCmdUI`\-Memberfunktionen des Objekts auf, um den Zustand des Benutzeroberflächenobjekts zu aktualisieren.  Dieser Vorgang ist identisch, ob das Benutzeroberflächenobjekt, das mit einem bestimmten Befehl zugeordnet ist, ein Menüelement oder eine oder beide Schaltfläche ist.  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 Fungiert als Basisklasse für alle Klassen Objekte, die auf Meldungen empfangen und reagieren können.  
  
 [CCmdUI](../mfc/reference/ccmdui-class.md)  
 Stellt eine programmgesteuerte Schnittstelle zum Aktualisieren von Benutzeroberflächenobjekten wie Menüelemente oder Steuerleistenschaltflächen bereit.  Das Befehlszielobjekt aktiviert, deaktiviert, überprüft und\/oder löscht das Benutzeroberflächeobjekt mit diesem Objekt.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)