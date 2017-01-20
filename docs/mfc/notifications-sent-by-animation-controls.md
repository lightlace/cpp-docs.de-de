---
title: "Von Animationssteuerelementen gesendete Benachrichtigungen"
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
  - "Animationssteuerungselemente [C++], Benachrichtigungen"
  - "CAnimateCtrl-Klasse, Benachrichtigungen"
  - "Steuerelemente [MFC], Animation"
  - "Benachrichtigungen, Animationssteuerungselemente"
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Von Animationssteuerelementen gesendete Benachrichtigungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Animationssteuerung \([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)\) sendet zwei verschiedene Typen Benachrichtigungsmeldungen.  Die Benachrichtigungen werden in Form von [Da WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachrichten gesendet.  
  
 Die [CAN\_START](http://msdn.microsoft.com/library/windows/desktop/bb761891) Meldung gesendet, sofern das Animationssteuerung die Wiedergabe eines Klipps gestartet wurde.  Die [CAN\_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893) Meldung gesendet, sofern das Animationssteuerung beendet oder angehalten hat, einen Klipp wiederzugeben.  
  
## Siehe auch  
 [Verwenden von CAnimateCtrl](../mfc/using-canimatectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)