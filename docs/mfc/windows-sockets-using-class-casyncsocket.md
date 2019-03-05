---
title: 'Windows Sockets: Verwenden der Klasse CAsyncSocket'
ms.date: 11/04/2016
f1_keywords:
- CAsyncSocket
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
ms.openlocfilehash: 51274791393d95517bd8de5ae7248dc634018037
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263105"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Sockets: Verwenden der Klasse CAsyncSocket

In diesem Artikel wird erläutert, wie Sie mit der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Denken Sie daran, dass diese Klasse der Windows Sockets-API auf einer sehr niedrigen Ebene kapselt. `CAsyncSocket` Dient zur Verwendung von Programmierern, die die Netzwerkkommunikation im Detail kennen, aber die Vorteile von Rückrufen für Benachrichtigungen über Netzwerkereignisse verwenden möchten. Auf dieser Annahme basieren, bietet dieser Artikel nur grundlegende Anweisungen. Möglicherweise sollten Sie verwenden `CAsyncSocket` Wenn Sie Windows-Sockets benutzerfreundlichkeit beim Umgang mit mehreren Netzwerkprotokollen in einer MFC-Anwendung aber nicht die Flexibilität zu verzichten möchten. Sie können darüber hinaus können Sie, dass Sie bessere Effizienz abrufen können, indem Sie programmieren, direkt konnte sich selbst als allgemeinere Klasse ein alternatives Modell verwenden `CSocket`.

`CAsyncSocket` finden Sie unter den *MFC-Referenz*. Visual C++ bietet auch die Windows-Sockets-Spezifikation, befindet sich im Windows SDK. Die Details werden Ihnen überlassen. Visual C++ stellt keine beispielanwendung `CAsyncSocket`.

Wenn Sie keine umfassenden Kenntnisse in die Netzwerkkommunikation sind und eine einfache Lösung, verwenden Sie die Klasse [CSocket](../mfc/reference/csocket-class.md) mit einem `CArchive` Objekt. Finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md) für Weitere Informationen.

Dieser Artikel behandelt Folgendes:

- Erstellen und Verwenden einer `CAsyncSocket` Objekt.

- [Ihre Zuständigkeiten mit CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).

##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Erstellen und verwenden ein CAsyncSocket-Objekt

#### <a name="to-use-casyncsocket"></a>Verwenden der CAsyncSocket

1. Erstellen einer [CAsyncSocket](../mfc/reference/casyncsocket-class.md) Objekt, und verwenden Sie das Objekt zum Erstellen der zugrunde liegende **SOCKET** behandeln.

   Ein Socket folgt MFC-Muster der Erstellung in zwei Schritten.

   Zum Beispiel:

   [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]

     - oder - 

   [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]

   Der erste Konstruktor, der oben genannten erstellt eine `CAsyncSocket` Objekt im Stapel. Der zweite Konstruktor erstellt ein `CAsyncSocket` auf dem Heap. Die erste [erstellen](../mfc/reference/casyncsocket-class.md#create) Aufruf oben die Standardparameter verwendet, um einen Streamsocket zu erstellen. Die zweite `Create` Aufruf erstellt einen Datagrammsocket mit einem angegebenen Port und Adresse. (Verwenden Sie entweder `Create` Version mit beiden Erstellungsmethoden.)

   Die Parameter für `Create` sind:

   - Eine "Port": eine kurze ganze Zahl.

         For a server socket, you must specify a port. For a client socket, you typically accept the default value for this parameter, which lets Windows Sockets select a port.

   - Ein Sockeltyp: **SOCK_STREAM** (Standard) oder **SOCK_DGRAM**.

   - Ein Socket "Address", z. B. "ftp.microsoft.com" oder "128.56.22.8".

         This is your Internet Protocol (IP) address on the network. You will probably always rely on the default value for this parameter.

   Die Begriffe "Port" und "Socketadresse" werden in erläutert [Windows Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md).

1. Wenn der Socket ein Client ist, das Socketobjekt mit einem Server verbinden socket mit [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect).

     - oder - 

   Wenn der Socket auf einen Server handelt, legen Sie den Socket auf (mit [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen)) für Connect versucht von einem Client. Eingeht, eine verbindungsanforderung, akzeptieren Sie ihn mit [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).

   Nach dem Akzeptieren einer Verbindungs können Sie Aufgaben wie das Überprüfen von Kennwörtern ausführen.

    > [!NOTE]
    >  Die `Accept` Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Müssen Sie dieses Objekt erstellen, vor dem Aufruf `Accept`. Wenn dieser Socketobjekt den Geltungsbereich verlässt, wird die Verbindung. Rufen Sie keine `Create` für dieses neuen Socketobjekt. Ein Beispiel finden Sie im Artikel [Windows Sockets: Reihenfolge der Operationen](../mfc/windows-sockets-sequence-of-operations.md).

1. Tragen Sie die Kommunikation mit anderen Sockets durch Aufrufen der `CAsyncSocket` objektelementfunktionen, die die Windows Sockets-API-Funktionen zu kapseln.

   Finden Sie unter der Windows Sockets-Spezifikation und die Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md) in die *MFC-Referenz*.

