---
title: "CSocket Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocket class"
  - "SOCKET handle"
  - "sockets classes"
  - "WinSock CSocket class"
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ist von `CAsyncSocket`, erbt die Kapselung der Windows Sockets APIs und stellt eine höhere Abstraktionsebene als das `CAsyncSocket` eines \- Objekts dar.  
  
## Syntax  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSocket::CSocket](../Topic/CSocket::CSocket.md)|Erstellt ein `CSocket`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSocket::Attach](../Topic/CSocket::Attach.md)|Fügt ein **SOCKET** Handle für ein `CSocket`\-Objekt.|  
|[CSocket::CancelBlockingCall](../Topic/CSocket::CancelBlockingCall.md)|Bricht einen blockierenden Aufruf ab, der gerade ausgeführt wird.|  
|[CSocket::Create](../Topic/CSocket::Create.md)|Erstellt einen Socket.|  
|[CSocket::FromHandle](../Topic/CSocket::FromHandle.md)|Gibt einen Zeiger auf ein \- Objekt zurück, `CSocket` ein **SOCKET** Handle angegeben.|  
|[CSocket::IsBlocking](../Topic/CSocket::IsBlocking.md)|Bestimmt, ob ein blockierender Aufruf ausgeführt wird.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSocket::OnMessagePending](../Topic/CSocket::OnMessagePending.md)|Aufgerufen, um während Meldungen beim Warten auf einen blockierenden Aufruf zu verarbeiten, um abzuschließen.|  
  
## Hinweise  
 `CSocket` funktioniert mit Klassen `CSocketFile` und `CArchive`, um das Senden und Empfangen von Daten zu verwalten.  
  
 Ein `CSocket`\-Objekt stellt auch die Blockierung, das dem Gleichlaufbetrieb von `CArchive` erforderlich ist.  Sperrfunktionen, wie `Receive`, `Send`, `ReceiveFrom`, `SendTo` und alle `Accept` \(geerbt von `CAsyncSocket`\), geben `WSAEWOULDBLOCK` keinen Fehler in `CSocket` zurück.  Stattdessen diese Funktionen warten, bis der Vorgang abgeschlossen ist.  Außerdem wird der ursprüngliche Aufruf mit dem Fehler `WSAEINTR`, wenn `CancelBlockingCall` aufgerufen wird, während eine dieser Funktionen blockiert wird.  
  
 Um ein `CSocket`\-Objekt zu verwenden, rufen Sie den \- Konstruktor, dann den Aufruf `Create` auf um das zugrunde liegende `SOCKET` Handle \(Typ `SOCKET`\) zu erstellen.  Die Standardparameter von `Create` erstellen einen Streamsocket, aber, wenn Sie den Socket mit einem `CArchive`\-Objekt verwenden, können Sie einen Parameter, um einen Datagrammsocket oder Bindung angeben an einen bestimmten Port stattdessen zu erstellen, um einen Serversocket zu erstellen.  Stellen Sie eine Verbindung mit einem Clientsocket mithilfe `Connect` auf Clientseite und `Accept` auf Serverseite an.  Anschließend erstellen Sie ein `CSocketFile`\-Objekt und ordnen Sie sie dem `CSocket`\-Objekt im `CSocketFile`\-Konstruktor auf.  Danach erstellen Sie ein `CArchive`\-Objekt zum Senden und einen für das Empfangen von Daten \(bei Bedarf\), und ordnen Sie sie dem `CSocketFile`\-Objekt im `CArchive`\-Konstruktor auf.  Wenn Kommunikation abgeschlossen ist, löschen Sie `CArchive`, `CSocketFile` und `CSocket`\-Objekte.  Der `SOCKET` Datentyp wird im Artikel [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md) beschrieben.  
  
 Wenn Sie `CArchive` mit `CSocketFile` und `CSocket` verwenden, treten unter Umständen eine Situation an, in der `CSocket::Receive` eine Schleife \(durch `PumpMessages(FD_READ)`\) auf die angeforderte Menge von Bytes wartenden eingibt.  Dies ist, da Windows Sockets nur einen recv Aufruf pro FD\_READ\-Benachrichtigung gewähren, aber `CSocketFile` und `CSocket` können mehrere recv Aufrufe pro FD\_READ.  Wenn Sie ein FD\_READ abrufen, wenn keine zu lesen, gibt Daten, hängt die Anwendung.  Wenn Sie nie ein anderes FD\_READ abrufen, beendet die Anwendung auf, über dem Socket zu kommunizieren.  
  
 Sie können dieses Problem wie folgt auflösen.  In der `OnReceive`\-Methode der Socketklasse, Aufruf `CAsyncSocket::IOCtl(FIONREAD, ...)`, bevor Sie die `Serialize`\-Methode der Nachrichtenklasse aufrufen, wenn die erwarteten vom Socket gelesen werden Daten, die Größe eines TCP\-Paket überschreiten \(maximale Übertragungseinheit des Netzwerkmediums, normalerweise mindestens 1096 Bytes\).  Wenn die Größe der verfügbaren Daten weniger als benötigt wird, warten Sie auf alle empfangen werden nur Daten, und starten Sie dann den Lesevorgang.  
  
 Im folgenden Beispiel ist `m_dwExpected` die ungefähre Anzahl von Bytes, die der Benutzer erwartet, zu empfangen.  Es wird davon ausgegangen, dass Sie es an anderer Stelle im Code deklarieren.  
  
 [!CODE [NVC_MFCSocketThread#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSocketThread#4)]  
  
> [!NOTE]
>  Wenn Sie MFC\-Sockets in den sekundären Threads in einer statisch verknüpften MFC\-Anwendung verwenden, müssen Sie `AfxSocketInit` in jedem Thread aufrufen, der Sockets verwendet, um die Socketbibliotheken zu initialisieren.  Standardmäßig wird `AfxSocketInit` nur im primären Thread aufgerufen.  
  
 Weitere Informationen finden Sie unter [Windows Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets: Wie Sockets mit Archiven funktionieren](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets: Sequenz von Vorgängen](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets: Beispiel für Sockets mithilfe der Archive](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## Anforderungen  
 **Header:** afxsock.h  
  
## Siehe auch  
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket Class](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)