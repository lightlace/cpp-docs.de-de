---
title: 'Windows Sockets: Verwenden von Sockets mit Archiven'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
ms.openlocfilehash: 64c5c058404b977254ca54d5595193654b3f4479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615386"
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Windows Sockets: Verwenden von Sockets mit Archiven

Dieser Artikel beschreibt die [CSocket Programmiermodell](#_core_the_csocket_programming_model). Klasse [CSocket](../mfc/reference/csocket-class.md) -Socket-Unterstützung auf eine höhere Abstraktionsebene bereitstellt, als Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md). `CSocket` verwendet eine Version des Protokolls der MFC-Serialisierung zum Übergeben von Daten in und aus der ein Socketobjekt über ein MFC- [CArchive](../mfc/reference/carchive-class.md) Objekt. `CSocket` enthält (beim Verwalten von Verarbeitung im Hintergrund von Windows-Nachrichten) blockiert, und bietet Zugriff auf `CArchive`, viele Aspekte der Kommunikation, die Sie mit der raw-API oder Klasse selbst durchzuführen hätten verwaltet `CAsyncSocket`.

> [!TIP]
>  Klasse können `CSocket` sich als praktischer Version `CAsyncSocket`, aber das einfachste Modell für die Programmierung ist die Verwendung `CSocket` mit einer `CArchive` Objekt.

Weitere Informationen dazu, wie die Implementierung von Sockets mit Archiven funktioniert, finden Sie unter [Windows Sockets: wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md). Beispielcode, finden Sie unter [Windows Sockets: Reihenfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md) und [Windows Sockets: Beispiel für Sockets mithilfe von Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md). Informationen über einige der Funktionen erhalten Sie durch Ihre eigenen Klassen aus den Socketklassen ableiten, finden Sie unter [Windows Sockets: Ableiten von Socket-Classen](../mfc/windows-sockets-deriving-from-socket-classes.md).

> [!NOTE]
>  Wenn Sie eine MFC-Clientprogramm zur Kommunikation mit Servern mit eingerichteten (MFC-Fremd) schreiben, werden C++-Objekte über das Archiv nicht gesendet werden. Wenn der Server eine MFC-Anwendung, die die Arten von Objekten zu verstehen, die Sie senden möchten ist, ist es nicht möglich zu empfangen und Deserialisieren Ihrer Objekte. Verwandtes Material zu diesem Thema für die Kommunikation mit nicht-MFC-Anwendungen, auch finden Sie im Artikel [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).

##  <a name="_core_the_csocket_programming_model"></a> Das Programmiermodell CSocket

Mit einem `CSocket` Objekt umfasst das Erstellen und Zuordnen von mehreren MFC-Klassenobjekten. Jeder Schritt stammt in der folgenden allgemeinen Verfahren sowohl für den Serversocket als auch für den Clientsocket, mit Ausnahme von Schritt 3, in dem jeder Sockettyp eine andere Aktion erfordert.

> [!TIP]
>  Zur Laufzeit wird die Server-Anwendung in der Regel zunächst bereit, und "überwachen", wenn die Clientanwendung eine Verbindung anfordert. Wenn der Server nicht bereit ist, wenn der Client versucht, eine Verbindung herstellen, müssen Sie in der Regel die benutzeranwendung, versuchen Sie es später noch mal.

#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Zum Einrichten der Kommunikation zwischen einem Serversocket und einem Clientsocket

1. Erstellen einer [CSocket](../mfc/reference/csocket-class.md) Objekt.

1. Verwenden Sie das Objekt zum Erstellen der zugrunde liegende **SOCKET** behandeln.

   Für eine `CSocket` Client-Objekt, sollten Sie die Standardparameter, normalerweise verwenden [erstellen](../mfc/reference/casyncsocket-class.md#create), es sei denn, Sie über einen Datagrammsocket benötigen. Für eine `CSocket` -Serverobjekt, geben Sie einen Port in der `Create` aufrufen.

    > [!NOTE]
    >  `CArchive` funktioniert nicht mit Datagrammsockets. Wenn Sie verwenden möchten `CSocket` für einen Datagrammsocket müssen Sie die Klasse verwenden, wie Sie mit `CAsyncSocket`, d. h. ohne Archiv. Da Datagramme unzuverlässig sind (nicht garantiert werden, auf das eingehen und wiederholt werden ungeordnet), sie sind nicht kompatibel mit der Serialisierung durch ein Archiv. Sie erwarten, dass ein Serialisierungsvorgang zuverlässig und in Reihenfolge ausführen. Wenn Sie versuchen, `CSocket` mit einem `CArchive` Objekt für ein Datagramm, MFC-Assertion ein Fehler auftritt.

1. Wenn der Socket ein Client ist, rufen Sie [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect) zur Verbindung mit eines Serversockets des Socket-Objekts.

     - oder - 

   Wenn der Socket auf einem Server ist, rufen Sie [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen) beginnen Lauschen von Verbindungsversuchen von einem Client. Eingeht, eine verbindungsanforderung, akzeptieren Sie sie durch Aufrufen von [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).

    > [!NOTE]
    >  Die `Accept` Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Müssen Sie dieses Objekt erstellen, vor dem Aufruf `Accept`. Wenn dieser Socketobjekt den Geltungsbereich verlässt, wird die Verbindung. Rufen Sie keine `Create` für dieses neuen Socketobjekt.

1. Erstellen Sie eine [CSocketFile](../mfc/reference/csocketfile-class.md) Objekt zuordnen der `CSocket` Objekt mit.

1. Erstellen Sie eine [CArchive](../mfc/reference/carchive-class.md) -Objekt für das Laden (empfangen) oder das Speichern von Daten (senden). Das Archiv zugeordnet ist die `CSocketFile` Objekt.

   Beachten Sie, dass `CArchive` funktioniert nicht mit Datagrammsockets.

1. Verwenden der `CArchive` Objekt, das Übergeben von Daten zwischen dem Client und Server-Sockets.

   Beachten Sie, dass eine bestimmte `CArchive` Objekt verschiebt Daten nur in eine Richtung: entweder zum Laden (empfangen) oder für das Speichern von (senden). In einigen Fällen verwenden Sie zwei `CArchive` Objekte: eine für das Senden von Daten, die andere für den Empfang von Bestätigungen.

   Nach dem Akzeptieren einer Verbindung und Einrichten des Archivs, können Sie Aufgaben wie das Überprüfen von Kennwörtern ausführen.

1. Zerstören Sie das Archiv, Socketdatei und Socketobjekte.

    > [!NOTE]
    >  Klasse `CArchive` liefert die `IsBufferEmpty` Memberfunktion, die speziell zur Verwendung mit der Klasse `CSocket`. Wenn der Puffer mehrere Datennachrichten enthält, müssen Sie z. B. Schleife, bis alle werden gelesen, und der Puffer wird gelöscht. Die nächste Benachrichtigung, dass Daten empfangen werden kann, andernfalls auf unbestimmte Zeit verschoben werden. Verwendung `IsBufferEmpty` um sicherzustellen, dass Sie alle Daten abzurufen.

Der Artikel [Windows Sockets: Reihenfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md) beide Seiten dieses Prozesses mit Beispielcode veranschaulicht.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket::Create](../mfc/reference/csocket-class.md#create)

