---
title: 'Windows Sockets: Reihenfolge der Operationen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9667bf7359677d00b54023cb5542ffd7977baa02
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376047"
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows Sockets: Reihenfolge der Operationen

Dieser Artikel veranschaulicht, nebeneinander, die Reihenfolge der Vorgänge für einen Serversocket und einem Clientsocket. Da die Sockets verwenden `CArchive` Objekte, sie sind notwendigerweise [streamen Sockets](../mfc/windows-sockets-stream-sockets.md).

## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Reihenfolge der Operationen für eine Stream-Socket-Kommunikation

Bis zum Zeitpunkt der Erstellung einer `CSocketFile` Objekt ist, wird die folgende Sequenz (mit ein paar Unterschiede für Parameter) für beide `CAsyncSocket` und `CSocket`. Von diesem Zeitpunkt an, die Sequenz dient ausschließlich zur `CSocket`. Die folgende Tabelle zeigt die Reihenfolge der Vorgänge zum Einrichten der Kommunikation zwischen einem Client und einem Server.

### <a name="setting-up-communication-between-a-server-and-a-client"></a>Einrichten der Kommunikation zwischen einem Server und einem Client

|Server|Client|
|------------|------------|
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - oder - <br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> – oder beides –|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - oder - <br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> – oder beides –|
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - oder - <br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - oder - <br /><br /> `arOut << dwValue;`6|

1. Wo *%nPort* ist eine Portnummer. Finden Sie unter [Windows Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md) ausführliche Informationen zu Ports.

2. Der Server muss immer einen Port angeben, damit Clients eine Verbindung herstellen können. Die `Create` Aufruf gibt auch eine Adresse an. Verwenden Sie auf der Clientseite die Standardparameter, die Fragen von MFC über einen beliebigen verfügbaren Port verwenden.

3. Wo *%nPort* ist eine Portnummer und *StrAddr* ist eine Adresse des Computers oder eine IP (Internet Protocol)-Adresse.

4. Computeradressen können unterschiedliche Formen annehmen: "ftp.microsoft.com", "microsoft.com". IP-Adressen verwenden Sie das Formular "gepunktet Anzahl" "127.54.67.32". Die `Connect` Funktion überprüft, ob die Adresse einer durch Punkte getrennte Zahl ist (obwohl es nicht überprüft, um sicherzustellen, dass die Anzahl gültiger Computer im Netzwerk). Wenn dies nicht der Fall ist, `Connect` geht davon aus einen Computernamen, der eine der anderen Formen.

5. Beim Aufruf `Accept` auf dem Server, übergeben Sie einen Verweis auf ein neues Socketobjekt. Sie müssen zuerst dieses Objekt erstellen, rufen Sie jedoch nicht `Create` dafür. Beachten Sie, dass wenn dieser Socketobjekt des Bereichs, die Verbindung geschlossen wird. MFC stellt eine Verbindung her, das neue Objekt ein **SOCKET** behandeln. Sie können den Socket, auf dem Stapel, wie gezeigt, oder klicken Sie auf dem Heap erstellen.

6. Das Archiv und die Datei geschlossen werden, wenn sie den gültigen Bereich verlassen. Der Socket Destruktor ruft auch die [schließen](../mfc/reference/casyncsocket-class.md#close) Memberfunktion für die Socketobjekt, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.

## <a name="additional-notes-about-the-sequence"></a>Weitere Hinweise für die Sequenz

Die Reihenfolge der Aufrufe, die in der obigen Tabelle aufgeführten ist für einen Streamsocket. Datagrammsockets, die verbindungslose sind, erfordern keine der [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect), [Lauschen](../mfc/reference/casyncsocket-class.md#listen), und [Accept](../mfc/reference/casyncsocket-class.md#accept) Aufrufe (Sie können zwar optional verwenden`Connect`). Stattdessen bei Verwendung der Klasse `CAsyncSocket`, Datagramm-sockets verwendet der `CAsyncSocket::SendTo` und `ReceiveFrom` Memberfunktionen. (Bei Verwendung von `Connect` mit einen Datagrammsocket Verwendung `Send` und `Receive`.) Da `CArchive` funktioniert nicht mit Datagramme, verwenden Sie keine `CSocket` mit einem Archiv, wenn der Socket ein Datagramm ist.

[CSocketFile](../mfc/reference/csocketfile-class.md) unterstützt nicht alle `CFile`Funktionen `CFile` Elemente wie z. B. `Seek`, die keinen Sinn für einen Socketkommunikation nicht verfügbar sind. Aus diesem Grund standardmäßig einige MFC `Serialize` Funktionen sind nicht kompatibel mit `CSocketFile`. Dies gilt insbesondere für die `CEditView` Klasse. Sie sollten nicht versuchen, serialisieren `CEditView` Daten über eine `CArchive` Objekt angefügt, um eine `CSocketFile` -Objekt mit `CEditView::SerializeRaw`; verwenden `CEditView::Serialize` stattdessen (nicht dokumentiert). Die [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) erwartet das Dateiobjekt, wenn Funktionen wie `Seek`, `CSocketFile` wird nicht unterstützt.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md)

- [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[CSocket-Klasse](../mfc/reference/csocket-class.md)<br/>
[CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)<br/>
[CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)

