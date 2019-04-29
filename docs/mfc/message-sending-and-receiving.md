---
title: Senden und Empfangen von Meldungen
ms.date: 11/04/2016
helpviewer_keywords:
- Windows messages [MFC], handling in MFC
- control-notification messages [MFC]
- messages [MFC], receiving
- messages [MFC], MFC
- MFC, messages
- messages [MFC], sending
ms.assetid: 9ce189cb-b259-4c3b-b6f2-9cfbed18b98b
ms.openlocfilehash: bda261f4141a7ceb4e678535d9012650818fabce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384041"
---
# <a name="message-sending-and-receiving"></a>Senden und Empfangen von Meldungen

Betrachten Sie den Sendevorgang des Prozesses und das Framework wie reagiert werden soll.

Die meisten Nachrichten ergeben sich aus der Benutzerinteraktion mit dem Programm. Befehle werden von Mausklicks auf Menüelemente und Symbolleisten-Schaltflächen oder durch Drücken von Zugriffstasten generiert. Der Benutzer generiert Windows-Nachrichten nach, auch z. B. verschieben oder Ändern der Größe eines Fensters. Andere Windows-Meldungen werden immer dann gesendet, wenn z. B. beim Programmstart oder Beendigung Ereignissen wie Windows abzurufen oder den Fokus verliert und so weiter. Steuerelemente-benachrichtigungsmeldungen werden von Mausklicks oder anderen Benutzerinteraktionen mit einem Steuerelement, z. B. eine Schaltfläche oder ein Listenfeld-Steuerelement in einem Dialogfeld generiert.

Die `Run` Memberfunktion der Klasse `CWinApp` ruft Nachrichten ab und verteilt sie an das entsprechende Fenster. Die meisten befehlsmeldungen werden an das Hauptrahmenfenster der Anwendung gesendet. Die `WindowProc` vordefiniert durch die Klasse Bibliothek ruft Nachrichten aus, und diese unterschiedlich, abhängig von der Kategorie der empfangenen Nachricht weiterleitet.

Betrachten Sie nun die empfangenden Teil des Prozesses.

Der erste Empfänger einer Nachricht muss ein Window-Objekt. Windows-Nachrichten werden in der Regel direkt vom, Window-Objekt behandelt. Command-Meldungen, stammen in der Regel in der Anwendung Hauptrahmenfenster, auf die Befehlsziel Kette, die in beschriebenen weitergeleitet [Befehlsrouting](../mfc/command-routing.md).

Jedes Objekt, das Empfangen von Nachrichten oder Befehle verfügt über eine eigene Nachricht diese Paare eine Nachricht oder einen Befehl mit dem Namen der der Handler zugeordnet.

Wenn ein Befehlsziel Objekt eine Nachricht oder einen Befehl empfängt, werden seine meldungszuordnung, nach einer Übereinstimmung gesucht. Wenn sie einen Handler für die Nachricht findet, wird den Handler. Weitere Informationen dazu, wie meldungszuordnungen durchsucht werden, finden Sie unter [wie das Framework sucht Meldungszuordnungen](../mfc/how-the-framework-searches-message-maps.md). Finden Sie in der Abbildung erneut [Befehle im Framework](../mfc/user-interface-objects-and-command-ids.md).

## <a name="see-also"></a>Siehe auch

[So ruft das Framework einen Handler auf](../mfc/how-the-framework-calls-a-handler.md)
