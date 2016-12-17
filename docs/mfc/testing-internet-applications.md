---
title: "Testen von Internetanwendungen"
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
  - "Debuggen [MFC], Webanwendungen"
  - "Debuggen von Webanwendungen, Testen von Anwendungen"
  - "Internet Debuggen und Testen"
  - "Testen, Internetanwendungen"
  - "Webanwendungen, Testen"
ms.assetid: ac4c74e3-d4ad-4e19-8f6c-e270de067f01
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Testen von Internetanwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt mehrere eindeutige Testsherausforderungen im Internet, besonders für Anwendungen, die auf einem Webserver ausgeführt werden.  Die ursprünglichen Tests sind wahrscheinlich mit einem Einzelbenutzer\- Clients ausgeführt, der auf einen Testserver herstellt.  Dies ist für das Debuggen des Codes.  
  
 Sie möchten auch unter realen Bedingungen testen: wenn die mehrerer Clients über Hochgeschwindigkeits\-Verbindungen sowie langsamen seriellen Linien verbunden sind, einschließlich Modem\-Verbindungen.  Es kann schwierig, echte Bedingungen zu simulieren, ist jedoch durch das näher Verbringen der Zeit, die mögliche Szenarios entworfen und sie ausgeführt wird.  Wenn möglich, sollten Sie auch Tools verwenden, um Kapazitäts\- und Belastungstests verwendet.  Manche Klassen von Fehlern, z Fehlern der zeitlichen Steuerung, ist schwer zu finden und zu reproduzieren.  
  
 Eine der ersten Herausforderungen bei der Internet\-Programmierung ist die Sichtbarkeit.  Viele Zugriffe zu der Site verlangsamen möglicherweise den Server.  Sie möchten den Server ordnungsgemäß eingeschränkt.  Sie möchten alle verhindern, die dem Computer eines Benutzers destruktiv sein könnte, wenn die Anwendung fehlschlägt, \(z Beschädigung der Daten beim Schreiben in die Registrierung oder beim Schreiben in den Cookies im Client\).  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)