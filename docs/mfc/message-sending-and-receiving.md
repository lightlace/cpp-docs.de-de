---
title: Senden und Empfangen von Meldungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55f450085c446503ebf86960dbee1b0d930691c2
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932003"
---
# <a name="message-sending-and-receiving"></a>Senden und Empfangen von Meldungen
Betrachten Sie den Sendevorgang des Prozesses und wie das Framework reagiert.  
  
 Die meisten Nachrichten ergeben durch eine Benutzerinteraktion mit dem Programm haben. Befehle werden von Mausklicks auf Menüelemente und Symbolleisten-Schaltflächen oder durch Drücken von Zugriffstasten generiert. Der Benutzer wird generiert auch Windows-Meldungen, z. B. verschieben oder Ändern der Größe eines Fensters. Anderen Windows-Meldungen werden gesendet, wenn z. B. Programmstart oder Beendigung Ereignissen wie Windows abzurufen oder den Fokus verliert und so weiter. Steuerelemente-benachrichtigungsmeldungen werden vom Mausklicks oder andere Benutzerinteraktionen mit einem Steuerelement, z. B. eine Schaltfläche oder im Listenfeld-Steuerelement in einem Dialogfeld generiert.  
  
 Die `Run` Memberfunktion der Klasse `CWinApp` ruft Nachrichten ab und sendet sie an das entsprechende Fenster. Die meisten befehlsmeldungen werden an das Hauptrahmenfenster der Anwendung gesendet. Die `WindowProc` durch die Klasse Bibliothek ruft Nachrichten vorab definiert und diese unterschiedlich, abhängig von der Kategorie der empfangenen Nachricht weiterleitet.  
  
 Nun sehen wir uns die empfangenden Teil des Prozesses.  
  
 Der erste Empfänger einer Nachricht muss einem Fensterobjekt. Windows-Meldungen werden in der Regel direkt vom Fensterobjekt behandelt. Command-Meldungen, stammen in der Regel im Hauptrahmenfenster für die Anwendung, auf die Befehlsziel Kette, die in beschriebenen weitergeleitet [Befehlsrouting](../mfc/command-routing.md).  
  
 Jedes Objekt, das Empfangen von Nachrichten oder Befehle verfügt über eine eigene Nachricht diese Paare eine Nachricht oder einen Befehl mit dem Namen des entsprechenden Handler zugeordnet.  
  
 Wenn eine Befehlszielobjekt eine Nachricht oder einen Befehl empfängt, werden seine meldungszuordnung, nach einer Übereinstimmung gesucht. Wenn einen Ereignishandler für die Nachricht gefunden wird, ruft er den Handler. Weitere Informationen dazu, wie meldungszuordnungen durchsucht werden, finden Sie unter [wie das Framework sucht Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md). Finden Sie in der Abbildung erneut [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md).  
  
## <a name="see-also"></a>Siehe auch  
 [So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)

