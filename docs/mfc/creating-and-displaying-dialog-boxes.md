---
title: "Erstellen und Anzeigen von Dialogfeldern"
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
  - "MFC-Dialogfelder, Erstellen"
  - "MFC-Dialogfelder, Anzeigen"
  - "Modale Dialogfelder, Erstellen"
  - "Nicht modale Dialogfelder, Erstellen"
  - "Öffnen von Dialogfeldern"
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen und Anzeigen von Dialogfeldern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein gleichzeitig zu erstellen ist ein Zweiphasenvorgang.  Erstellen Sie zuerst das gleichzeitig, Sie dann das Dialogfeld erstellt.  Modal und nicht modale Dialogfelder unterscheiden Sie sich ein wenig im Prozess, der verwendet wird, um sie zu erstellen und anzuzeigen.  Folgende Tabelle, z modale und nicht modale Dialogfelder normalerweise erstellt und angezeigt werden.  
  
### Dialogfeld\-Erstellung  
  
|Dialogfeldtyp|Wie Sie ihn erstellt|  
|-------------------|--------------------------|  
|[Modeless](../mfc/creating-modeless-dialog-boxes.md)|Erstellen Sie `CDialog`, und rufen Sie dann **Erstellen**\-Memberfunktion auf.|  
|[Modal](../mfc/creating-modal-dialog-boxes.md)|Konstrukt `CDialog`, rufen dann `DoModal`\-Memberfunktion auf.|  
  
 Sie können, wenn Sie möchten, erstellen das Dialogfeld von [Dialogfeldvorlage im Arbeitsspeicher](../mfc/using-a-dialog-template-in-memory.md), das Sie statt von einer Dialogfeldvorlagenressource erstellt haben.  Dies ist ein fortgeschrittenes Thema.  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)