1. Zerstört die `CAsyncSocket` Objekt.

   Wenn Sie das Socketobjekt auf dem Stapel erstellt, wird sein Destruktor aufgerufen, wenn die Funktion mit den Gültigkeitsbereich verlässt. Wenn Sie das Socketobjekt auf dem Heap erstellt haben, die **neue** Operator an, Sie sind verantwortlich für die Verwendung der **löschen** Operator, um das Objekt zu zerstören.

   Der Destruktor ruft die [schließen](../mfc/reference/casyncsocket-class.md#close) Memberfunktion vor dem Zerstören des Objekts.

Ein Beispiel für diese Sequenz im Code (für die tatsächlich eine `CSocket` Objekt), finden Sie unter [Windows Sockets: Reihenfolge der Operationen](../mfc/windows-sockets-sequence-of-operations.md).

##  <a name="_core_your_responsibilities_with_casyncsocket"></a> Ihre Zuständigkeiten mit CAsyncSocket

Wenn Sie ein Objekt der Klasse erstellen [CAsyncSocket](../mfc/reference/casyncsocket-class.md), das-Objekt kapselt eine Windows **SOCKET** behandeln und stellt Vorgänge für dieses Handle. Bei Verwendung von `CAsyncSocket`, müssen Sie alle Probleme, die Sie möglicherweise stoßen, wenn die API direkt verwenden müssen. Zum Beispiel:

- Szenarien mit "Blockieren".

- Byte-Order-Unterschiede zwischen den sendenden und empfangenden Computer.

- Legen Sie konvertieren zwischen Unicode- und multibyte-Zeichensätze (MBCS)-Zeichenfolgen.

Definitionen dieser Begriffe und Weitere Informationen finden Sie [Windows Sockets: Blockierende](../mfc/windows-sockets-blocking.md), [Windows Sockets: Die Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md), [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).

Trotz dieser Probleme Klasse `CAsycnSocket` kann die richtige Wahl für Sie sein, wenn Ihre Anwendung erfordert, die alle Flexibilität und Kontrolle, die Sie erhalten. Wenn nicht der Fall, sollten Sie erwägen Klasse `CSocket` stattdessen. `CSocket` viele Details, die von Ihnen ausgeblendet: Pumpen Windows während der Aufrufe zum Blockieren von Nachrichten und erhalten Sie Zugriff auf It `CArchive`, Unterschiede in der Bytereihenfolge und zeichenfolgenkonvertierung für Sie verwaltet.

Weitere Informationen finden Sie unter:

- [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md)

- [Windows Sockets: Stream-Sockets](../mfc/windows-sockets-stream-sockets.md)

- [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)
