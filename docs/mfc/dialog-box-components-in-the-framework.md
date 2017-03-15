---
title: "Dialogfeld-Steuerelemente im Framework | Microsoft Docs"
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
  - "Dialogklassen, Dialogfeldkomponenten"
  - "Dialogvorlagen, MFC-Framework"
  - "MFC-Dialogfelder, Informationen über MFC-Dialogfelder"
  - "MFC-Dialogfelder, Erstellen"
  - "MFC-Dialogfelder, Dialogressource"
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Dialogfeld-Steuerelemente im Framework
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im MFC\-Framework ist ein Dialogfeld zwei Komponenten:  
  
-   Eine Dialogfeldvorlagen\-Ressource, die von Steuerelementen und ihrer Platzierung Dialogfelds angibt.  
  
     Die Dialogressource speichert eine Dialogfeldvorlage Windows, von der das Dialogfeld erstellt und es anzeigt.  Die Vorlage gibt die Eigenschaften des Dialogfelds, einschließlich Größe, Position, Format und Typen und Position der Steuerelemente des Dialogfelds angezeigt.  Normalerweise verwenden Sie eine Dialogfeldvorlage, die als Ressource gespeichert wird, aber Sie können eine eigene Vorlage im Arbeitsspeicher auch erstellen.  
  
-   Eine Dialogklasse, abgeleitet von [CDialog\-Klasse](../mfc/reference/cdialog-class.md), um eine programmgesteuerte Schnittstelle zum Verwalten des Dialogfelds bereitzustellen.  
  
     Ein Dialogfeld ist ein Fenster und wird einem Windows\-Fenster angefügt werden, falls sichtbar.  Wenn das Dialogfeld erstellt wird, wird die Dialogfeldvorlagen\-Ressource als Vorlage zum Erstellen von Steuerelementen des untergeordneten Fensters für das Dialogfeld verwendet wird.  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)