---
title: "Speicherverwaltung"
ms.custom: na
ms.date: "12/13/2016"
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
  - "Speicher"
  - "Speicherreservierung"
  - "Speicherreservierung, MFC"
  - "Speicher, Verwalten"
  - "MFC, Speicherverwaltung"
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherverwaltung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Gruppe Artikel wird beschrieben, wie die grundlegenden Dienste der Microsoft Foundation Class\-Bibliothek " \(MFC\-Bibliothek\) verknüpft der Speicherverwaltung verwendet.  Speicherbelegung kann in zwei Hauptkategorien unterteilt werden: Framezuordnungen und \-Heapbelegungen.  
  
 Der Hauptunterschied zwischen den beiden Zuordnungstechniken ist mit der Framezuordnung, die Sie mit dem tatsächlichen Speicherblock auch bearbeiten, während mit Heapreservierung Ihnen immer ein Zeiger auf den Speicherblock angegeben werden.  Ein weiterer wichtiger Unterschied zwischen den zwei Schemas ist, dass Frameobjekte automatisch gelöscht werden, während Heapobjekte vom Programmierer explizit gelöscht werden müssen.  
  
 So Nicht\-MFC\-Information über Speicherverwaltung in Programmen für Windows, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Speicherverwaltung](http://msdn.microsoft.com/library/windows/desktop/aa366779).  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Feld Zuordnung](../mfc/memory-management-frame-allocation.md)  
  
-   [Heapreservierung](../mfc/memory-management-heap-allocation.md)  
  
-   [Speicherbelegung für ein Array](../mfc/memory-management-examples.md)  
  
-   [Freigeben von Speicher für ein Array vom Heap](../mfc/memory-management-examples.md)  
  
-   [Speicherbelegung für eine Datenstruktur](../mfc/memory-management-examples.md)  
  
-   [Speicherbelegung für ein Objekt](../mfc/memory-management-examples.md)  
  
-   [In der Größe veränderbare Speicherblöcke](../mfc/memory-management-resizable-memory-blocks.md)  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)