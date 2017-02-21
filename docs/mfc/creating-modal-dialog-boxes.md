---
title: "Erstellen von modalen Dialogfeldern | Microsoft Docs"
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
  - "MFC-Dialogfelder, Erstellen"
  - "MFC-Dialogfelder, Modal"
  - "Modale Dialogfelder, Erstellen"
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Erstellen von modalen Dialogfeldern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um ein modales Dialogfeld zu erstellen, rufen Sie einen der zwei öffentliche Konstruktoren auf, die in [CDialog\-Klasse](../mfc/reference/cdialog-class.md) deklariert werden.  Anschließend rufen Sie die [DoModal](../Topic/CDialog::DoModal.md)\-Memberfunktion des Dialogfeldobjekts auf, um das Dialogfeld anzuzeigen und Interaktion mit ihr zu verwalten, wenn der Benutzer auswählt OK oder Abbrechen.  Diese Verwaltung von `DoModal` ist, wie das Dialogfeld modal.  Für modalen Dialogfelder lädt `DoModal` die Dialogressource.  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)