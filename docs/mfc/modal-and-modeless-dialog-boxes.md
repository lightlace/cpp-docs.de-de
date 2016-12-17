---
title: "Modale und nicht modale Dialogfelder"
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
  - "MFC-Dialogfelder, Modal"
  - "MFC-Dialogfelder, Nicht modal"
  - "Modale Dialogfelder"
  - "Nicht modale Dialogfelder"
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Modale und nicht modale Dialogfelder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können [CDialog\-Klasse](../mfc/reference/cdialog-class.md)\-Klasse verwenden, um zwei Arten Dialogfelder zu verwalten:  
  
-   *Modale Dialogfelder*, die den Benutzer erfordern, reagiert, bevor das Programm fortsetzen  
  
-   *Nicht modale Dialogfelder*, die auf dem Bildschirm bleiben und können jederzeit verfügbar sind, aber lassen andere Benutzeraktivitäten  
  
 Die Ressourcenbearbeitung und der für das Erstellen einer Dialogfeldvorlage sind für modale und nicht modale Dialogfelder.  
  
 Das Erstellen eines Dialogfelds für das Programm benötigte die folgenden Schritte:  
  
1.  Verwenden Sie [Dialog\-Editor](../mfc/dialog-editor.md), um das Dialogfeld zu entwerfen und eine Dialogfeldvorlagen\-Ressource zu erstellen.  
  
2.  Erstellen Sie eine Dialogfeldklasse.  
  
3.  Schließen Sie [die Steuerelemente der Dialogfeldressource in den Meldungshandlern](../mfc/adding-event-handlers-for-dialog-box-controls.md) in der Dialogfeldklasse an.  
  
4.  Fügen Sie die zusätzlichen Felddatenmember hinzu, die in den Steuerelementen des Dialogfelds und [Dialogdatenaustausch](../mfc/dialog-data-exchange.md) und [Dialogfelddatenvalidierungen](../mfc/dialog-data-validation.md) für die Steuerelemente anzugeben zugeordnet werden.  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)