---
title: Message-Behandlung und Zuordnung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e6c13ed0bb19ef1ed2864378e151c6be8d98887
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="message-handling-and-mapping"></a>Meldungsbehandlung und -zuordnung
Diese Artikelreihe wird beschrieben, wie Meldungen und Befehle durch MFC-Frameworks verarbeitet werden und wie Sie sie mit Ihren jeweiligen Handlerfunktionen zu verbinden.  
  
 In herkömmlichen Programmen für Windows Windows-Meldungen in einer großen Switch-Anweisung in eine Fensterprozedur behandelt werden. Stattdessen verwendet MFC [meldungszuordnungen](../mfc/message-categories.md) , direkte Nachrichten unterschiedliche Klassenmemberfunktionen zuzuordnen. Meldungszuordnungen sind effizienter als virtuelle Funktionen für diesen Zweck, und ermöglichen den Nachrichten von den am besten geeigneten C++-Objekt behandelt werden: Anwendung, Dokument anzeigen und So weiter. Sie können eine einzelne Nachricht oder eine Reihe von Nachrichten, die Befehls-IDs zuordnen oder Steuerelement-IDs.  
  
 **WM_COMMAND** Nachrichten – in der Regel von Menüs, Symbolleisten-Schaltflächen und Zugriffstasten generiert – auch die meldungszuordnungsmechanismus verwenden. MFC definiert einen Standard [routing](../mfc/command-routing.md) von befehlsmeldungen zwischen der Anwendung, frame-Fensters, Ansicht und aktive Dokumente in Ihrem Programm. Sie können die dieses routing bei Bedarf überschreiben.  
  
 Meldungszuordnungen geben auch eine Möglichkeit zum Aktualisieren von Benutzeroberflächenobjekten (z. B. Menüs und Symbolleisten-Schaltflächen), aktivieren oder deaktivieren sie entsprechend den aktuellen Kontext.  
  
 Allgemeine Informationen über Nachrichten und Warteschlangen in Windows finden Sie unter [Nachrichten und Warteschlangen](http://msdn.microsoft.com/library/windows/desktop/ms632590) im Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [Wie das Framework einen Message-Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [So durchsucht das Framework Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)  
  
-   [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [Vorgehensweise beim Anzeigen von Befehlsinformationen in der Statusleiste](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [Dynamische Aktualisierung von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)  
  
-   [Vorgehensweise: Erstellen einer Meldungszuordnung für eine Vorlagenklasse](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [CWnd-Klasse](../mfc/reference/cwnd-class.md)   
 [CCmdTarget-Klasse](../mfc/reference/ccmdtarget-class.md)
