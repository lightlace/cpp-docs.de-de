---
title: "Zerst&#246;ren des Dialogfelds"
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
  - "Zerstörung, Dialogfeld"
  - "Dialogfelder, Löschen"
  - "Dialogfelder, Zerstören"
  - "Dialogfelder, Entfernen"
  - "MFC-Dialogfelder, Zerstören"
  - "Modale Dialogfelder, Zerstören"
  - "Nicht modale Dialogfelder, Zerstören"
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Zerst&#246;ren des Dialogfelds
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Modale Dialogfelder werden normalerweise im Stapelrahmen erstellt und wann die Funktion zerstört, die sie endet erstellt hat.  Der Destruktor des Dialogfeldobjekts wird aufgerufen, wenn das Objekt den Gültigkeitsbereich verlässt.  
  
 Nicht modale Dialogfelder werden normalerweise durch eine übergeordnete Ansicht oder ein Rahmenfenster \- das Hauptrahmenfenster oder ein Dokumentrahmenfenster Anwendung erstellt und verwendet.  Der standardmäßige Handler [OnClose](../Topic/CWnd::OnClose.md) ruft [DestroyWindow](../Topic/CWnd::DestroyWindow.md) auf, der das Dialogfeldfenster zerstört.  Wenn das Dialogfeld allein stehen, ohne Zeiger darauf oder anderen spezieller Besitzsemantik, sollten Sie [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md) überschreiben, um das C\+\+\-Dialogfeldobjekt zu zerstören.  Sie sollten [OnCancel](../Topic/CDialog::OnCancel.md) auch überschreiben und `DestroyWindow` aus dafür aufrufen.  Wenn nicht, sollte der Besitzer des Dialogfelds das C\+\+\-Objekt zerstören, wenn nicht mehr erforderlich ist.  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)