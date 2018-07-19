---
title: 'Windows Sockets: Blockieren | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ec6b8383f13e8b632163a1fe83a2cd79f7966c5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956186"
---
# <a name="windows-sockets-blocking"></a>Windows Sockets: Blocking
In diesem Artikel sowie zwei Begleit-Artikel wird erläutert, mehrere Probleme bei der Windows Sockets-Programmierung. Dieser Artikel behandelt das blockieren. Die anderen Probleme werden in den Artikeln behandelt: [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) und [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).  
  
 Wenn Sie verwenden oder eine von der Klasse Ableitung [CAsyncSocket](../mfc/reference/casyncsocket-class.md), müssen Sie diese Probleme selbst verwalten. Wenn Sie verwenden oder eine von der Klasse Ableitung [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.  
  
## <a name="blocking"></a>Blockieren  
 Ein Socket kann in "blockieren" oder "nicht blockierenden Modus." Die Funktionen von Sockets im blockierenden (oder synchronen) Modus geben keine zurück, bis sie ihre Aktion abgeschlossen werden können. Heißt dies blockieren, da der Socket, dessen Funktion aufgerufen wurde, nichts zu tun kann nicht – wird blockiert, bis der Aufruf zurückkehrt. Ein Aufruf der `Receive` Memberfunktion ist, z. B. möglicherweise eine willkürlich lange Zeit in Anspruch nehmen, wie er darauf wartet, dass die sendende Anwendung senden (Dies ist bei Verwendung von `CSocket`, oder über `CAsyncSocket` mit blockieren). Wenn eine `CAsyncSocket` Objekt befindet sich im nicht blockierenden Modi (asynchron), der Aufruf sofort zurückgegeben und aktuelle abrufbar mit Fehlercode die [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) Memberfunktion ist **WSAEWOULDBLOCK**, gibt an, dass der Aufruf blockiert worden wäre es aufgrund der Modus ist nicht sofort zurückgegeben wurde. (`CSocket` nie zurückgegeben **WSAEWOULDBLOCK**. Die Klasse verwaltet Sie blockiert.)  
  
 Das Verhalten des Sockets unterscheidet sich bei 32-Bit und 64-Bit-Betriebssystemen (z. B. Windows 95 oder Windows 98) als bei 16-Bit-Betriebssystemen (z. B. Windows 3.1 oder höher). Im Gegensatz zu 16-Bit-Betriebssystemen die 32-Bit und 64-Bit-Betriebssysteme präemptives Multitasking verwenden und multithreading bereitzustellen. Unter der 32-Bit und 64-Bit-Betriebssystemen können Sie Ihre Sockets in separaten Arbeitsthreads einfügen. Ein Socket in einem Thread kann ohne Konflikte mit anderen Aktivitäten in der Anwendung und ohne die Ausgaben von Rechenzeit für die Blockierung zu blockieren. Informationen zu Multithreading-Programmierung, finden Sie im Artikel [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
> [!NOTE]
>  In Multithreadanwendungen verwendet werden können, können Sie den blockierenden Charakter `CSocket` Entwurf Ihres Programms ohne Auswirkungen auf die Reaktionsfähigkeit der Benutzeroberfläche zu vereinfachen. Durch die Behandlung von Benutzerinteraktionen im Hauptthread und `CSocket` Verarbeitung in anderen Threads, können Sie diese logische Vorgänge trennen. In einer Anwendung, die nicht Multithread ist, diese zwei Aktivitäten kombiniert und als also in der Regel mit einem einzelnen Thread behandelt werden müssen `CAsyncSocket` damit Kommunikation Anforderungen bedarfsgesteuerte oder überschreiben behandelt werden kann `CSocket::OnMessagePending` um Benutzeraktionen zu behandeln. bei längeren synchrone Aktivität.  
  
 Der Rest des in dieser Diskussion ist für Programmierer, die 16-Bit-Betriebssysteme abzielt:  
  
 In der Regel bei Verwendung von `CAsyncSocket`, sollten Sie mithilfe von blockierenden Vorgängen vermeiden und stattdessen asynchron arbeiten. Asynchrone Vorgänge, an dem Punkt, an dem Sie empfangen, eine **WSAEWOULDBLOCK** Fehlercode nach dem Aufruf `Receive`, angenommen, Sie warten, bis Ihre `OnReceive` Memberfunktion aufgerufen wird, damit Sie benachrichtigt werden, dass Sie lesen können erneut aus. Asynchrone Aufrufe von Rückrufe des Sockets entsprechende Benachrichtigung Rückruffunktion an, wie z. B. [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).  
  
 Unter Windows werden blockierende Aufrufe nicht üblich berücksichtigt. Standardmäßig [CAsyncSocket](../mfc/reference/casyncsocket-class.md) asynchrone Aufrufe unterstützt, und Sie müssen die Blockierung mit Rückruf Benachrichtigungen selbst verwalten. Klasse [CSocket](../mfc/reference/csocket-class.md), auf der anderen Seite ist synchron. Er ruft Nachrichten von Windows und Blockierung für Sie verwaltet.  
  
 Weitere Informationen zum Blockieren finden Sie unter der Windows Sockets-Spezifikation. Weitere Informationen zu "On" Funktionen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md) und [Windows Sockets: Ableiten von Socket-Classen](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)

