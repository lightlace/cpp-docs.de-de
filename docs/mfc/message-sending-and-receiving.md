---
title: "Senden und Empfangen von Meldungen | Microsoft Docs"
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
  - "Steuerelemente-Benachrichtigungsmeldungen"
  - "Nachrichten [C++], MFC"
  - "Nachrichten [C++], Empfangen"
  - "Nachrichten [C++], Senden"
  - "MFC [C++], Meldungen"
  - "Windows-Nachrichten [C++], Behandeln in MFC"
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Senden und Empfangen von Meldungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Betrachten Sie den sendenden Teil des Prozesses und wie das Framework reagiert.  
  
 Die meisten Meldungen liefern der Benutzerinteraktion mit dem Programm.  Befehle werden von Mausklicks in den Menüelementen oder den Symbolleisten\-Schaltflächen oder durch Zugriffstastentastatureingaben generiert.  Der Benutzer generiert auch Windows\-Meldungen um ein Fenster beispielsweise verschieben oder Größe ändern.  Andere Windows\-Meldungen werden gesendet, wenn Ereignisse wie Programmstart oder Threadende, während Fenster abrufen oder den Fokus verlieren, z. B. auftreten.  Steuerelement\-Benachrichtigungen werden von Mausklicks oder andere Benutzerinteraktionen mit einem Steuerelement, wie eine Schaltfläche oder ein Listenfeld\-Steuerelement in einem Dialogfeld generiert.  
  
 Die **Ausführen**\-Memberfunktion der `CWinApp`\-Klasse ruft Meldungen ab und stellt sie an das entsprechende Fenster aus.  Die meisten Befehlsmeldungen werden z Hauptrahmenfenster der Anwendung gesendet.  `WindowProc`, das die Klassenbibliothek vordefiniert ist, ruft die Meldungen und leitet sie anders weiter, abhängig von der Kategorie der Meldung.  
  
 Betrachten Sie nun den empfangenden Teil des Prozesses.  
  
 Der ursprüngliche Empfänger einer Meldung ein Window\-Objekt sein muss.  Windows\-Meldungen werden normalerweise direkt von diesem Window\-Objekt bearbeitet.  Beherrschen Sie die Meldungen und im Hauptrahmenfenster der Anwendung stammen normalerweise, rufen Sie die BefehlZielkette weitergeleitet ab, die in [Befehls\-Routing](../mfc/command-routing.md) beschrieben wird.  
  
 Jedes Objekt, das dem Empfangen von Nachrichten oder von Befehlen anzeigen kann, verfügt über eine eigene Meldungszuordnung, die eine Meldung oder ein Befehl durch den Namen des Handlers zuordnet.  
  
 Wenn ein BefehlZielobjekt eine Meldung oder ein Befehl erhält, sucht er die Meldungszuordnung für eine Übereinstimmung.  Wenn sich kein Handler für die Meldung gefunden wird, ruft der den Handler auf.  Weitere Informationen dazu, wie Meldungszuordnungen gefunden werden, finden Sie unter [Wie das Framework Meldungszuordnungen sucht](../mfc/how-the-framework-searches-message-maps.md).  Verweisen Sie wieder Abbildung [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md).  
  
## Siehe auch  
 [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)