---
title: Windows-Sockets in MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84fc25ab6515b22fa647b3cc32833c791b59f2b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385511"
---
# <a name="windows-sockets-in-mfc"></a>Windows-Sockets in MFC
> [!NOTE]
>  MFC unterstützt Windows Sockets-1, jedoch keine [Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673). Windows Sockets 2 zuerst im Lieferumfang von Windows 98 und Windows 2000 enthaltene Version ist.  
  
 MFC stellt zwei Modelle für die Netzwerk-Kommunikation Programmentwicklung mit Windows-Sockets in MFC-Klassen, die zwei Begriffe bereit. Dieser Artikel beschreibt diese Modelle und weiteren Details MFC-sockets unterstützt. Ein "Socket" ist ein Endpunkt der Kommunikation: ein Objekt, das über die kommuniziert die Anwendung mit anderen Windows-Sockets-Anwendungen in einem Netzwerk.  
  
 Windows Sockets, einschließlich einer Erläuterung der Socketkonzepts: Informationen finden Sie unter [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a> Sockets Programmiermodelle  
 Die beiden Windows Sockets in MFC Programmiermodelle werden von den folgenden Klassen unterstützt:  
  
-   `CAsyncSocket`  
  
     Diese Klasse kapselt die Windows Sockets-API. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) für Programmierer, die netzwerkprogrammierung kennen und die Flexibilität der Programmierung direkt an Sockets-API auch möchten jedoch die Vorteile von Rückruffunktionen für die Benachrichtigung über Netzwerkereignisse ist. Als Verpacken-Sockets in objektorientierten Formular für die Verwendung in C++, ist die nur zusätzliche Abstraktion, die diese Klasse stellt bestimmte Socket-bezogene Windows-Meldungen in Rückrufe konvertiert. Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Diese Klasse abgeleitet `CAsyncSocket`, liefert einen höheren Abstraktionsgrad für die Arbeit mit über ein MFC-Sockets [CArchive](../mfc/reference/carchive-class.md) Objekt. Verwenden einen Socket mit einem Archiv erheblich ähnelt der MFC Serialisierung Dateiprotokoll. Dies erleichtert es zu verwenden als die `CAsyncSocket` Modell. [CSocket](../mfc/reference/csocket-class.md) erbt viele Memberfunktionen von `CAsyncSocket` , der Windows Sockets-APIs kapseln; einiger dieser Funktionen und Socketprogrammierung verstehen müssen. Aber `CSocket` verwaltet viele Aspekte der Kommunikation, die Sie selbst unter Verwendung der raw-API oder Klasse `CAsyncSocket`. Am wichtigsten ist, `CSocket` enthält (mit hintergrundverarbeitung von Windows-Nachrichten) blockieren ist wichtig, damit die synchrone Ausführung von `CArchive`.  
  
 Erstellen und Verwenden von `CSocket` und `CAsyncSocket` Objekte wird beschrieben, [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md) und [Windows Sockets: verwenden CAsyncSocket-Klasse](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets-DLLs  
 Microsoft Windows-Betriebssysteme Geben Sie die Windows-Sockets Dynamic Link Libraries (DLL). Visual C++ bietet die entsprechenden Header-Dateien und Bibliotheken und der Windows Sockets-Spezifikation.  
  
 Weitere Informationen zu Windows-Sockets finden Sie unter:  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows-Sockets: Reihenfolge der Operationen](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows-Sockets: Beispiel für Sockets mithilfe der Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Ableiten von Socket-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows-Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows-Sockets: Blocking](../mfc/windows-sockets-blocking.md)  
  
-   [Windows-Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows-Sockets: Umwandeln von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows-Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets](../mfc/windows-sockets.md)

