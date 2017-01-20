---
title: "Ausf&#252;hren von Memberfunktion"
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
  - "CWinApp-Klasse, Run"
  - "Nachrichtensystem in CWinApp::Run"
  - "Meldungen, Schleifen"
  - "Run-Methode, Nachrichten- und Leerlaufverarbeitung"
  - "WinMain-Methode"
  - "WinMain-Methode, calls CWinApp::Run"
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Ausf&#252;hren von Memberfunktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Framework\-Anwendung aufwendet den Großteil der Zeit in der [Ausführen](../Topic/CWinApp::Run.md)\-Memberfunktion der Klasse [CWinApp](../mfc/reference/cwinapp-class.md).  Nach Initialisierung `WinMain` ruft **Ausführen** auf, um die Meldungsschleife zu verarbeiten.  
  
 **Ausführen** wird über eine Nachrichtenschleife rad und überprüft die Meldungswarteschlange nach verfügbaren Meldungen.  Wenn eine Nachricht verfügbar ist, wird **Ausführen** diese Aktion für weiter.  Wenn keine Nachrichten verfügbar sind, das häufig zutrifft, **Ausführen** Ruft `OnIdle` auf, um eines Leerlaufs auszuführen, die verarbeitet, dass Sie möglicherweise oder das Framework durchgeführt benötigen.  Wenn keine Meldungen und keine Leerlaufverarbeitung gibt, auszuführen, wartet die Anwendung, wenn etwas geschieht.  Wenn die Anwendung **Ausführen** endet, ruft `ExitInstance` auf.  Die Abbildung in [OnIdle\-Memberfunktion](../mfc/onidle-member-function.md) zeigt die Aktionsfolge in der Meldungsschleife an.  
  
 Das Meldungsweiterleiten hängt von der Art von Meldung ab.  Weitere Informationen finden Sie unter [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md).  
  
## Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)