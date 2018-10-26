---
title: Windows-Sockets in MFC | Microsoft-Dokumentation
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
ms.openlocfilehash: a460870887f3a012bf02ee6518ba70c65881c804
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081416"
---
# <a name="windows-sockets-in-mfc"></a>Windows-Sockets in MFC

> [!NOTE]
>  MFC unterstützt Windows Sockets-1 unterstützt jedoch keine [Windows Sockets 2](/windows/desktop/WinSock/windows-sockets-start-page-2). Windows Sockets-2 wird zuerst im Lieferumfang von Windows 98 und die Version, mit Windows 2000 enthalten ist.

MFC bietet zwei Modelle für das Schreiben von mit Windows-Sockets, zwei Klassen von MFC vorliegen. In diesem Artikel wird beschrieben, diese Modelle und weitere Details MFC-sockets unterstützt. Ein "Socket" ist ein Endpunkt der Kommunikation: ein Objekt, das über die Ihre Anwendung mit anderen Windows Sockets-Anwendungen in einem Netzwerk kommuniziert.

Weitere Informationen zu Windows-Sockets, einschließlich einer Erläuterung der Socket-Konzept, finden Sie unter [Windows Sockets: Hintergrund](../mfc/windows-sockets-background.md).

##  <a name="_core_sockets_programming_models"></a> Sockets-Programmiermodelle

Die zwei MFC Windows Sockets-Programmiermodelle nutzen, werden durch die folgenden Klassen unterstützt:

- `CAsyncSocket`

   Diese Klasse kapselt die Windows Sockets-API. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) ist für Programmierer, die netzwerkprogrammierung wissen und die Flexibilität des direkten Programmieren auf Sockets-API auch möchten jedoch die Vorteile von Rückruffunktionen für Benachrichtigungen über Netzwerkereignisse. Als Packen-Sockets in objektorientierten Formular für die Verwendung in C++ ist der einzige zusätzliche Abstraktion, die diese Klasse stellt bestimmte Socket-bezogene Windows-Nachrichten in Rückrufen konvertiert. Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md).

- `CSocket`

   Diese Klasse, aus abgeleiteten `CAsyncSocket`, liefert einen höheren Abstraktionsgrad für die Arbeit mit Sockets über ein MFC [CArchive](../mfc/reference/carchive-class.md) Objekt. Verwenden einen Socket mit einem Archiv erheblich ähnelt der MFC Serialisierung Dateiprotokoll. Dies erleichtert es zu verwenden als die `CAsyncSocket` Modell. [CSocket](../mfc/reference/csocket-class.md) erbt viele Memberfunktionen aus `CAsyncSocket` , die Windows Sockets-APIs kapseln, müssen einige dieser Funktionen verwenden, und Verstehen von Socketprogrammierung. Aber `CSocket` verwaltet viele Aspekte der Kommunikation, die Sie mit der raw-API oder Klasse selbst durchzuführen hätten `CAsyncSocket`. Der wichtigste `CSocket` bietet blockiert (mit der Verarbeitung im Hintergrund von Windows-Nachrichten), ist wichtig, damit die synchronen Vorgang `CArchive`.

Erstellen und Verwenden von `CSocket` und `CAsyncSocket` Objekte finden Sie im [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md) und [Windows Sockets: CAsyncSocket-Klasse unter Verwendung](../mfc/windows-sockets-using-class-casyncsocket.md).

##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets-DLLs

Die Microsoft Windows-Betriebssysteme bereitstellen der Windows Sockets-Dynamic Link Libraries (DLL). Visual C++ bietet die entsprechenden Headerdateien und Bibliotheken und die Windows Sockets-Spezifikation.

Weitere Informationen zu Windows-Sockets finden Sie unter:

- [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Reihenfolge der Operationen](../mfc/windows-sockets-sequence-of-operations.md)

- [Windows-Sockets: Beispiel für Sockets mithilfe der Archive](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Ableiten von Socket-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows-Sockets: Socketbenachrichtigungen](../mfc/windows-sockets-socket-notifications.md)

- [Windows-Sockets: Blocking](../mfc/windows-sockets-blocking.md)

- [Windows-Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md)

- [Windows-Sockets: Umwandeln von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md)

- [Windows-Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets](../mfc/windows-sockets.md)

