---
title: 'Windows Sockets: Socketbenachrichtigungen'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
ms.openlocfilehash: c08305b8aeeca00eaf41e4f1c24b51a46a8c4254
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289909"
---
# <a name="windows-sockets-socket-notifications"></a>Windows Sockets: Socketbenachrichtigungen

Dieser Artikel beschreibt die Benachrichtigungsfunktionen in den Socketklassen. Diese Memberfunktionen sind Rückruffunktionen, die vom Framework aufgerufen, um Ihre Socketobjekt von wichtigen Ereignissen zu benachrichtigen. Die Benachrichtigungsfunktionen sind:

- [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): Benachrichtigt diesen Socket, dass Daten in den Puffer abzurufen, indem er [Receive](../mfc/reference/casyncsocket-class.md#receive).

- [OnSend](../mfc/reference/casyncsocket-class.md#onsend): Benachrichtigt diesen Socket, sie können jetzt Daten durch den Aufruf senden [senden](../mfc/reference/casyncsocket-class.md#send).

- [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): Benachrichtigt diesen empfangsbereiten Sockets, den es ausstehende verbindungsanforderungen, durch den Aufruf annehmen kann [Accept](../mfc/reference/casyncsocket-class.md#accept).

- [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): Benachrichtigt diesen eine Verbindung herstellen Socket, der der Verbindungsversuch abgeschlossen: möglicherweise erfolgreich, oder vielleicht Fehler.

- [OnClose](../mfc/reference/casyncsocket-class.md#onclose): Benachrichtigt diesen Socket, die der Socket aus dem eine Verbindung ist geschlossen wurde.

    > [!NOTE]
    >  Eine weitere Benachrichtigung-Funktion ist [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata). Diese Benachrichtigung weist dem Socket empfangen, dass der sendende Socket "Out-of-Band"-Daten gesendet hat. Out-of-Band-Daten sind logisch unabhängige Kanäle für jedes Paar an verbundene Streamsockets verknüpft ist. Der Out-of-Band-Kanal wird normalerweise verwendet, um "dringend" Daten zu senden. MFC unterstützt die Out-of-Band-Daten. Erfahrene Benutzer, die Arbeit mit Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md) müssen möglicherweise verwenden die Out-of-Band-Kanal, aber die Benutzer der Klasse [CSocket](../mfc/reference/csocket-class.md) wird davon abgeraten, aus deren Nutzung. Die einfachste Methode besteht darin einen zweiten Socket für die Übergabe dieser Daten zu erstellen. Weitere Informationen über Out-of-Band-Daten finden Sie unter der Windows Sockets-Spezifikation, die im Windows SDK verfügbar.

Bei der Ableitung von der Klasse `CAsyncSocket`, müssen Sie die Benachrichtigungsfunktionen für die Netzwerk-Veranstaltungen für Ihre Anwendung überschreiben. Wenn Sie eine Klasse aus der Klasse ableiten `CSocket`, sie haben die Wahl, ob die Benachrichtigungsfunktionen relevanten überschrieben. Sie können auch `CSocket` selbst in diesem Fall die Benachrichtigung Funktionen standardmäßig keine Aktion ausführt.

Diese Funktionen sind überschreibbare Rückruffunktionen. `CAsyncSocket` und `CSocket` Konvertieren von Nachrichten an die Benachrichtigungen, aber Sie müssen implementieren, wie die Benachrichtigung reagieren funktioniert, wenn Sie sie verwenden möchten. Die Benachrichtigungsfunktionen werden zum Zeitpunkt aufgerufen, die Ihre Socket benachrichtigt wird, ein Ereignis von Interesse sind, z. B. das Vorhandensein von Daten, die gelesen werden.

MFC ruft die Benachrichtigungsfunktionen zum können Sie zum Zeitpunkt des Sockets-Verhalten anpassen, die sie darüber benachrichtigt wird. Sie können z. B. Aufrufen `Receive` aus Ihrem `OnReceive` Benachrichtigungsfunktion, also auf wird benachrichtigt, dass die zu lesenden Daten vorhanden ist, rufen Sie `Receive` zum Lesen. Dieser Ansatz ist nicht erforderlich, aber es ist ein gültiges Szenario. Als Alternative können Ihre Benachrichtigungsfunktion zum Nachverfolgen des Verlaufs, Drucken **ABLAUFVERFOLGUNG** Nachrichten und So weiter.

Sie können diese Benachrichtigungen nutzen die Benachrichtigungsfunktionen in einer abgeleiteten Socketklasse überschreiben und eine Implementierung bereitstellen.

Während eines Vorgangs, z. B. empfangen oder Senden von Daten eine `CSocket` Objekt wird synchron. Während der den Zustand "synchron" sind keine Benachrichtigungen zur anderen Sockets in der Warteschlange, während des aktuellen Sockets für die Benachrichtigung auf die sie möchte. (Z. B. während einer `Receive` Aufruf wird der Socket möchte eine Benachrichtigung zum Lesen.) Sobald der Socket der synchrone Vorgang abgeschlossen und wieder asynchrone ist, können andere Sockets Empfang der Benachrichtigungen in der Warteschlange beginnen.

> [!NOTE]
>  In `CSocket`, `OnConnect` Benachrichtigungsfunktion wird nie aufgerufen. Für Verbindungen, rufen Sie `Connect`, die dann zurück, wenn die Verbindung (erfolgreich oder Fehler) erstellt wird. Behandlung von Benachrichtigungen von Verbindung ist ein Implementierungsdetail MFC.

Weitere Informationen zu den einzelnen Notification-Funktionen finden Sie unter der Funktion unter Klasse `CAsyncSocket` in die *MFC-Referenz*. Quellcode und Informationen über MFC-Beispiele finden Sie [MFC-Beispiele](../visual-cpp-samples.md).

Weitere Informationen finden Sie unter:

- [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Sockets: Ableiten aus Socketklassen](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Sockets: Blocking](../mfc/windows-sockets-blocking.md)

- [Windows Sockets: Die Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)

- [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
