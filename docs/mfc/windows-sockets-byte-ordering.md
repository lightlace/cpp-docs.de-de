---
title: 'Windows Sockets: Die Bytereihenfolge'
ms.date: 11/04/2016
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
ms.openlocfilehash: ca572ad32a9a46756cacf0221d80b2953b710723
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217570"
---
# <a name="windows-sockets-byte-ordering"></a>Windows Sockets: Die Bytereihenfolge

In diesem Artikel und zwei begleitenden Artikel erläutern mehrere Probleme bei der Windows Sockets-Programmierung. Dieser Artikel behandelt die Bytereihenfolge. In den Artikeln werden weitere Aspekte behandelt: [Windows-Sockets: Blockierende](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).

Wenn Sie verwenden, oder leiten Sie von der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Sie müssen diese Probleme selbst zu verwalten. Wenn Sie verwenden, oder leiten Sie von der Klasse [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.

## <a name="byte-ordering"></a>Die Bytereihenfolge

Abweichender Architektur wird manchmal Daten, die mit verschiedenen Byte Order gespeichert. Intel-basierte Computer z. B. speichern Daten in der umgekehrten Reihenfolge (Motorola)-Macintosh-Computer. Bytereihenfolge von Intel, dem Namen "little-Endian-," ist auch das Gegenteil von die standardmäßige "big-Endian-Reihenfolge. In der folgende Tabelle werden diese Begriffe erläutert.

### <a name="big--and-little-endian-byte-ordering"></a>Groß - und Little-Endian-Bytereihenfolge

|Die Bytereihenfolge|Bedeutung|
|-------------------|-------------|
|Big-Endian|Das höchstwertige Byte wird am linken Ende eines Worts.|
|Little-Endian-|Das höchstwertige Byte wird am rechten Ende ein Wort.|

In der Regel, Sie müssen keine Bytereihenfolge-Konvertierung für Daten kümmern, die Sie senden und über das Netzwerk empfangen, aber es gibt Situationen, in denen Sie Bytereihenfolge zu konvertieren.

## <a name="when-you-must-convert-byte-orders"></a>Wenn müssen Sie Bytereihenfolge konvertieren.

In diesem Fall müssen Sie eine Byte-Order in den folgenden Situationen zu konvertieren:

- Übergeben Sie Informationen, die über das Netzwerk, im Gegensatz zu den Daten interpretiert werden soll, die Sie an einem anderen Computer senden muss. Sie können z. B. übergeben Ports und Adressen, die im Netzwerk kennen müssen.

- Die Server-Anwendung, mit der Sie kommunizieren, ist keiner MFC-Anwendung (und Sie haben keinen Quellcode dafür). Dies ruft Bytereihenfolge konvertiert, wenn die beiden Computer nicht die gleichen Bytereihenfolge freigeben.

## <a name="when-you-do-not-have-to-convert-byte-orders"></a>Wenn Sie keine Bytereihenfolge konvertieren

Sie können die Arbeit der Konvertierung Bytereihenfolgen in den folgenden Situationen vermeiden:

- Die Computer auf beiden Seiten können nicht zum Austauschen von Bytes stimmen zu, und verwenden Sie beide Computer die gleiche Bytereihenfolge.

- Der Server, mit dem Sie kommunizieren, ist eine MFC-Anwendung.

- Sie haben die Quellcode für den Server, die, dem Sie mit dem Sie kommunizieren, sodass Sie explizit erkennen können, ob Sie Bytereihenfolgen oder nicht konvertieren müssen.

- Sie können den Server mit MFC portieren. Dies ist recht einfach, und das Ergebnis ist in der Regel kleiner, schneller Code.

Arbeiten mit [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Sie müssen alle erforderlichen Bytereihenfolge-Konvertierungen selbst verwalten. Windows Sockets standardisiert das "big-Endian-Bytereihenfolge-Modell und bietet Funktionen zum Konvertieren zwischen diesen Auftrag und andere. [CArchive](../mfc/reference/carchive-class.md)jedoch die Verwendung mit [CSocket](../mfc/reference/csocket-class.md), verwendet den umgekehrten Reihenfolge der ("little-Endian"), aber `CArchive` die Details der Bytereihenfolge-Konvertierungen für Sie übernimmt. Mithilfe dieser standard Sortierung in Ihren Anwendungen oder mithilfe von Windows Sockets-Byte-Order-Konvertierungsfunktionen können Sie Ihren Code besser portierbar vornehmen.

Das ideale Argument für die Verwendung von MFC-Sockets ist, wenn Sie beide Enden der Kommunikation schreiben und dabei eine MFC-Bibliothek an beiden Enden verwenden. Wenn Sie eine Anwendung schreiben, die mit MFC-fremden Anwendungen, z. B. von einem FTP-Server kommuniziert wird, müssen Sie wahrscheinlich verwalten Byteaustausch selbst, bevor Sie Daten in das Archivobjekt übergeben, verwenden Sie die Windows Sockets-Konvertierungsroutinen **Ntohs**, **Ntohl**, **Htons**, und **Htonl**. Ein Beispiel für diese Funktionen bei der Kommunikation mit einer nicht-MFC-Anwendung verwendet, die später in diesem Artikel wird angezeigt.

> [!NOTE]
>  Wenn das andere Ende der Kommunikation keiner MFC-Anwendung ist, außerdem müssen Sie vermeiden streaming von C++-Objekte, die von abgeleiteten `CObject` in Ihr Archiv, da der Empfänger nicht mit ihnen umgehen kann. Siehe den Hinweis im [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md).

Weitere Informationen zu Byte Order finden Sie unter der Windows Sockets-Spezifikation, die im Windows SDK verfügbar.

## <a name="a-byte-order-conversion-example"></a>Ein Beispiel für die Bytereihenfolge-Konvertierung

Das folgende Beispiel zeigt eine Serialisierungsfunktion für eine `CSocket` -Objekt, ein Archiv verwendet. Es zeigt auch die Bytereihenfolge-Konvertierungsfunktionen in der Windows Sockets-API verwenden.

Dieses Beispiel zeigt ein Szenario, in dem Sie einen Client schreiben, der mit einer MFC-fremde Server-Anwendung kommuniziert für die Sie keinen Zugriff auf den Quellcode haben. In diesem Szenario müssen Sie davon ausgehen, dass der MFC-fremde Server standard-Netzwerk-Bytereihenfolge verwendet. Im Gegensatz dazu die MFC-Clientanwendung verwendet einen `CArchive` Objekt mit einer `CSocket` Objekt und `CArchive` "little-Endian-Bytereihenfolge, das Gegenteil des standard-Netzwerks verwendet.

Nehmen wir an, dass der MFC-fremde Server, mit dem Sie kommunizieren möchten, ein gängiges Protokoll für ein Meldungspaket wie die folgende verfügt:

[!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]

MFC-ausgedrückt würde dies wie folgt ausgedrückt werden:

[!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]

In C++ ist eine **Struktur** ist im Grunde dasselbe wie eine Klasse. Die `Message` Struktur besitzen Member-Funktionen, wie z. B. die `Serialize` Memberfunktion oben deklariert. Die `Serialize` Member-Funktion wie folgt aussehen:

[!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]

Dieses Beispiel ruft für die Bytereihenfolge-Konvertierungen von Daten, da eine klare Nichtübereinstimmung zwischen der Bytereihenfolge der MFC-fremde Server-Anwendung an einem Ende und der `CArchive` in Ihrer MFC-Clientanwendung auf der anderen Seite verwendet. Das Beispiel veranschaulicht einige der Bytereihenfolge-Konvertierungsfunktionen, die Windows-Sockets bereitstellt. Die folgende Tabelle beschreibt diese Funktionen.

### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows Sockets-Byte-Order-Konvertierungsfunktionen

|Funktion|Zweck|
|--------------|-------------|
|**ntohs**|Konvertiert eine 16-Bit-Menge von Netzwerk-Bytereihenfolge in die Host-Bytereihenfolge (von big-Endian in little-Endian).|
|**ntohl**|Konvertieren Sie eine 32-Bit-Menge von Netzwerk-Bytereihenfolge in die Host-Bytereihenfolge (von big-Endian in little-Endian) ein.|
|**Htons**|Konvertiert eine 16-Bit-Menge von Host-Bytereihenfolge in die Netzwerk-Bytereihenfolge (little-Endian-, big-Endian).|
|**Htonl**|Konvertieren Sie eine 32-Bit-Menge von Host-Bytereihenfolge in die Netzwerk-Bytereihenfolge (little-Endian-, big-Endian-) ein.|

Ein weiterer Aspekt, der in diesem Beispiel ist, wenn der Socket-Anwendung am anderen Ende der Kommunikation eine MFC-fremde Anwendung ist, Sie vermeiden müssen, etwa wie folgt ausführen:

`ar << pMsg;`

wo `pMsg` ist ein Zeiger auf ein C++-Objekt, das von der Klasse abgeleitet `CObject`. Hiermit wird, dass zusätzliche MFC-Informationen, die Objekte und dem Server zugeordnet, nicht versteht, als wäre, wäre es eine MFC-Anwendung gesendet.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden der Klasse „CAsyncSocket“](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

- [Windows-Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
