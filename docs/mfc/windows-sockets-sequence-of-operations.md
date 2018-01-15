---
title: 'Windows Sockets: Reihenfolge der Operationen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], operations
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- sockets [MFC], operations
- stream sockets [MFC]
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70765d94b0104cf905130ce043c2b0e35b26a41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-sequence-of-operations"></a>Windows Sockets: Reihenfolge der Operationen
Dieser Artikel veranschaulicht parallel verwendet werden, die Abfolge der Vorgänge für einen Serversocket und ein Clientsocket. Da die Sockets verwenden `CArchive` Objekte sind notwendigerweise [streamen Sockets](../mfc/windows-sockets-stream-sockets.md).  
  
## <a name="sequence-of-operations-for-a-stream-socket-communication"></a>Reihenfolge der Operationen zur Kommunikation über Streamsockets  
 Bis zum Zeitpunkt der Erstellung einer `CSocketFile` Objekt ist, wird die folgende Sequenz (mit wenigen Unterschieden für Parameter) für beide `CAsyncSocket` und `CSocket`. Ab diesem Zeitpunkt die Sequenz dient ausschließlich zur `CSocket`. Die folgende Tabelle veranschaulicht die Abfolge der Vorgänge für das Einrichten der Kommunikation zwischen einem Client und einem Server.  
  
### <a name="setting-up-communication-between-a-server-and-a-client"></a>Einrichten der Kommunikation zwischen einem Server und einem Client  
  
|Server|Client|  
|------------|------------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - oder - <br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> – oder beide –|`// construct an archive`<br /><br /> `CArchive arIn(&file, CArchive::load);`<br /><br /> - oder - <br /><br /> `CArchive arOut(&file, CArchive::store);`<br /><br /> – oder beide –|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - oder - <br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> - oder - <br /><br /> `arOut << dwValue;`6|  
  
 1. Wobei `nPort` ist eine Portnummer. Finden Sie unter [Windows Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md) ausführliche Informationen zu Ports.  
  
 2. Der Server muss immer einen Port angeben, damit Clients eine Verbindung herstellen können. Die **erstellen** Aufruf gibt in manchen Fällen auch eine Adresse. Verwenden Sie auf der Clientseite der Standardparameter, die MFC ermöglicht, verwenden Sie einen beliebigen verfügbaren Port zu bitten.  
  
 3. Wobei `nPort` ist eine Portnummer und *StrAddr* ist eine Adresse des Computers oder einer Adresse Internetprotokoll (IP).  
  
 4. Adressen der Computer können verschiedene Formen annehmen: "ftp.microsoft.com", "microsoft.com". IP-Adressen verwenden Sie das Formular "gepunktet Anzahl" "127.54.67.32". Die **verbinden** Funktion überprüft, um festzustellen, ob die Adresse einer gepunkteten Anzahl (obwohl es nicht überprüft, um sicherzustellen, dass die Anzahl gültiger Computer im Netzwerk). Wenn dies nicht der Fall ist, **verbinden** einen Computernamen einer der anderen Formen annimmt.  
  
 5. Beim Aufruf **Accept** auf Serverseite, übergeben Sie einen Verweis auf ein neues Socketobjekt. Sie müssen dieses Objekt zunächst erstellen, rufen Sie jedoch nicht **erstellen** dafür. Beachten Sie, dass wenn dieser Socketobjekt des Bereichs, die Verbindung geschlossen wird. MFC stellt eine Verbindung her, das neue Objekt ein **SOCKET** behandeln. Sie können den Socket auf dem Stapel, wie dargestellt, oder klicken Sie auf dem Heap erstellen.  
  
 6. Die Archivierungs- und die Socketdatei geschlossen werden, wenn sie außerhalb des Gültigkeitsbereichs liegen. Das Socketobjekt-Destruktor ruft auch die [schließen](../mfc/reference/casyncsocket-class.md#close) Memberfunktion für die Socketobjekt, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.  
  
## <a name="additional-notes-about-the-sequence"></a>Weitere Hinweise zum der Sequenz  
 Die Reihenfolge der Aufrufe, die in der obigen Tabelle aufgeführten ist für einen Datenstrom-Socket. Datagrammsockets, die verbindungslose sind, erfordern keine der [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect), [Lauschen](../mfc/reference/casyncsocket-class.md#listen), und [Accept](../mfc/reference/casyncsocket-class.md#accept) Aufrufe (obwohl Sie optional können**Verbinden**). Stattdessen bei Verwendung der Klasse `CAsyncSocket`, Datagramm-sockets verwendet den `CAsyncSocket::SendTo` und `ReceiveFrom` Memberfunktionen. (Bei Verwendung von **verbinden** mit einen Datagrammsocket verwenden Sie **senden** und **Receive**.) Da `CArchive` funktioniert nicht mit Datagramme, verwenden Sie keine `CSocket` mit einem Archiv, wenn der Socket ein Datagramm ist.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md) unterstützen nicht alle `CFile`Funktionalität. `CFile` Elemente wie z. B. `Seek`, die für die Socketkommunikation keine sinnvoll sind nicht verfügbar. Aus diesem Grund standardmäßig einige MFC `Serialize` Funktionen sind nicht kompatibel mit `CSocketFile`. Dies gilt insbesondere für die `CEditView` Klasse. Sie sollten nicht versuchen, serialisieren `CEditView` Daten über eine `CArchive` Objekt angefügt, um eine `CSocketFile` -Objekt unter Verwendung `CEditView::SerializeRaw`; verwenden **CEditView:: Serialize** stattdessen (nicht dokumentiert). Die [SerializeRaw](../mfc/reference/ceditview-class.md#serializeraw) erwartet das Objekt "Datei", haben die Funktionen, z. B. `Seek`, `CSocketFile` nicht unterstützt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket-Klasse](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../mfc/reference/casyncsocket-class.md#create)   
 [CAsyncSocket::Close](../mfc/reference/casyncsocket-class.md#close)

