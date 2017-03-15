---
title: "Internetsicherheit (C++)"
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
  - "Codezugriffssicherheit [C++], Überlegungen zur Internetsicherheit"
  - "Codesignatur [C++]"
  - "Codesignatur [C++], Internetsicherheit"
  - "Digitale Signaturen, Internetsicherheit"
  - "Internetanwendungen, Sicherheit"
  - "Verwenden einer Sandbox"
  - "Sicherheit [MFC]"
  - "Sicherheit [MFC], Internet"
  - "Webanwendungssicherheit"
  - "Webanwendungssicherheit, Ansätze für die Internetsicherheit"
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Internetsicherheit (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Code ist ein ernstes Problem für Entwickler und für Benutzer von Internetanwendungen.  Es gibt Risiken: schädlicher Code, Code, denen manipuliert wurde und mit Code aus dem Unbekannten positioniert oder erstellt.  
  
 Es gibt zwei grundlegende Methoden zur Sicherheit bei der Entwicklung für das Internet.  Das Erste wird aufgerufen "Sandkasten". In dieser Vorgehensweise wird eine Anwendung an ein bestimmtes beschränkt, die von APIs festgelegt ist und von den möglicherweise gefährlichen wie Datei\-E\/A ausgeschlossen ist, in der ein Programm Daten auf dem Computer eines Benutzers löschen konnte.  Das zweite wird mithilfe der digitalen Signaturen implementiert.  Dieser Ansatz wird, als für Internet "shrinkwrap".  Code wird unter Verwendung der Technologie des entsprechenden privaten\/öffentlichen Schlüssel überprüft und signiert.  Bevor der Code ausgeführt wird, wird die digitale Signatur überprüft, um sicherzustellen, dass der Code von einer bekannten authentifizierten Quelle ist und dass der Code nicht geändert wurde, wird es signiert wurde.  
  
 Im ersten Fall Vertrauen darauf, dass die Anwendung kein Schaden wird und Sie dem Ursprung der Anwendung.  In dem zweiten werden digitale Signaturen verwendet, um die Echtheit zu überprüfen.  Digital\-Signierung ist ein industriekompatibles verwendete, z von Informationen über den Herausgeber des Codes zu identifizieren und bereitzustellen.  Seine Technologie basiert auf Standards, einschließlich RSA und X.509.  Browser ermöglichen normalerweise Benutzer, um auszuwählen, wenn sie Code eines unbekannten Ursprungs herunterladen und ausführen möchten.  
  
 Zusätzliche Informationen über und Codesignaturen andere Sicherheitsmaßnahmen ist im Internet verfügbar.  auf Informationen können von der MSDN Online\-Web\-Workshopsite oder [http:\/\/msdn.microsoft.com\/](http://msdn.microsoft.com/) über am World Wide Web Consortium an [http:\/\/www.w3.org\/](http://www.w3.org/) zugegriffen werden.  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)