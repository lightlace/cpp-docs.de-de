---
title: "CAsyncSocket Class"
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
  - "CAsyncSocket"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "asynchronous Windows Sockets"
  - "CAsyncSocket class"
  - "Kommunikation [C++], Netzwerk"
  - "network communications"
  - "sockets [C++], Windows"
  - "Windows Sockets [C++], Asynchron"
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CAsyncSocket Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Windows Socket \- einen Endpunkt der Netzwerkkommunikation dar.  
  
## Syntax  
  
```  
class CAsyncSocket : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](../Topic/CAsyncSocket::CAsyncSocket.md)|Erstellt ein `CAsyncSocket`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md)|Akzeptiert eine Verbindung auf dem Socket.|  
|[CAsyncSocket::AsyncSelect](../Topic/CAsyncSocket::AsyncSelect.md)|Fordert Ereignisbenachrichtigung für den Socket.|  
|[CAsyncSocket::Attach](../Topic/CAsyncSocket::Attach.md)|Fügt ein Sockethandle zu einem `CAsyncSocket`\-Objekt.|  
|[CAsyncSocket::Bind](../Topic/CAsyncSocket::Bind.md)|Ordnet eine lokale Adresse mit dem Socket zu.|  
|[CAsyncSocket::Close](../Topic/CAsyncSocket::Close.md)|Schließt den Socket.|  
|[CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md)|Richtet eine Verbindung zu einem Peersocket ein.|  
|[CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)|Erstellt einen Socket.|  
|[CAsyncSocket::Detach](../Topic/CAsyncSocket::Detach.md)|Trennt ein Sockethandle von einem `CAsyncSocket`\-Objekt.|  
|[CAsyncSocket::FromHandle](../Topic/CAsyncSocket::FromHandle.md)|Gibt einen Zeiger auf ein Objekt zurück, `CAsyncSocket` ein Sockethandle zugewiesen.|  
|[CAsyncSocket::GetLastError](../Topic/CAsyncSocket::GetLastError.md)|Ruft den Fehler\-Status für den letzten Vorgang ab, der fehlgeschlagen ist.|  
|[CAsyncSocket::GetPeerName](../Topic/CAsyncSocket::GetPeerName.md)|Ruft die Adresse des Peersockets ab, an den der Socket verbunden ist.|  
|[CAsyncSocket::GetPeerNameEx](../Topic/CAsyncSocket::GetPeerNameEx.md)|Ruft die Adresse des Peersockets ab, an den der Socket verbunden ist \(Adressen der Handles IPv6\).|  
|[CAsyncSocket::GetSockName](../Topic/CAsyncSocket::GetSockName.md)|Ruft den lokalen Namen für einen Socket ab.|  
|[CAsyncSocket::GetSockNameEx](../Topic/CAsyncSocket::GetSockNameEx.md)|Ruft den lokalen Namen für einen Socket ab \(Adressen der Handles IPv6\).|  
|[CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)|Ruft eine Socketoption ab.|  
|[CAsyncSocket::IOCtl](../Topic/CAsyncSocket::IOCtl.md)|Steuert den Modus des Sockets.|  
|[CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md)|Richtet einen Socket ein, um auf eingehende Aufforderungen zum Aufbau einer Verbindung zu überwachen.|  
|[CAsyncSocket::Receive](../Topic/CAsyncSocket::Receive.md)|Empfängt Daten vom Socket.|  
|[CAsyncSocket::ReceiveFrom](../Topic/CAsyncSocket::ReceiveFrom.md)|Empfängt ein Datagramm und speichert die Quelladresse.|  
|[CAsyncSocket::ReceiveFromEx](../Topic/CAsyncSocket::ReceiveFromEx.md)|Empfängt ein Datagramm und speichert die Quelladresse \(Adressen der Handles IPv6\).|  
|[CAsyncSocket::Send](../Topic/CAsyncSocket::Send.md)|Sendet Daten zu verbundenen Socket.|  
|[CAsyncSocket::SendTo](../Topic/CAsyncSocket::SendTo.md)|Sendet Daten einem bestimmten Ziel.|  
|[CAsyncSocket::SendToEx](../Topic/CAsyncSocket::SendToEx.md)|Sendet Daten einem bestimmten Ziel \(Adressen der Handles IPv6\).|  
|[CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)|Legt eine Socketoption fest.|  
|[CAsyncSocket::ShutDown](../Topic/CAsyncSocket::ShutDown.md)|Deaktiviert **Send** und\/oder **Receive** Aufrufe an den Socket.|  
|[CASyncSocket::Socket](../Topic/CASyncSocket::Socket.md)|Ordnet ein Sockethandle zu.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](../Topic/CAsyncSocket::OnAccept.md)|Benachrichtigt einen überwachenden Socket, dass er während Aufforderungen zum Aufbau einer Verbindung akzeptieren kann, indem er **Annehmen** aufruft.|  
|[CAsyncSocket::OnClose](../Topic/CAsyncSocket::OnClose.md)|Benachrichtigt einen Socket, dass der Socket, der mit ihm verbunden wird, geschlossen hat.|  
|[CAsyncSocket::OnConnect](../Topic/CAsyncSocket::OnConnect.md)|Benachrichtigt eine Steckverbindung, dass der Verbindungsversuch abgeschlossen ist, ob erfolgreich oder im Fehler.|  
|[CAsyncSocket::OnOutOfBandData](../Topic/CAsyncSocket::OnOutOfBandData.md)|Benachrichtigt einen empfangenden Socket, dass es auf die gibt dem Socket gelesen werden Out\-of\-Band\-Daten, normalerweise eine dringende Meldung.|  
|[CAsyncSocket::OnReceive](../Topic/CAsyncSocket::OnReceive.md)|Benachrichtigt einen überwachenden Socket, dass sie die mit gibt abgerufen werden Daten, **Receive** aufruft.|  
|[CAsyncSocket::OnSend](../Topic/CAsyncSocket::OnSend.md)|Benachrichtigt einen Socket, dass er Daten senden kann, indem er **Send** aufruft.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncSocket::operator \=](../Topic/CAsyncSocket::operator%20=.md)|Weist einen neuen Wert zu einem `CAsyncSocket`\-Objekt zu.|  
|[CAsyncSocket::operator SOCKET](../Topic/CAsyncSocket::operator%20SOCKET.md)|Verwenden Sie diesen Operator, um das **SOCKET** Handle des `CAsyncSocket`\-Objekts abzurufen.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAsyncSocket::m\_hSocket](../Topic/CAsyncSocket::m_hSocket.md)|Gibt das **SOCKET** Handle an, das diesem Objekt `CAsyncSocket` angefügt wird.|  
  
## Hinweise  
 `CAsyncSocket`\-Klasse kapselt die Windows Socket\-Funktionen APIs und stellt eine objektorientierte Abstraktion für Programmierer bereit, die Windows Sockets in Verbindung mit MFC verwenden möchten.  
  
 Diese Klasse basiert auf der Annahme, dass Sie Netzwerkkommunikationen verstehen.  Sie sind für das Behandelnblockieren, die Bytereihenfolgenunterschiede und die Konvertierungen zwischen Unicode und Zeichenfolgen mit Mehrbyte\-Zeichensätzen \(MBCS\) zuständig.  Wenn Sie eine zweckmäßigere Schnittstelle soll, die diese Probleme für Sie verwaltet werden, finden Sie unter [CSocket](../../mfc/reference/csocket-class.md)\-Klasse.  
  
 So fügen Sie ein Objekt `CAsyncSocket` verwenden, ihren Konstruktor aufrufen, die [Erstellen Sie](../Topic/CAsyncSocket::Create.md)\-Funktion aufzurufen, um das zugrunde liegende Sockethandle \(Typ `SOCKET`\), außer auf akzeptierte Sockets zu erstellen.  Für einen Serversocket rufen Sie die [Lauschen Sie](../Topic/CAsyncSocket::Listen.md)\-Memberfunktion auf, und für einen Clientsocket rufen Sie die [Schließen Sie an](../Topic/CAsyncSocket::Connect.md)\-Memberfunktion auf.  Der Serversocket sollte die [Übernehmen Sie](../Topic/CAsyncSocket::Accept.md)\-Funktion nach Empfang einer Aufforderung zum Aufbau einer Verbindung aufrufen.  Verwenden Sie die übrigen `CAsyncSocket`\-Funktionen, um die Kommunikation zwischen Sockets durchzuführen.  Nach Abschluss zerstören Sie das `CAsyncSocket`\-Objekt, wenn es auf dem Heap erstellt wurde, der Destruktor wird automatisch die [Schließen Sie](../Topic/CAsyncSocket::Close.md)\-Funktion auf.  Der `SOCKET` Datentyp wird im Artikel [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md) beschrieben.  
  
> [!NOTE]
>  Wenn Sie MFC\-Sockets in den sekundären Threads in einer statisch verknüpften MFC\-Anwendung verwenden, müssen Sie `AfxSocketInit` in jedem Thread aufrufen, der Sockets verwendet, um die Socketbibliotheken zu initialisieren.  Standardmäßig wird `AfxSocketInit` nur im primären Thread aufgerufen.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden der Klasse CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) und verwandte Artikel. sowie [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## Anforderungen  
 **Header:**  afxsock.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)