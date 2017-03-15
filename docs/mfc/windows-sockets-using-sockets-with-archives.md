---
title: "Windows Sockets: Verwenden von Sockets mit Archiven | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Archive [C++], und Windows-Sockets"
  - "CSocket-Klasse, Programmiermodell"
  - "Sockets [C++], mit Archiven"
  - "Windows-Sockets [C++], Archive"
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows Sockets: Verwenden von Sockets mit Archiven
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt [CSocket\-Programmiermodell](#_core_the_csocket_programming_model).  Klasse [CSocket](../mfc/reference/csocket-class.md) stellt Socketunterstützung auf einer höheren Ebene der Abstraktion bereit, als [CAsyncSocket](../mfc/reference/casyncsocket-class.md)\- Klassen.  `CSocket` wird eine Version des MFC\-Serialisierungsprotokolls, um Daten zu und von einem Socketobjekt durch ein Objekt MFC\- [CArchive](../mfc/reference/carchive-class.md) zu übergeben.  `CSocket` stellt das Blockieren \(beim Verwalten von Hintergrundverarbeitung von Windows\-Meldungen\) und bietet Zugriff auf `CArchive`, der zahlreiche Aspekte der Kommunikation verwaltet, dass Sie entweder mithilfe unformatierter API zu tun würden oder `CAsyncSocket`\- Klasse müssen.  
  
> [!TIP]
>  Sie können `CSocket` als Klasse, komfortablere Version von `CAsyncSocket` allein verwenden, aber das einfachste Programmiermodell ist, `CSocket` mit einem `CArchive`\-Objekt zu verwenden.  
  
 Weitere Informationen darüber, wie die die Implementierung von Sockets mit Archiven funktioniert, finden Sie unter [Windows Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md).  Beispielcode finden, [Windows Sockets: Reihenfolge der Operationen](../mfc/windows-sockets-sequence-of-operations.md) und [Windows Sockets: Beispiel für das Verwenden von Sockets mit Archiven](../mfc/windows-sockets-example-of-sockets-using-archives.md).  Informationen über einige der Funktionen, die Sie erhalten, indem Sie eigene Klassen von Socketklassen ableiten, finden Sie unter [Windows Sockets: Ableiten von Socket\-Classen](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
> [!NOTE]
>  Wenn Sie ein MFC\-Clientprogramm schreiben, um mit den festgelegten \(Nicht\-MFC\-\) Servern zu kommunizieren, senden Sie C\+\+\-Objekte nicht durch das Archiv.  Sofern, dass der Server eine MFC\-Anwendung, die den Arten von Objekten, versteht Sie senden möchten, ist unklar, die Objekte zum Empfangen und zu deserialisieren.  Für verwandtes Material bezüglich des Verständigens mit Nicht\-MFC\-Anwendungen, wird auch im Artikel [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md).  
  
##  <a name="_core_the_csocket_programming_model"></a> Das CSocket\-Programmiermodell  
 Verwenden eines `CSocket`\-Objekts umfasst, einige MFC\-Klassen\- mit einobjekte zusammen erstellen und zuordnen.  In der allgemeinen Prozedur unten, wird jeder Schritt durch den Serversocket und den Clientsocket, außer Schritt 3 ausgeführt, in der jeder Sockettyp eine andere Aktion erforderlich.  
  
> [!TIP]
>  Zur Laufzeit wird die Serveranwendung normalerweise zuerst, um bereit und "lauschend" zu sein, wenn die Clientanwendung eine Verbindung sucht.  Wenn der Server nicht bereit ist, wenn der Client versucht herzustellen, benötigen Sie normalerweise die Benutzer\-Anwendung herzustellen, später erneut zu versuchen.  
  
#### Kommunikation zwischen einem Serversocket und einem Clientsocket installieren  
  
1.  Erstellen Sie ein [CSocket](../mfc/reference/csocket-class.md)\-Objekt.  
  
2.  Verwenden Sie das Objekt, um das zugrunde liegende **SOCKET** Handle zu erstellen.  
  
     Ein `CSocket` Clientobjekt sollten Sie die Standardparameter zu [Erstellen](../Topic/CAsyncSocket::Create.md) normalerweise verwenden, es sei denn, Sie einen Datagrammsocket benötigen.  Ein `CSocket` Serverobjekt müssen Sie einen Port im Aufruf **Erstellen** angeben.  
  
    > [!NOTE]
    >  `CArchive` funktioniert nicht mit Datagrammsockets.  Wenn Sie `CSocket` für einen Datagrammsocket verwenden möchten, müssen Sie die Klasse verwenden, wie Sie `CAsyncSocket` h. ohne ein Archiv verwenden würden.  Da Datagramme \(nicht gewährleistet, dass anzukommen und wird möglicherweise aus oder wiederholt\) Sequenz out, unzuverlässig sind, sind sie nicht mit Serialisierung von einem Archiv kompatibel.  Sie erwarten einen Serialisierungsvorgang, um zuverlässig und nacheinander abzuschließen.  Wenn Sie versuchen, `CSocket` mit einem `CArchive`\-Objekt für ein Datagramm zu verwenden, schlägt eine MFC\-Assertion aus.  
  
3.  Wenn der Client ein Socket ist, rufen Sie [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md), um den Socketobjekts zu einem Serversocket herzustellen.  
  
     \- oder \-  
  
     Wenn der Socket ein Server ist, schließen Aufruf [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md), um den Hörens zu starten Versuche von einem Client an.  Bei Empfang einer Aufforderung zum Aufbau einer Verbindung, akzeptieren Sie sie, indem Sie [CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md) aufrufen.  
  
    > [!NOTE]
    >  Die **Annehmen**\-Memberfunktion übernimmt einen Verweis in einem neuen, leeren `CSocket`\-Objekt als Parameter.  Sie müssen dieses Objekt erstellen, bevor Sie **Annehmen** aufrufen.  Wenn dieses Socketobjekt den Bereich verlässt, wird die Verbindung.  Rufen Sie **Erstellen** nicht für dieses neue Socketobjekt auf.  
  
4.  Erstellen Sie ein [CSocketFile](../mfc/reference/csocketfile-class.md)\-Objekt und das `CSocket`\-Objekt damit zuordnen.  
  
5.  Erstellen Sie ein Objekt entweder [CArchive](../mfc/reference/carchive-class.md) für Laden \(Empfangen\) oder das Speichern von Daten \(Senden\).  Im "Archive" wird mit dem `CSocketFile`\-Objekt zugeordnet.  
  
     Beachten Sie, dass `CArchive` nicht mit Datagrammsockets funktioniert.  
  
6.  Verwenden Sie das `CArchive`\-Objekt dem ein Textvorlagenhost zwischen dem Client und den Serversockets.  
  
     Beachten Sie, dass ein bestimmtes `CArchive`\-Objekt Daten in einer Richtung nur verschoben werden: entweder zum Laden \(Empfangen\) oder das Senden \(Speichern\).  In einigen Fällen verwenden Sie zwei `CArchive`\-Objekte: ein für das Senden von Daten, das andere für den Empfang von Bekräftigungen.  
  
     Nachdem Sie eine Verbindung akzeptiert haben und das Archiv installiert haben, können Sie diese Aufgaben wie Kennwörter, Überprüfung durchführen.  
  
7.  Zerstören Sie das Archiv, die Socketdatei und die Socketobjekte.  
  
    > [!NOTE]
    >  Die `CArchive` stellt die `IsBufferEmpty`\-Memberfunktion ausdrücklich für Klasse `CSocket`.  Wenn der Puffer mehrere Datennachrichten beispielsweise enthält müssen Sie durchlaufen, bis alle sind der Puffer gelesen und gelöscht wird.  Andernfalls wird die folgende Benachrichtigung, dass es die empfangen werden gibt Daten, unbegrenzt verzögert werden.  Verwenden Sie `IsBufferEmpty`, um zu gewährleisten, dass Sie alle Daten abrufen.  
  
 Der Artikel [Windows Sockets: Reihenfolge der Operationen](../mfc/windows-sockets-sequence-of-operations.md) veranschaulicht beide Seiten des Prozesses mit Beispielcode.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Siehe auch  
 [Windows\-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)