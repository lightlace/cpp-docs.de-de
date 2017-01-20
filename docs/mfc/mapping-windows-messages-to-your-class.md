---
title: "Zuordnen von Windows-Meldungen zu einer Klasse"
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
  - "Zuordnungen, Meldungen an Dialogklassen"
  - "Meldungszuordnungen [C++], in Dialogklasse"
  - "Meldungszuordnungen [C++], Zuordnen von Windows-Meldungen zu einer Klasse"
  - "Meldungen an Dialogklassen"
  - "Meldungen an Dialogklassen, Zuordnen"
  - "MFC-Dialogfelder, Windows-Meldungen"
  - "Windows-Nachrichten [C++], Zuordnen in Dialogklassen"
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Zuordnen von Windows-Meldungen zu einer Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie das Dialogfeld benötigen, die Windows\-Meldungen bearbeiten, überschreiben Sie die entsprechenden Handlerfunktionen.  Hierzu, verwenden Sie das Eigenschaftenfenster zu [Ordnen Sie die Meldungen zu](../mfc/reference/mapping-messages-to-functions.md) die Dialogfeldklasse.  Dadurch wird ein Eintrag in der Meldungszuordnung für jede Meldung und fügt den Meldungshandlermemberfunktionen der Klasse hinzu.  Verwenden Sie den Visual C\+\+\-Quellcode\-Editor, um Code in den Meldungshandlern zu schreiben.  
  
 Sie können Memberfunktionen von [CDialog\-Klasse](../mfc/reference/cdialog-class.md) und von den Basisklassen, besonders [CWnd](../mfc/reference/cwnd-class.md) auch überschreiben.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
-   [Häufig überschriebene Memberfunktionen](../mfc/commonly-overridden-member-functions.md)  
  
-   [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)