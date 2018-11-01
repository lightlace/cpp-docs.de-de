---
title: 'Windows Sockets: Blocking'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 7b41f034e08570e418bf24d9d720795eafc37932
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610573"
---
# <a name="windows-sockets-blocking"></a>Windows Sockets: Blocking

In diesem Artikel und zwei begleitenden Artikel erläutern mehrere Probleme bei der Windows Sockets-Programmierung. In diesem Artikel behandelt das blockieren. Die anderen Probleme werden in den Artikeln behandelt: [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) und [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).

Wenn Sie verwenden, oder leiten Sie von der Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Sie müssen diese Probleme selbst zu verwalten. Wenn Sie verwenden, oder leiten Sie von der Klasse [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.

## <a name="blocking"></a>Blockieren

Ein Socket kann sich in "blockieren" oder "nicht blockierenden Modus." befinden. Die Funktionen des Sockets im blockierenden (oder synchrone) Modus geben keine zurück, bis sie die Aktion abgeschlossen werden können. Dies wird aufgerufen, blockiert werden, da der Socket, deren Funktion aufgerufen wurde, kann keine Aktionen ausführen: wird blockiert, bis der Aufruf zurückgegeben. Ein Aufruf der `Receive` Member-Funktion, z. B. kann ein beliebig lange dauern abgeschlossen werden, weil er darauf wartet, dass die sendende Anwendung zum Senden von (Dies ist bei Verwendung von `CSocket`, oder `CAsyncSocket` beim blockieren). Wenn eine `CAsyncSocket` Objekt befindet sich im nicht blockierenden Modus (asynchron arbeitet), der Aufruf sofort zurückgegeben und der aktuellen Fehlercode, die abgerufen, mit der [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) Member-Funktion ist **WSAEWOULDBLOCK**, gibt an, dass der Aufruf blockiert wäre es nicht sofort zurückgegeben werden, da der Modus haben. (`CSocket` gibt nie Werte zurück **WSAEWOULDBLOCK**. Die Klasse verwaltet für Sie blockiert.)

Das Verhalten des Sockets unterscheidet sich bei 32-Bit und 64-Bit-Betriebssystemen (z. B. Windows 95 oder Windows 98) als bei 16-Bit-Betriebssystemen (z. B. Windows 3.1). Im Gegensatz zu 16-Bit-Betriebssystemen die 32-Bit- und 64-Bit-Betriebssysteme verwenden, präemptives Multitasking und multithreading bereitzustellen. Bei den 32-Bit und 64-Bit-Betriebssystemen können Sie Ihre Sockets in separaten Arbeitsthreads einfügen. Ein Socket in einem Thread kann ohne Konflikte mit anderen Aktivitäten in Ihrer Anwendung und ohne die Ausgaben von Compute-Zeit für die Blockierung blockieren. Informationen zur Multithreadprogrammierung finden Sie im Artikel [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).

> [!NOTE]
>  In Multithread-Anwendungen können Sie die blockierende Art der `CSocket` Ihres Programms Entwurf zu vereinfachen, ohne Auswirkungen auf die Reaktionsfähigkeit der Benutzeroberfläche. Durch das Behandeln von Interaktionen der Benutzer im Hauptthread und `CSocket` in anderen Threads verarbeiten, können Sie diesen logischen Vorgängen trennen. In einer Anwendung, die nicht von mehreren Threads ist, diese beiden Aktivitäten kombiniert und als also in der Regel mit einem einzelnen Thread verarbeitet werden müssen `CAsyncSocket` damit Sie die Kommunikation Anforderungen bedarfsgesteuerte oder überschreiben behandeln können `CSocket::OnMessagePending` um Benutzeraktionen zu behandeln. bei längeren synchrone-Aktivität.

Der Rest dieser Diskussion ist für Programmierer, die für 16-Bit-Betriebssysteme:

In der Regel bei Verwendung von `CAsyncSocket`, sollten Sie vermeiden Sie die Verwendung von blockiervorgängen ist und stattdessen asynchron arbeiten. In asynchrone Vorgänge, an dem Punkt, an dem Sie empfangen, eine **WSAEWOULDBLOCK** Fehlercode: nach dem Aufruf `Receive`, z. B. Sie warten, bis Ihre `OnReceive` Memberfunktion aufgerufen wird, um benachrichtigt zu werden, dass Sie lesen können erneut aus. Asynchrone Aufrufe werden durch den Aufruf zurück des Sockets korrekte Rückruf-Benachrichtigung-Funktion, wie z. B. [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).

Unter Windows gelten die blockierende Aufrufe nicht üblich. In der Standardeinstellung [CAsyncSocket](../mfc/reference/casyncsocket-class.md) asynchrone Aufrufe unterstützt, und Sie müssen die Blockierung mit rückrufbenachrichtigungen selbst verwalten. Klasse [CSocket](../mfc/reference/csocket-class.md), auf der anderen Seite ist synchron. Er ruft Nachrichten von Windows und verwaltet, für die Sie blockieren.

Weitere Informationen zum Blockieren finden Sie unter der Windows Sockets-Spezifikation. Weitere Informationen zu "On"-Funktionen, finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md) und [Windows Sockets: Ableiten von Socket-Classen](../mfc/windows-sockets-deriving-from-socket-classes.md).

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

- [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)

