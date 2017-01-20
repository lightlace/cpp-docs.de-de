---
title: "Erstellen eigener Dialogfeldklassen"
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
  - "Dialogfelder [C++], Erstellen"
  - "Dialogklassen, Assistent zum Hinzufügen von Klassen"
  - "Dialogklassen, Erstellen"
  - "Dateien [C++], Erstellen"
  - "MFC-Dialogfelder, Erstellen"
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eigener Dialogfeldklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für jedes Dialogfeld im Programm, erstellen Sie eine neue Dialogklasse, um die Dialogfeldressource zu arbeiten.  
  
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md) erläutert, wie eine neue erstellt Dialogfeldklasse.  Wenn Sie eine Dialogfeldklasse mit dem Assistenten zum Hinzufügen von Klassen erstellen, erstellt sie die folgenden Artikel in. H und CPP\-Dateien, die Sie angeben:  
  
 In. Außerdem:  
  
-   Eine Klassendeklaration für die Dialogfeldklasse.  Die Klasse wird von [CDialog\-Klasse](../mfc/reference/cdialog-class.md) abgeleitet.  
  
 in der CPP\-Datei:  
  
-   Eine Meldungszuordnung für die Klasse.  
  
-   Ein Standardkonstruktor für das Dialogfeld.  
  
-   Eine Überschreibung der Memberfunktion [DoDataExchange](../Topic/CWnd::DoDataExchange.md).  Bearbeiten Sie diese Funktion.  Sie wird für Dialogdatenaustausch\- Validierungsfunktionen und verwendet, wie in [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md) weiter unten beschrieben.  
  
## Siehe auch  
 [Erstellen einer Dialogfeldklasse mit Code\-Assistenten](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)