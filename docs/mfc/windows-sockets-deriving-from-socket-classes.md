---
title: 'Windows Sockets: Ableiten von Socket-Classen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c562a8d6bf1c3f00f3812f6c25a4afd70276c64f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418956"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Sockets: Ableiten von Socket-Classen

Dieser Artikel beschreibt einige der Funktionen, die Sie durch Ableiten von eine eigene Klasse von einer der Socketklassen erzielen können.

Sie können Ihre eigenen Socketklassen ableiten, entweder [CAsyncSocket](../mfc/reference/casyncsocket-class.md) oder [CSocket](../mfc/reference/csocket-class.md) eigene Funktionen hinzufügen. Geben Sie diese Klassen vor allem eine Anzahl von virtuellen Memberfunktionen, die Sie überschreiben können. Zu diesen Funktionen zählen [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), und [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Sie können die Funktionen überschreiben, in Ihrer abgeleiteten Socketklasse, die Benachrichtigungen nutzen, die sie bei der Netzwerkereignisse auftreten. Das Framework ruft diese Benachrichtigung Rückruffunktionen, um Sie über wichtige Socket-Ereignisse, z. B. den Empfang von Daten zu benachrichtigen, dass Sie, Lesen beginnen. Weitere Informationen zu Notification-Funktionen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md).

Darüber hinaus Klasse `CSocket` liefert die [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) Member-Funktion (eine erweiterte überschreibbare). MFC ruft diese Funktion während der Socket Windows-basierten Meldungen weiterleitet. Sie können außer Kraft setzen `OnMessagePending` suchen Sie nach bestimmten Nachrichten von Windows und auf diese reagieren.

Die Standardversion von `OnMessagePending` in Klasse bereitgestellten `CSocket` untersucht die Nachrichtenwarteschlange für WM_PAINT-Meldungen beim Warten auf eines blockierenden Aufrufs abgeschlossen. Es sendet Paint-Meldungen zur Verbesserung der Anzeigequalität. Abgesehen von sinnvolle Weise veranschaulicht dies eine Möglichkeit, die Sie die Funktion außer Kraft setzen können sich selbst. Wenn Sie beispielsweise in Betracht `OnMessagePending` für die nachfolgend aufgeführte Aufgabe. Nehmen wir an, dass Sie ein nicht modales Dialogfeld anzeigen, beim Warten auf den Abschluss einer Netzwerk-Transaktions. Das Dialogfeld enthält eine Schaltfläche "Abbrechen", mit denen der Benutzer blockierende Transaktionen abgebrochen wird, die zu lange dauern. Ihre `OnMessagePending` außer Kraft setzen kann Meldungen, die im Zusammenhang mit diesem nicht modalen Dialogfeld senden.

In Ihrer `OnMessagePending` überschrieben wird, zurückgeben **"true"** bzw. die Rückgabe von einem Aufruf der Basisklasse-Version des `OnMessagePending`. Rufen Sie die Basisklassenversion, wenn er führt die Arbeit, die für Sie interessant.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Blocking](../mfc/windows-sockets-blocking.md)

- [Windows-Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)

- [Windows-Sockets: Umwandeln von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

