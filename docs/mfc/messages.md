---
title: "Meldungen | Microsoft Docs"
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
  - "Meldungen"
  - "Meldungen, MFC"
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Meldungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Nachrichtenschleife in der **Ausführen**\-Memberfunktion der `CWinApp`\-Klasse ruft die in der Warteschlange enthaltenen Meldungen ab, die durch verschiedene Ereignisse generiert werden.  Wenn der Benutzer mit der Maus geklickt hat, sendet Windows einige mausbezogene Meldungen, wie `WM_LBUTTONDOWN`, wenn die linke Maustaste gedrückt wird und `WM_LBUTTONUP`, wenn die linke Maustaste losgelassen wird.  Die Implementierung des Framework der Anwendungsnachrichtenschleife stellt die Meldung an das entsprechende Fenster aus.  
  
 Die wichtigen Kategorien von Meldungen werden in [Meldungs\-Kategorien](../mfc/message-categories.md) beschrieben.  
  
## Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)