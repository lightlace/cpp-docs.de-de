---
title: 'Windows Sockets: Verwenden von Sockets mit Archiven | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7ad4e5b94403582f9073e4d3bd3542f8aa75d08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Sockets: Verwenden von Sockets mit Archiven
Dieser Artikel beschreibt die [CSocket-Programmiermodell](#_core_the_csocket_programming_model). Klasse [CSocket](../mfc/reference/csocket-class.md) -Socket-Unterstützung auf eine höhere Abstraktionsebene bereitstellt, als Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md). `CSocket` verwendet eine Version des Protokolls die MFC-Serialisierung zum Übergeben von Daten in und aus einem Socketobjekt, über ein MFC- [CArchive](../mfc/reference/carchive-class.md) Objekt. `CSocket` enthält (beim Verwalten von hintergrundverarbeitung von Windows-Nachrichten) blockieren und ermöglicht den Zugriff auf `CArchive`, die zahlreiche Aspekte der Kommunikation, die Sie selbst unter Verwendung der raw-API oder Klasse verwaltet `CAsyncSocket`.  
  
> [!TIP]
>  Können Sie Klasse `CSocket` selbst als bequemer Version `CAsyncSocket`, aber das einfachste Programmiermodell ist die Verwendung `CSocket` mit einer `CArchive` Objekt.  
  
 Weitere Informationen zur Funktionsweise der Implementierung von Sockets mit Archiven finden Sie unter [Windows Sockets: wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md). Beispielcode hierzu finden Sie unter [Windows Sockets: Reihenfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md) und [Windows Sockets: Beispiel für Sockets mithilfe von Archiven](../mfc/windows-sockets-example-of-sockets-using-archives.md). Informationen über einige der Funktionen erhalten Sie durch Ihren eigenen Klassen von Socketklassen ableiten, finden Sie unter [Windows Sockets: Ableiten von Socket-Classen](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
> [!NOTE]
>  Wenn Sie ein MFC-Clientprogramm zur Kommunikation mit Servern hergestellt (MFC-Fremd) schreiben, senden Sie C++-Objekte über das Archiv nicht. Wenn der Server eine MFC-Anwendung, die die Arten von Objekten zu verstehen, die Sie senden möchten ist, ist dies nicht empfangen und deserialisiert Objekte. Verwandtes Material für den Betreff der Kommunikation mit MFC-fremden Anwendungen auch finden Sie im Artikel [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).  
  
##  <a name="_core_the_csocket_programming_model"></a> CSocket-Programmiermodell  
 Mit einem `CSocket` Objekt umfasst das Erstellen und mehrere MFC-Klassenobjekten miteinander verknüpfen. Im allgemeinen Verfahren ist jeder Schritt ausgeführt, durch den Serversocket und den Clientsocket, mit Ausnahme von Schritt 3, in dem jeder Sockettyp eine andere Aktion erfordert.  
  
> [!TIP]
>  Zur Laufzeit startet die Anwendung für die in der Regel zunächst bereit und "Überwachung", wenn die Clientanwendung eine Verbindung anfordert. Wenn der Server nicht bereit ist, wenn der Client versucht, eine Verbindung herzustellen, müssen Sie in der Regel die benutzeranwendung, versuchen es später erneut.  
  
#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Zum Einrichten der Kommunikation zwischen einem Serversocket und eines Clientsockets  
  
1.  Erstellen einer [CSocket](../mfc/reference/csocket-class.md) Objekt.  
  
2.  Verwenden Sie das Objekt zum Erstellen des zugrunde liegenden **SOCKET** behandeln.  
  
     Für eine `CSocket` Client-Objekt, sollten Sie normalerweise die Standardparameter für verwenden [erstellen](../mfc/reference/casyncsocket-class.md#create), es sei denn, Sie einen Datagrammsocket benötigen. Für eine `CSocket` -Serverobjekt, geben Sie einen Port in der **erstellen** aufrufen.  
  
    > [!NOTE]
    >  `CArchive` funktioniert nicht mit Datagrammsockets. Wenn Sie verwenden möchten `CSocket` für einen Datagrammsocket müssen Sie die Klasse verwenden, wie `CAsyncSocket`, d. h. ohne ein Archiv. Da Datagramme unzuverlässig sind (nicht unbedingt eingehen und wiederholt werden und ungeordnet), sie sind nicht kompatibel mit der Serialisierung über ein Archiv. Sie erwarten, dass ein Serialisierungsvorgang zuverlässig und in Reihenfolge abgeschlossen. Wenn Sie versuchen, `CSocket` mit einem `CArchive` -Objekt für ein Datagramm eine MFC-Assertion fehlschlägt.  
  
3.  Wenn der Socket ein Client ist, rufen Sie [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect) zur Verbindung mit einem Serversocket des Socket-Objekts.  
  
     - oder -   
  
     Wenn der Socket ein Server ist, rufen Sie [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen) beginnen Verbindungsversuche von einem Client überwacht. Nach dem Empfang einer verbindungsanforderung, akzeptieren Sie sie durch Aufrufen von [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
    > [!NOTE]
    >  Die **Accept** Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Sie müssen dieses Objekt erstellen, vor dem Aufruf **Accept**. Wenn dieses Socketobjekt den Gültigkeitsbereich verlässt, schließt die Verbindung. Rufen Sie nicht **erstellen** für dieses neue Socketobjekt.  
  
4.  Erstellen einer [CSocketFile](../mfc/reference/csocketfile-class.md) Objekt zuordnen der `CSocket` Objekt mit.  
  
5.  Erstellen einer [CArchive](../mfc/reference/carchive-class.md) Objekte für das Laden (empfangen) oder Speichern von Daten (senden). Das Archiv zugeordnet ist die `CSocketFile` Objekt.  
  
     Beachten Sie, dass `CArchive` funktioniert nicht bei Datagrammsockets.  
  
6.  Verwenden der `CArchive` Objekt Daten zwischen dem Client und Server Sockets übergeben.  
  
     Beachten Sie, dass eine bestimmte `CArchive` Objekt verschiebt Daten nur in eine Richtung: entweder für das Laden (empfangen) oder speichern (senden). In einigen Fällen verwenden Sie zwei `CArchive` Objekte: eines für das Senden von Daten, die andere für den Empfang von Bestätigungen.  
  
     Nach dem Akzeptieren einer Verbindung und das Archiv einrichten, können Sie Aufgaben wie das Überprüfen von Kennwörtern ausführen.  
  
7.  Das Archiv, Socketdatei und Socketobjekte zu zerstören.  
  
    > [!NOTE]
    >  Klasse `CArchive` liefert die `IsBufferEmpty` Memberfunktion speziell zur Verwendung mit der Klasse `CSocket`. Wenn der Puffer mehrere Datennachrichten enthält, müssen Sie z. B. Schleife, bis alle gelesen werden und der Puffer geleert. Die nächste Benachrichtigung, dass Daten empfangen werden kann, andernfalls unbegrenzt verzögert werden. Verwendung `IsBufferEmpty` sichergestellt, dass Sie alle Daten abgerufen werden.  
  
 Der Artikel [Windows Sockets: Reihenfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md) beide Seiten dieses Prozesses mit Beispielcode veranschaulicht.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../mfc/reference/csocket-class.md#create)

