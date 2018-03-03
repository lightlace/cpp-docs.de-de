---
title: 'Windows Sockets: Ableiten von Socket-Classen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63f8b8f735b62c1cbfedd50320bf65cec5905632
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Sockets: Ableiten von Socket-Classen
Dieser Artikel beschreibt einige der Funktionen, die Sie erhalten durch eine eigene Klasse von einer der Socketklassen ableiten.  
  
 Sie können entweder eine eigene Socketklassen ableiten [CAsyncSocket](../mfc/reference/casyncsocket-class.md) oder [CSocket](../mfc/reference/csocket-class.md) Ihre eigenen Funktionen hinzufügen. Diese Klassen geben insbesondere eine Anzahl von virtuellen Memberfunktionen, die Sie überschreiben können. Zu diesen Funktionen zählen [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect), und [OnClose](../mfc/reference/casyncsocket-class.md#onclose). Sie können die Funktionen überschreiben, in die abgeleitete Socketklasse, um Benachrichtigungen nutzen, die sie bereitstellen, wenn Ereignisse auftreten. Das Framework ruft diese Benachrichtigung Fehlerrückruf-Funktionen, um wichtige Socket-Ereignisse, wie den Empfang der Daten benachrichtigt, dass Sie, Lesen beginnen. Weitere Informationen zu Benachrichtigungsfunktionen, finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md).  
  
 Darüber hinaus-Klasse `CSocket` liefert die [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) Memberfunktion (eine erweiterte überschreibbaren). MFC ruft diese Funktion auf, während der Socket Windows-basierten Meldungen weiterleitet. Sie können außer Kraft setzen `OnMessagePending` , die von Windows für bestimmte Nachrichten suchen, und reagieren Sie darauf.  
  
 Die Standardversion von `OnMessagePending` in Klasse bereitgestellten `CSocket` untersucht die Nachrichtenwarteschlange für `WM_PAINT` Nachrichten beim Warten auf eines blockierenden Aufrufs abgeschlossen. Er sendet Paint-Meldungen, um die Anzeige zu verbessern. Abgesehen von etwas Sinnvolles Weise veranschaulicht dies eine Möglichkeit, die Sie die Funktion überschreibt möglicherweise selbst. Erwägen Sie ein weiteres Beispiel `OnMessagePending` für die nachfolgend aufgeführte Aufgabe. Angenommen Sie, Sie ein nicht modales Dialogfeld anzeigen, während des Wartens auf den Abschluss einer Netzwerk-Transaktions. Das Dialogfeld enthält eine Schaltfläche "Abbrechen", mit denen Benutzer blockierende Transaktionen "Abbrechen", die zu lange dauert. Ihre `OnMessagePending` Außerkraftsetzung möglicherweise Fehlermeldungen im Zusammenhang mit diesem nicht modalen Dialogfeld Datapump.  
  
 In Ihrem `OnMessagePending` außer Kraft setzen, zurückgeben **"true"** oder die Rückgabe von einem Aufruf der Basisklassenversion von `OnMessagePending`. Rufen Sie die Basisklassenversion, wenn es Aufgaben ausführt, die Sie trotzdem ausgeführt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Blocking](../mfc/windows-sockets-blocking.md)  
  
-   [Windows-Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows-Sockets: Umwandeln von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

