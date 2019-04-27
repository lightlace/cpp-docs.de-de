---
title: 'Windows Sockets: Hintergrund'
ms.date: 11/04/2016
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
ms.openlocfilehash: 6ab866609d0b75aaf9d06a01c204433d80e7e3d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217877"
---
# <a name="windows-sockets-background"></a>Windows Sockets: Hintergrund

In diesem Artikel werden die Eigenschaften und der Zweck von Windows Sockets erläutert. Der Artikel enthalt auch folgende Informationen:

- [Definition des Begriffs "Socket"](#_core_definition_of_a_socket).

- [Beschreibt den Datentyp der SOCKET-Handle](#_core_the_socket_data_type).

- [Beschreibung von Verwendungszwecken für Sockets](#_core_uses_for_sockets).

In der Spezifikation für Windows Sockets wird eine mit einem Binärformat kompatible Netzwerk-Programmierungsschnittstelle für Microsoft Windows definiert. Windows Sockets basieren auf der UNIX-Socketimplementierung in Berkeley Software Distribution (BSD, Release 4.3) der Universität von Kalifornien, Berkeley, USA. Die Spezifikation umfasst die Socketroutinen im BSD-Format und für Windows spezifische Erweiterungen. Wenn Sie Windows Sockets verwenden, kann die Anwendung über ein beliebiges Netzwerk kommunizieren, das der Windows Sockets-API entspricht. Auf Win32 sorgen Windows Sockets für Threadsicherheit.

Viele Netzwerksoftwareanbieter unterstützen Windows Sockets für Netzwerkprotokolle, wie Transmission Control Protocol/Internet Protocol (TCP/IP), Xerox Network System (XNS), Digital Equipment Corporations DECNet-Protokoll, Internet Packet Exchange/Sequenced Packed Exchange-Protokoll (IPX/SPX) von Novell Corporation und andere. Obwohl in der vorhandenen Windows Socket-Spezifikation die Socketabstraktion für TCP/IP definiert wird, kann jedes Netzwerkprotokoll mit Windows Sockets übereinstimmen, indem es eine eigene Version der DLL (Dynamic Link Library) bereitstellt, in der Windows Sockets implementiert sind. Kommerzielle Anwendungen, die mit Windows Sockets geschrieben werden, sind z. B. X Windows-Server, Terminalemulatoren und E-Mail-Systeme.

> [!NOTE]
>  Der Zweck von Windows Sockets ist, eine Abstraktion jenseits des zugrunde liegenden Netzwerks zu bieten, damit dieses Netzwerk nicht bekannt sein muss und die Anwendung auf einem beliebigen Netzwerk ausgeführt werden kann, das Sockets unterstützt. Daher werden in dieser Dokumentation keine Details zu Netzwerkprotokollen erläutert.

Die Microsoft Foundation Class-Bibliothek (MFC-Bibliothek) unterstützt Programmierung mit der Windows Sockets-API, indem sie zwei Klassen bereitstellt. Eine dieser Klassen, `CSocket`, bietet eine hohe Abstraktionsebene, wodurch die Programmierung der Netzwerkkommunikation vereinfacht wird.

Der Windows Sockets-Spezifikation Windows Sockets: Eine Schnittstelle zu öffnen, für die Network Computing unter Microsoft Windows, jetzt in Version 1.1, wurde als offener Netzwerkstandard von einer großen Gruppe von Einzelpersonen und Unternehmen in der TCP/IP-Community entwickelt und steht kostenlos zur Verfügung. Das Socket-Programmiermodell unterstützt derzeit eine „Kommunikationsdomäne“ und verwendet dabei die Internetprotokollsammlung. Die Spezifikation ist im Windows SDK verfügbar.

> [!TIP]
>  Da die Sockets die Internetprotokollsammlung verwenden, werden sie als bevorzugte Route für Anwendungen verwendet, die Internetkommunikation auf der „Datenautobahn“ unterstützen.

##  <a name="_core_definition_of_a_socket"></a> Definition eines Sockets

Ein Socket ist ein Kommunikationsendpunkt - ein Objekt, durch das eine Windows Socket-Anwendung Datenpakete über ein Netzwerk sendet oder empfängt. Ein Socket hat einen Typ, ist einem laufenden Prozess zugeordnet und einen Namen haben. Derzeit tauschen Sockets Daten im Allgemeinen nur mit anderen Sockets in derselben "Kommunikationsdomäne" aus, in der die Internetprotokollfamilie verwendet wird.

Beide Arten von Sockets sind bidirektional. Es handelt sich um Datenflüsse, die in beide Richtungen gleichzeitig übermittelt werden können (Vollduplex).

Zwei Sockettypen sind verfügbar:

- Streamsockets

   Streamsockets sorgen für einen Datenfluss ohne Datensatzbegrenzungen: ein Bytedatenstrom. Streams werden garantiert übermittelt, ordnungsgemäß sequenziert und sind nicht dupliziert.

- Datagrammsockets

   Datagrammsockets unterstützen einen Datenfluss nach Datensätzen, der nicht garantiert übermittelt wird und eventuell beim Senden nicht sequenziert wird oder dupliziert sein kann.

"Sequenziert" bedeutet, dass Pakete in der gesendeten Reihenfolge übermittelt werden. "Nicht dupliziert" bedeutet, dass Sie ein bestimmtes Paket nur einmal abrufen können.

> [!NOTE]
>  Bei einigen Netzwerkprotokollen, wie XNS, können Datenströme auf Datensätze als Datensatzstreams anstelle von Bytedatenströmen ausgerichtet sein. Bei dem allgemeineren Protokoll TCP/IP sind die Datenströme jedoch Bytedatenströme. Windows Sockets stellen eine Abstraktionsebene bereit, die unabhängig vom zugrunde liegenden Protokoll ist.

Informationen zu diesen Typen und welche Art von Socket in bestimmten Situationen verwenden, finden Sie unter [Windows Sockets: Stream Sockets](../mfc/windows-sockets-stream-sockets.md) und [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md).

##  <a name="_core_the_socket_data_type"></a> Der Datentyp SOCKET

Jedes MFC-Socketobjekt umfasst ein Handle für ein Windows Socket-Objekt. Der Datentyp dieses Handles **SOCKET**. Ein **SOCKET** Handle ist analog zu den `HWND` für ein Fenster. MFC-Socketklassen stellen Operationen für das enthaltene Handle bereit.

Die **SOCKET** -Datentyp ist ausführlich im Windows SDK. Siehe "Socket-Datentyp und Fehlerwerte" unter Windows Sockets.

##  <a name="_core_uses_for_sockets"></a> Verwendungszwecke für Sockets

Sockets sind in mindestens drei Kommunikationskontexten äußerst nützlich:

- Client/Server-Modelle

- Peer-zu-Peer-Szenarien, wie Messaging-Anwendungen

- Remoteprozeduraufrufe (RPC), bei denen die empfangende Anwendung eine Meldung als Funktionsaufruf interpretiert

> [!TIP]
>  Das ideale Argument für die Verwendung von MFC-Sockets ist, wenn Sie beide Enden der Kommunikation schreiben und dabei eine MFC-Bibliothek an beiden Enden verwenden. Weitere Informationen zu diesem Thema, wie Sie die Groß-/Kleinschreibung zu verwalten, wenn Sie eine Kommunikation mit nicht-MFC-Anwendungen sind finden Sie unter [Windows Sockets: Die Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).

Weitere Informationen finden Sie unter Windows Sockets-Spezifikation: **Ntohs**, **Ntohl**, **Htons**, **Htonl**. Informationen finden Sie auch in folgenden Themen:

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Beispiel für Sockets mithilfe von Archiven](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows-Sockets: Verwenden der Klasse „CAsyncSocket“](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
