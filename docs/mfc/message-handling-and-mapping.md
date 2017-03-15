---
title: "Meldungsbehandlung und -zuordnung | Microsoft Docs"
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
  - "Meldungsbehandlung"
  - "Meldungszuordnungen"
  - "MFC, Meldungen"
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Meldungsbehandlung und -zuordnung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Artikelfamilie beschreibt, wie Nachrichten und Befehle vom MFC\-Framework verarbeitet werden und wie Sie sie an ihrer Handlerfunktionen herstellen.  
  
 In herkömmlichen Programmen für Windows, werden Windows\-Meldungen in einer großen switch\-Anweisung in einer Fensterprozedur bearbeitet.  MFC verwendet stattdessen [Meldungszuordnungen](../mfc/message-categories.md), um Nachrichten zu direkten unterschiedlichen Klassenmemberfunktionen zuzuordnen.  Meldungszuordnungen sind effizienter als virtuelle Funktionen zu diesem Zweck, und sie ermöglichen die die meisten durch die Behandlung von Meldungen, entsprechendes C\+\+\-Objekt \- Anwendung, dokumentieren, zeigen, z. B. an.  Sie können eine einzelne Meldung oder einem Bereich von Meldungen, von Befehls\-IDs oder der Steuerelement\-IDs zuordnen.  
  
 **WM\_COMMAND** \- Meldungen normalerweise generiert durch Menüs, Symbolleisten\-Schaltflächen oder Zugriffstasten \- auch den Mechanismus zur Meldungszuordnung.  MFC definiert einen Standard [Routing](../mfc/command-routing.md) von Befehlsmeldungen mit der Anwendung, im Rahmenfenster, Ansicht und den aktiven Dokumenten im Programm.  Sie können das Routing überschreiben, wenn Sie benötigen.  
  
 Meldungszuordnungen stellen außerdem eine Möglichkeit, Benutzeroberflächen\-Objekte zu aktualisieren \(z Menüs und Symbolleisten\-Schaltflächen\) und aktivieren oder deaktivieren, um sie dem aktuellen Kontext zu entsprechen.  
  
 Allgemeine Informationen zu Meldungen und Meldungswarteschlangen in Windows, finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Meldungen und Meldungswarteschlangen](http://msdn.microsoft.com/library/windows/desktop/ms632590).  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Wie das Framework einen Meldungshandler aufruft](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [Wie das Framework Meldungszuordnungen sucht](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [Deklarieren von Meldungshandler\-Funktionen](../mfc/declaring-message-handler-functions.md)  
  
-   [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [Erstellen Befehls\-Informationen in der Statusleiste anzeigt](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [Dynamisches Update von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Gewusst wie: Erstellen einer Meldungszuordnung für eine Vorlagenklasse](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)   
 [CWnd\-Klasse](../mfc/reference/cwnd-class.md)   
 [CCmdTarget Class](../mfc/reference/ccmdtarget-class.md)