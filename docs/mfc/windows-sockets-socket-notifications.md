---
title: 'Windows Sockets: Socket-Benachrichtigungen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6fd065d13d3c61b88cc24144cfc64368020d16
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953970"
---
# <a name="windows-sockets-socket-notifications"></a>Windows Sockets: Socketbenachrichtigungen
Dieser Artikel beschreibt die Benachrichtigungsfunktionen in den Socketklassen. Diese Memberfunktionen sind Rückruffunktionen, die vom Framework aufgerufen, um Ihre Socketobjekt von wichtigen Ereignissen zu benachrichtigen. Die Benachrichtigungsfunktionen sind:  
  
-   [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): benachrichtigt Sie diesem Socket, dass Daten in den Puffer zum Abrufen von durch den Aufruf [Receive](../mfc/reference/casyncsocket-class.md#receive).  
  
-   [OnSend](../mfc/reference/casyncsocket-class.md#onsend): benachrichtigt Sie diesem Socket, dass sie Daten durch den Aufruf jetzt senden kann [senden](../mfc/reference/casyncsocket-class.md#send).  
  
-   [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): Diese empfangsbereiten Sockets, die er durch Aufrufen von ausstehenden verbindungsanforderungen annehmen kann benachrichtigt [Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
-   [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): teilt diese verbindende Socket, der der Verbindungsversuch abgeschlossen: vielleicht erfolgreich oder möglicherweise fehlerhaft.  
  
-   [OnClose](../mfc/reference/casyncsocket-class.md#onclose): benachrichtigt diesem Socket, die der Socket ist mit geschlossen wurde.  
  
    > [!NOTE]
    >  Eine weiterer Benachrichtigungsszenarien-Funktion ist [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata). Diese Benachrichtigung teilt dem empfangenden Socket, dass der sendende Socket "Out-of-Band"-Daten gesendet hat. Out-of-Band-Daten ist ein logisch unabhängig für jedes Paar an verbundene Streamsockets verknüpft sind. Der Out-of-Band-Kanal wird normalerweise verwendet, um "dringend" Daten zu senden. MFC unterstützt die Out-of-Band-Daten. Fortgeschrittene Benutzer arbeiten mit Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md) müssen möglicherweise verwenden die Out-of-Band-Kanal, sondern Benutzer der Klasse [CSocket](../mfc/reference/csocket-class.md) werden aus ihrer Verwendung abgeraten. Einfacher besteht darin, einen zweiten Socket für die Übergabe von Daten zu erstellen. Weitere Informationen über Out-of-Band-Daten finden Sie unter der Windows Sockets-Spezifikation, die im Windows SDK verfügbar.  
  
 Wenn Sie von der Klasse ableiten `CAsyncSocket`, müssen Sie für die Netzwerk-Veranstaltungen für Ihre Anwendung die Benachrichtigungsfunktionen überschreiben. Wenn Sie eine Klasse von der Klasse ableiten `CSocket`, sie haben die Wahl, ob die Benachrichtigungsfunktionen von Interesse sind, überschrieben. Sie können auch `CSocket` selbst in diesem Fall die Benachrichtigung Funktionen standardmäßig nichts zu machen.  
  
 Diese Funktionen sind überschreibbare Rückruffunktionen. `CAsyncSocket` und `CSocket` Konvertieren von Nachrichten an die Benachrichtigungen, aber Sie müssen implementieren, wie die Benachrichtigung reagieren funktioniert, wenn Sie sie verwenden möchten. Die Benachrichtigungsfunktionen heißen zum Zeitpunkt, zu die der Socket eines Ereignisses von Interesse sind, wie etwa der Anwesenheit von zu lesenden Daten benachrichtigt wird.  
  
 MFC Ruf die Benachrichtigungsfunktionen auf, können Sie die Socket-Verhalten zu dem Zeitpunkt anpassen, die sie darüber benachrichtigt wird. Sie können z. B. Aufrufen `Receive` aus Ihrer `OnReceive` Benachrichtigungsfunktion, d. h. auf wird darüber benachrichtigt, dass die zu lesenden Daten vorhanden ist, rufen Sie `Receive` lesen. Dieser Ansatz ist nicht erforderlich, aber es ist ein gültiges Szenario. Als Alternative können Ihre Benachrichtigungsfunktion zum Nachverfolgen des Verlaufs, Drucken **ABLAUFVERFOLGUNG** Nachrichten und So weiter.  
  
 Sie können diese Benachrichtigungen nutzen die Benachrichtigungsfunktionen in einer abgeleiteten Socketklasse zu überschreiben und eine Implementierung bereitstellen.  
  
 Während eines Vorgangs, z. B. empfangen oder Senden von Daten eine `CSocket` Objekt wird synchron. Während der synchronen Zustand werden alle Benachrichtigungen, die für andere Sockets vorgesehen in Warteschlangen eingereiht, während der aktuellen Socket für die Benachrichtigung wartet werden. (Z. B. während einer `Receive` Aufruf der, der Socket möchte eine Benachrichtigung zum Lesen.) Um, sobald der Socket Staffelung synchron abgeschlossen und ist das asynchrone wieder, können anderen Sockets beginnen, die in der Warteschlange Benachrichtigungen empfangen.  
  
> [!NOTE]
>  In `CSocket`die `OnConnect` Benachrichtigungsfunktion wird nie aufgerufen. Rufen Sie für Verbindungen, `Connect`, die dann zurück, wenn die Verbindung (erfolgreich oder fehlerhaft) abgeschlossen ist. Behandlung von Verbindung Benachrichtigungen ist ein Implementierungsdetail MFC.  
  
 Weitere Informationen zu jeder Benachrichtigungsfunktion, finden Sie unter der Funktion unter Klasse `CAsyncSocket` in der *MFC-Referenz*. Quellcode und Informationen über MFC-Beispiele finden Sie unter [MFC-Beispiele](../visual-cpp-samples.md).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Ableiten von Socket-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows-Sockets: Blocking](../mfc/windows-sockets-blocking.md)  
  
-   [Windows-Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows-Sockets: Umwandeln von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

