---
title: "Windows Sockets: Reihenfolge der Operationen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Sockets [C++], Operationen"
  - "Sockets [C++], Streamsockets"
  - "Streamsockets [C++]"
  - "Windows-Sockets [C++], Operationen"
  - "Windows-Sockets [C++], Streamsockets"
ms.assetid: 43ce76f5-aad3-4247-b8a6-16cc7d012796
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets: Reihenfolge der Operationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel veranschaulicht, parallel, die Reihenfolge der Vorgänge für einen Serversocket und einen Clientsocket.  Da die Sockets `CArchive`\-Objekte verwenden, weisen diese immer eine [Streamsockets](../mfc/windows-sockets-stream-sockets.md).  
  
## Sequenz von Vorgängen für eine Streamsocket\-Kommunikation  
 Bis zum Punkt zum Erstellen eines `CSocketFile`\-Objekts, ist die folgende Sequenz \(mit einigen Parameterunterschieden\) für `CAsyncSocket` und `CSocket` genau.  Von diesem Zeitpunkt an, ist die Sequenz nur für `CSocket`.  Die folgende Tabelle zeigt die Reihenfolge der Vorgänge zum Installieren von Kommunikation zwischen einem Client und einem Server.  
  
### Aufstellungs\-Kommunikation zwischen einem Client und einem Server  
  
|Server|Client|  
|------------|------------|  
|`// construct a socket`<br /><br /> `CSocket sockSrvr;`|`// construct a socket`<br /><br /> `CSocket sockClient;`|  
|`// create the SOCKET`<br /><br /> `sockSrvr.Create(nPort);`1,2|`// create the SOCKET`<br /><br /> `sockClient.Create( );`2|  
|`// start listening`<br /><br /> `sockSrvr.Listen( );`||  
||`// seek a connection`<br /><br /> `sockClient.Connect(strAddr, nPort);`3,4|  
|`// construct a new, empty socket`<br /><br /> `CSocket sockRecv;`<br /><br /> `// accept connection`<br /><br /> `sockSrvr.Accept( sockRecv );` 5||  
|`// construct file object`<br /><br /> `CSocketFile file(&sockRecv);`|`// construct file object`<br /><br /> `CSocketFile file(&sockClient);`|  
|`// construct an archive`<br /><br /> `CArchive arIn(&file,`  `CArchive::load);`<br /><br /> \- oder \-<br /><br /> `CArchive arOut(&file,`  `CArchive::store);`<br /><br /> \- oder beide \-|`// construct an archive`<br /><br /> `CArchive arIn(&file,`  `CArchive::load);`<br /><br /> \- oder \-<br /><br /> `CArchive arOut(&file,`  `CArchive::store);`<br /><br /> \- oder beide \-|  
|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> \- oder \-<br /><br /> `arOut << dwValue;`6|`// use the archive to pass data:`<br /><br /> `arIn >> dwValue;`<br /><br /> \- oder \-<br /><br /> `arOut << dwValue;`6|  
  
 1.  Dabei ist `nPort` eine Portnummer ist.  Siehe [Windows Sockets: Anschlüsse und Socket\-Adressen](../mfc/windows-sockets-ports-and-socket-addresses.md) Details darüber Ports.  
  
 2.  Der Server muss einem Port immer angeben, daher können Clients herstellen.  **Erstellen** Der Aufruf wird manchmal auch einer Adresse an.  auf der Clientseite verwenden Sie die Standardparameter, die MFC anfordern, einen beliebigen verfügbaren Anschluss verwenden.  
  
 3.  Wo `nPort` ist, ist eine Portnummer und *ein strAddr* eine Computeradresse Internetprotokoll \(ip\)\- oder eine Adresse.  
  
 4.  Computeradressen können verschiedene Formen aufweisen: "ftp.microsoft.com", "microsoft.com".  IP\-Adressen verwenden das "durch Punkte getrennte Zahlen\-" Formular "127.54.67.32".  Die **Verbinden**\-Funktionsüberprüfungen, um, wenn die Adresse eine durch Punkte getrennte Zahl ist \(obwohl sie nicht überprüft, um sicherzustellen, Zahl\- zu finden ist ein gültiger Computer im Netzwerk\).  Wenn nicht, wird **Verbinden** einen Computernamen aus einem der anderen Formate an.  
  
 5.  Wenn Sie **Annehmen** auf Serverseite aufrufen, übergeben Sie einen Verweis auf einen neuen Socketobjekt.  Sie müssen dieses Objekt zuerst erstellen, aber rufen **Erstellen** nicht für sie auf.  Beachten Sie, dass, wenn dieses Socketobjekt des Gültigkeitsbereichs, die Verbindung schließt.  MFC enthält das neue Objekt auf **SOCKET** Handle an.  Sie können den Socket auf dem Stapel, wie dargestellt oder auf dem Heap erstellt.  
  
 6.  Das Archiv und die Socketdatei werden geschlossen, wenn sie den Gültigkeitsbereich verlassen.  Der Destruktor des Socketobjekts ruft außerdem die [Schließen](../Topic/CAsyncSocket::Close.md) für das Socketobjekt Memberfunktion auf, wenn das Objekt den Gültigkeitsbereich verlässt oder gelöscht wird.  
  
## Zusätzliche Hinweise zur Sequenz  
 Die Sequenz von Aufrufen, die in der vorherigen Tabelle aufgeführt sind, ist für einen Streamsocket.  Datagrammsockets, die verbindungslos sind, benötigen nicht [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md), [Lauschen Sie](../Topic/CAsyncSocket::Listen.md) und [Annehmen](../Topic/CAsyncSocket::Accept.md) aufgerufen \(obwohl Sie **Verbinden** optional verwenden können\).  Sie stattdessen Klasse `CAsyncSocket` verwenden, verwenden Datagrammsockets die Memberfunktionen `CAsyncSocket::SendTo` und `ReceiveFrom`. \(Wenn Sie **Verbinden** mit einem Datagrammsocket verwenden, verwenden Sie **Senden** und **Empfangen**.\) Da `CArchive` nicht mit Datagrammen funktioniert, verwenden Sie nicht `CSocket` mit einem Archiv, wenn der Socket ein Datagramm ist.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md) unterstützt nicht alle `CFile`\-Funktionen; `CFile`\-Member wie `Seek`, die nicht sinnvoll für eine Socketkommunikation sind, sind nicht verfügbar.  Deswegen nehmen einige Funktionen MFC `Serialize` sind nicht kompatibel mit `CSocketFile` den Standardwert an.  Dies ist von der `CEditView`\-Klasse insbesondere.  Versuchen Sie nicht, Daten über `CEditView` ein `CArchive` zu serialisierende Objekt, das auf ein `CSocketFile`\-Objekt mit `CEditView::SerializeRaw` angefügt wird; Verwenden Sie stattdessen **CEditView::Serialize** \(nicht dokumentiert\).  Die [SerializeRaw](../Topic/CEditView::SerializeRaw.md)\-Funktion erwartet das Dateiobjekt, um Funktionen, z `Seek` haben, das `CSocketFile` nicht unterstützt.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets: Anschlüsse und Socket\-Adressen](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
-   [Windows Sockets: Streamsockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket Class](../mfc/reference/csocket-class.md)   
 [CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)   
 [CAsyncSocket::Close](../Topic/CAsyncSocket::Close.md)