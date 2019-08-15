---
title: Windows-Sockets in MFC
ms.date: 11/04/2016
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
ms.openlocfilehash: 44a4838a1cd863bd484701966a156be9f61f8988
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510628"
---
# <a name="windows-sockets-in-mfc"></a>Windows-Sockets in MFC

> [!NOTE]
>  MFC unterstützt Windows Sockets 1, bietet jedoch keine Unterstützung für [Windows Sockets 2](/windows/win32/WinSock/windows-sockets-start-page-2). Windows Sockets 2 wurde zunächst mit Windows 98 ausgeliefert und ist die in Windows 2000 enthaltene Version.

MFC bietet zwei Modelle zum Schreiben von Netzwerk Kommunikationsprogrammen mit Windows Sockets, die in zwei MFC-Klassen enthalten sind. In diesem Artikel werden diese Modelle und weitere Details zur MFC-Socketunterstützung beschrieben. Ein "Socket" ist ein Kommunikations Endpunkt: ein Objekt, über das Ihre Anwendung über ein Netzwerk mit anderen Windows Sockets-Anwendungen kommuniziert.

Informationen zu Windows Sockets, einschließlich einer Erläuterung des Socketkonzepts, finden [Sie unter Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md).

##  <a name="_core_sockets_programming_models"></a>Sockets-Programmier Modelle

Die beiden MFC-Windows Sockets-Programmier Modelle werden von den folgenden Klassen unterstützt:

- `CAsyncSocket`

   Diese Klasse kapselt die Windows Sockets-API. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) ist für Programmierer gedacht, die die Netzwerk Programmierung kennen und die Flexibilität der direkten Programmierung mit der Sockets-API wünschen, aber auch die Vorteile von Rückruf Funktionen für die Benachrichtigung von Netzwerk Ereignissen benötigen. Abgesehen von der Verpackung von Sockets in objektorientierter Form zur Verwendung C++in ist die einzige zusätzliche Abstraktion, die diese Klasse bereitstellt, bestimmte socketbezogene Windows-Meldungen in Rückrufe. Weitere Informationen finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md).

- `CSocket`

   Diese Klasse, die von `CAsyncSocket`abgeleitet ist, stellt eine Abstraktion auf höherer Ebene für die Arbeit mit Sockets über ein MFC- [CArchive](../mfc/reference/carchive-class.md) -Objekt bereit. Die Verwendung eines Sockets mit einem Archiv ähnelt der Verwendung des Datei-serialisierungsprotokolls von MFC. Dies erleichtert die Verwendung als das `CAsyncSocket` Modell. [CSocket](../mfc/reference/csocket-class.md) erbt viele Member-Funktionen `CAsyncSocket` von, die Windows Sockets-APIs Kapseln. Sie müssen einige dieser Funktionen verwenden und die Socketprogrammierung im Allgemeinen verstehen. Verwaltet `CSocket` jedoch viele Aspekte der Kommunikation, die Sie selbst mithilfe der RAW-API oder der-Klasse `CAsyncSocket`ausführen müssten. Am wichtigsten ist `CSocket` , dass eine Blockierung (mit Hintergrundverarbeitung von Windows-Meldungen) bereitstellt, die für `CArchive`den synchronen Betrieb von unverzichtbar ist.

Das Erstellen und `CSocket` verwenden `CAsyncSocket` von-Objekten und [-Objekten wird in Windows Sockets beschrieben: Verwenden von Sockets mit](../mfc/windows-sockets-using-sockets-with-archives.md) Archiven [und Windows Sockets: Verwenden der CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)-Klasse.

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>Windows Sockets-DLLs

Die Windows Sockets-DLL (Dynamic-Link Libraries) werden von den Microsoft Windows-Betriebssystemen bereitgestellt. Visual C++ liefert die entsprechenden Header Dateien und Bibliotheken sowie die Windows Sockets-Spezifikation.

Weitere Informationen zu Windows Sockets finden Sie unter:

- [Windows-Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Abfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows-Sockets: Beispiel für Sockets mithilfe von Archiven](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows-Sockets: Funktionsweise von Sockets mit Archiven](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows-Sockets: Verwenden der Klasse „CAsyncSocket“](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Ableiten aus Socketklassen](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows-Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md)

- [Windows-Sockets: Blocking](../mfc/windows-sockets-blocking.md)

- [Windows-Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)

- [Windows-Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)

- [Windows-Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets](../mfc/windows-sockets.md)
