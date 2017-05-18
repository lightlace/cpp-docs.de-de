---
title: CAsyncSocket-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncSocket
- AFXSOCK/CAsyncSocket
- AFXSOCK/CAsyncSocket::CAsyncSocket
- AFXSOCK/CAsyncSocket::Accept
- AFXSOCK/CAsyncSocket::AsyncSelect
- AFXSOCK/CAsyncSocket::Attach
- AFXSOCK/CAsyncSocket::Bind
- AFXSOCK/CAsyncSocket::Close
- AFXSOCK/CAsyncSocket::Connect
- AFXSOCK/CAsyncSocket::Create
- AFXSOCK/CAsyncSocket::Detach
- AFXSOCK/CAsyncSocket::FromHandle
- AFXSOCK/CAsyncSocket::GetLastError
- AFXSOCK/CAsyncSocket::GetPeerName
- AFXSOCK/CAsyncSocket::GetPeerNameEx
- AFXSOCK/CAsyncSocket::GetSockName
- AFXSOCK/CAsyncSocket::GetSockNameEx
- AFXSOCK/CAsyncSocket::GetSockOpt
- AFXSOCK/CAsyncSocket::IOCtl
- AFXSOCK/CAsyncSocket::Listen
- AFXSOCK/CAsyncSocket::Receive
- AFXSOCK/CAsyncSocket::ReceiveFrom
- AFXSOCK/CAsyncSocket::ReceiveFromEx
- AFXSOCK/CAsyncSocket::Send
- AFXSOCK/CAsyncSocket::SendTo
- AFXSOCK/CAsyncSocket::SendToEx
- AFXSOCK/CAsyncSocket::SetSockOpt
- AFXSOCK/CAsyncSocket::ShutDown
- AFXSOCK/CASyncSocket::Socket
- AFXSOCK/CAsyncSocket::OnAccept
- AFXSOCK/CAsyncSocket::OnClose
- AFXSOCK/CAsyncSocket::OnConnect
- AFXSOCK/CAsyncSocket::OnOutOfBandData
- AFXSOCK/CAsyncSocket::OnReceive
- AFXSOCK/CAsyncSocket::OnSend
- AFXSOCK/CAsyncSocket::m_hSocket
dev_langs:
- C++
helpviewer_keywords:
- network communications
- asynchronous Windows Sockets
- CAsyncSocket class
- Windows Sockets [C++], asynchronous
- communications [C++], network
- sockets [C++], Windows
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7a175fc12146d98becc5d06f80e975df5b5a008
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="casyncsocket-class"></a>CAsyncSocket-Klasse
Stellt einen Windows Socket dar – ein Endpunkt der Netzwerkkommunikation.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAsyncSocket : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Erstellt ein `CAsyncSocket`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::Accept](#accept)|Akzeptiert eine Verbindung für den Socket.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|Benachrichtigung bei Anfragen für den Socket.|  
|[CAsyncSocket::Attach](#attach)|Fügt ein Sockethandle für ein `CAsyncSocket` Objekt.|  
|[CAsyncSocket::Bind](#bind)|Ordnet eine lokale Adresse den Socket.|  
|[CAsyncSocket::Close](#close)|Schließt den Socket.|  
|[CAsyncSocket:: Connect](#connect)|Stellt eine Verbindung mit einem Peer-Socket.|  
|[CAsyncSocket::Create](#create)|Ein Socket erstellt.|  
|[CAsyncSocket::Detach](#detach)|Trennt eine Socket-Handle aus einem `CAsyncSocket` Objekt.|  
|[CAsyncSocket::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CAsyncSocket` -Objekt, ein Socket-Handle.|  
|[CAsyncSocket::GetLastError](#getlasterror)|Ruft den Fehlerstatus für den letzten fehlgeschlagenen Vorgang ab.|  
|[CAsyncSocket::GetPeerName](#getpeername)|Ruft die Adresse des Peer-Sockets, mit dem der Socket verbunden ist.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Ruft die Adresse für den Peer-Socket, der Socket verbunden ist (Handles IPv6-Adressen) ist.|  
|[CAsyncSocket::GetSockName](#getsockname)|Ruft den lokalen Namen für einen Socket.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Ruft den lokalen Namen für einen Socket (Handles IPv6-Adressen).|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|Ruft einen Socket-Option ab.|  
|[CAsyncSocket::IOCtl](#ioctl)|Steuert den Modus des Sockets.|  
|[CAsyncSocket:: Listen](#listen)|Stellt ein Socket zum Lauschen auf eingehende Verbindungsanfragen her.|  
|[CAsyncSocket::Receive](#receive)|Empfängt Daten von den Socket.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Empfängt ein Datagramm und speichert die Quelladresse.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Empfängt ein Datagramm und speichert die Quelladresse (Handles IPv6-Adressen).|  
|[CAsyncSocket::Send](#send)|Sendet Daten an einen verbundenen Socket.|  
|[Einsatz](#sendto)|Sendet Daten an ein bestimmtes Ziel.|  
|[CAsyncSocket::SendToEx](#sendtoex)|Sendet Daten an ein bestimmtes Ziel (Handles IPv6-Adressen).|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|Wird eine Socketoption.|  
|[CAsyncSocket::ShutDown](#shutdown)|Deaktiviert die **senden** und/oder **empfangen** Ruft für den Socket.|  
|[CASyncSocket::Socket](#socket)|Reserviert ein Sockethandle.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|Benachrichtigt ein Abhörsocket, der es ausstehende verbindungsanforderungen, durch Aufrufen von akzeptieren kann **annehmen**.|  
|[CAsyncSocket::OnClose](#onclose)|Benachrichtigt ein Socket, den der Socket verbunden geschlossen wurde.|  
|[CAsyncSocket::OnConnect](#onconnect)|Benachrichtigt einem verbundenen Socket, dass der Verbindungsversuch abgeschlossen ist, gibt an, ob erfolgreich oder fehlerhaft ist.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Benachrichtigt einem empfangenden Socket über Out-of-Band-Daten für den Socket, in der Regel eine dringende Nachricht gelesen werden.|  
|[CAsyncSocket::OnReceive](#onreceive)|Benachrichtigt einen Abhörsocket, dass Daten durch Aufrufen von abgerufen werden sollen **empfangen**.|  
|[CAsyncSocket::OnSend](#onsend)|Benachrichtigt einem Socket, dass er Daten, durch Aufrufen von senden kann **senden**.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|Weist einen neuen Wert zu einem `CAsyncSocket` Objekt.|  
|[CAsyncSocket::operator SOCKET](#operator_socket)|Verwenden Sie diesen Operator zum Abrufen der **SOCKET** Handles aus dem `CAsyncSocket` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|Gibt die **SOCKET** Handle beigefügten `CAsyncSocket` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `CAsyncSocket` kapselt die Windows Socket-Funktionen-API bietet eine Abstraktion einer objektorientierten für Programmierer, die Windows-Sockets in Verbindung mit MFC verwendet werden soll.  
  
 Diese Klasse basiert auf der Annahme, dass Sie wissen, dass die Netzwerkkommunikation. Sie sind verantwortlich für die Behandlung blockieren, Byte-Reihenfolge unterschieden und Konvertierungen zwischen Unicode- und Mehrbyte-Zeichensätzen (MBCS)-Zeichenfolgen festgelegt. Eine weitere praktische Schnittstelle, die diese Probleme für Sie verwaltet, finden Sie unter Klasse [CSocket](../../mfc/reference/csocket-class.md).  
  
 Verwenden einer `CAsyncSocket` Objekt, dessen Konstruktor aufrufen rufen Sie dann die [erstellen](#create) -Funktion zum Erstellen der zugrunde liegenden Socket-Handle (Typ `SOCKET`), außer für akzeptierte Sockets. Für einen Server-Socket-Aufruf der [Überwachen](#listen) Member-Funktion, und für einen Client-Socket-Aufruf der [verbinden](#connect) Member-Funktion. Das Server-Socket aufrufen sollte der [annehmen](#accept) Funktion nach Empfang einer verbindungsanforderung. Verwenden Sie die verbleibenden `CAsyncSocket` Funktionen für die Kommunikation zwischen Sockets ausführen. Löschen Sie nach Abschluss der `CAsyncSocket` Objekt, wenn es auf dem Heap erstellt wurde, ruft der Destruktor automatisch die [schließen](#close) Funktion. Die `SOCKET` -Datentyp wird in diesem Artikel beschrieben [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch gebunden mit MFC_Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jedem Thread, die Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. In der Standardeinstellung `AfxSocketInit` wird nur im primären Thread aufgerufen.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: CAsyncSocket-Klasse mithilfe von](../../mfc/windows-sockets-using-class-casyncsocket.md) und verwandten Artikeln., sowie [API von Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CAsyncSocket`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Datei afxsock.h  
  
##  <a name="accept"></a>CAsyncSocket::Accept  
 Rufen Sie diese Memberfunktion zum Annehmen einer Verbindung auf einem Socket.  
  
```  
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,  
    SOCKADDR* lpSockAddr = NULL,  
    int* lpSockAddrLen = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rConnectedSocket`  
 Ein Verweis identifiziert einen neuen Socket, der für die Verbindung verfügbar ist.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) socket-Struktur, die die Adresse des verbindenden empfängt, wie im Netzwerk erkannt. Das genaue Format der der `lpSockAddr` -Argument wird bestimmt, von der Adressfamilie hergestellt, wenn der Socket erstellt wurde. Wenn `lpSockAddr` und/oder `lpSockAddrLen` gleich **NULL**, keine Informationen über die remote-Adresse der angenommenen Sockets zurückgegeben wird.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Adresse im `lpSockAddr` in Bytes. Die `lpSockAddrLen` ist ein Wert als Ergebnis Parameter: Es sollte die Menge des Speicherplatzes auf den anfänglich enthalten `lpSockAddr`; bei der Rückgabe die tatsächliche Länge (in Byte) der Adresse zurückgegeben enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist zu klein (kleiner als die Größe von einer [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **WSAEINPROGRESS** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAEINVAL** `Listen` wurde nicht vor accept aufgerufen.  
  
- **WSAEMFILE** die Warteschlange beim Einstieg in akzeptieren leer ist und keine Dateideskriptoren verfügbar sind.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP** referenzierte Socket ist kein Typ, der mit verbindungsorientierten Dienst unterstützt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und keine Verbindungen akzeptiert werden vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Routine extrahiert die erste Verbindung in der Warteschlange für ausstehende Verbindungen, erstellt einen neuen Socket mit den gleichen Eigenschaften wie diesem Socket und fügt es `rConnectedSocket`. Wenn keine ausstehenden Verbindungen in der Warteschlange vorhanden sind **annehmen** gibt NULL zurück und `GetLastError` gibt einen Fehler zurück. Der angenommene Socket ( *rConnectedSocket)* kann nicht verwendet werden, um weitere Verbindungen akzeptiert. Der ursprüngliche Socket bleibt geöffnet, und überwacht.  
  
 Das Argument `lpSockAddr` ist ein Ergebnisparameter, der die Adresse des verbundenen Sockets, eingetragen ist als der Kommunikation Ebene bezeichnet. **Übernehmen Sie** wird z. B. mit verbindungsorientierten Socket verwendet **SOCK_STREAM**.  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 Rufen Sie diese Memberfunktion zum Anfordern der Benachrichtigung für einen Socket.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- **FD_READ maskiert** Bereitschaft zum Lesen benachrichtigt werden soll.  
  
- **FD_WRITE** möchten Sie die Benachrichtigung erhalten, wenn Daten gelesen werden können.  
  
- **FD_OOB** Benachrichtigung über den Eingang von Out-of-Band-Daten empfangen soll.  
  
- **FD_ACCEPT** Benachrichtigung von eingehenden Verbindungen empfangen möchten.  
  
- **FD_CONNECT** Verbindungsergebnisse benachrichtigt werden soll.  
  
- **FD_CLOSE** möchten Sie die Benachrichtigung erhalten, wenn ein Socket vom Peer geschlossen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEINVAL** gibt an, dass mindestens eines der angegebenen Parameter ungültig ist.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um anzugeben, welche MFC-Benachrichtigung Rückruffunktionen für den Socket aufgerufen werden. `AsyncSelect`legt automatisch die Socketverbindung nicht blockierenden Modus fest. Weitere Informationen finden Sie im Artikel [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 Rufen Sie diese Memberfunktion Anfügen der `hSocket` handle für ein `CAsyncSocket` Objekt.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Parameter  
 `hSocket`  
 Enthält ein Handle für einen Socket.  
  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- **FD_READ maskiert** Bereitschaft zum Lesen benachrichtigt werden soll.  
  
- **FD_WRITE** möchten Sie die Benachrichtigung erhalten, wenn Daten gelesen werden können.  
  
- **FD_OOB** Benachrichtigung über den Eingang von Out-of-Band-Daten empfangen soll.  
  
- **FD_ACCEPT** Benachrichtigung von eingehenden Verbindungen empfangen möchten.  
  
- **FD_CONNECT** Verbindungsergebnisse benachrichtigt werden soll.  
  
- **FD_CLOSE** möchten Sie die Benachrichtigung erhalten, wenn ein Socket vom Peer geschlossen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich null, wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Die **SOCKET** Handle wird in des Objekts gespeichert [M_hSocket](#m_hsocket) -Datenmember.  
  
##  <a name="bind"></a>CAsyncSocket::Bind  
 Rufen Sie diese Memberfunktion um den Socket eine lokale Adresse zuzuordnen.  
  
```  
BOOL Bind(
    UINT nSocketPort,  
    LPCTSTR lpszSocketAddress = NULL);

 
BOOL Bind (
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Parameter  
 `nSocketPort`  
 Der Port, der die Socket-Anwendung angibt.  
  
 `lpszSocketAddress`  
 Die Netzwerkadresse einer gepunkteten Zahl z. B. "128.56.22.8". Übergeben der **NULL** Zeichenfolge für die dieser Parameter gibt die **CAsyncSocket** Instanz Clientaktivität an allen Netzwerkschnittstellen überwachen soll.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur, die Adresse enthält, die diesem Socket zuweisen.  
  
 `nSockAddrLen`  
 Die Länge der Adresse im `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEADDRINUSE** die angegebene Adresse wird bereits verwendet. (Siehe die **SO_REUSEADDR** Socketoption unter [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** der `nSockAddrLen` Argument ist zu klein (kleiner als die Größe von einer [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **WSAEINPROGRESS** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **** Die angegebenen Adressfamilie wird dieser Port nicht unterstützt.  
  
- **WSAEINVAL** der Socket ist bereits an eine Adresse gebunden.  
  
- `WSAENOBUFS`Nicht genügend Puffer verfügbar, zu viele Verbindungen.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Diese Routine wird auf einem nicht verbundenen Datagramm oder Streamsocket, vor dem nachfolgenden **verbinden** oder `Listen` aufrufen. Bevor er Verbindungsanfragen annehmen kann, ein Abhörsocket Server muss auswählen eine Portnummer und als bekannte an Windows Sockets durch Aufrufen von **binden**. **Binden Sie** richtet die lokale Zuordnung (Adresse/Port-Nummer) des Sockets durch einen unbenannten Socket einen lokalen Namen zuweisen.  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 Erstellt ein leeres Socketobjekt.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie seine **erstellen** Member-Funktion zum Erstellen der **SOCKET** Daten strukturieren und seine Adresse binden. (Auf dem Server eine Windows Sockets-Kommunikation, beim Erstellen der Abhörsocket ein Socket für die Verwendung in der **annehmen** aufrufen, rufen Sie **erstellen** für diesen Socket.)  
  
##  <a name="close"></a>CAsyncSocket::Close  
 Schließt den Socket.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt die Socket-Deskriptor frei, sodass Weitere Verweise mit dem Fehler fehl **WSAENOTSOCK**. Ist dies der letzte Verweis auf den zugrunde liegenden Socket, werden die zugehörigen Namensinformationen und die Daten in der Warteschlange verworfen. Das Socketobjekt Destruktor ruft **schließen** für Sie.  
  
 Für `CAsyncSocket`, jedoch nicht für `CSocket`, die Semantik der **schließen** sind von den Socketoptionen betroffen **SO_LINGER** und **SO_DONTLINGER**. Weitere Informationen finden Sie unter Memberfunktion `GetSockOpt`.  
  
##  <a name="connect"></a>CAsyncSocket:: Connect  
 Rufen Sie diese Memberfunktion zum Herstellen einer Verbindung mit einem nicht verbundenen Stream oder einem Datagrammsocket.  
  
```  
BOOL Connect(
    LPCTSTR lpszHostAddress,  
    UINT nHostPort);

 
BOOL Connect(
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszHostAddress`  
 Die Netzwerkadresse des Sockets, mit denen dieses Objekt verbunden ist: den Namen eines Computers, z. B. "ftp.microsoft.com", oder einer wie z. B. "128.56.22.8".  
  
 `nHostPort`  
 Der Port, der die Socket-Anwendung angibt.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die die Adresse des verbundenen Sockets enthält.  
  
 `nSockAddrLen`  
 Die Länge der Adresse im `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Wenn dies bedeutet, dass der Fehlercode **WSAEWOULDBLOCK**, und die überschreibbare Rückrufe von der Anwendung verwendet wird, empfängt die Anwendung eine `OnConnect` angezeigt, wenn der Verbindungsvorgang abgeschlossen wurde. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEADDRINUSE** die angegebene Adresse wird bereits verwendet.  
  
- **WSAEINPROGRESS** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.  
  
- **STARK** der Verbindungsversuch wurde zurückgewiesen.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAEFAULT** der `nSockAddrLen` Argument ist falsch.  
  
- **WSAEINVAL** ungültige Host-Adresse.  
  
- **WSAEISCONN** der Socket ist bereits verbunden.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- **WSAENETUNREACH** im Netzwerk nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar. Der Socket kann nicht verbunden werden.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAETIMEDOUT** Zeitlimit verbinden, ohne eine Verbindung herzustellen versuchen.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und die Verbindung nicht sofort abgeschlossen werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Socket aufgehoben wird, eindeutige Werte für die lokale Zuordnung vom System zugewiesen werden und der Socket ist als markiert gebunden. Beachten Sie, wenn das Adressfeld die Struktur ist Nullen, **verbinden**&0; (null) zurück. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die `GetLastError` -Memberfunktion.  
  
 Für Streamsockets (Typ **SOCK_STREAM**), wird eine aktive Verbindung mit dem fremden Host initiiert. Wenn der Socket-Aufruf erfolgreich abgeschlossen wurde, ist der Socket zum Senden/Empfangen von Daten bereit.  
  
 Für einen Datagrammsocket (Typ **SOCK_DGRAM**), ein Standardziel festgelegt ist, wird für nachfolgende verwendet werden **senden** und **empfangen** aufrufen.  
  
##  <a name="create"></a>CAsyncSocket::Create  
 Rufen Sie die **erstellen** Member-Funktion nach dem Konstruieren ein Socketobjekt, um den Windows-Socket erstellen und anfügen.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nSocketPort`  
 Ein well-known-Port mit der Socket oder 0 verwendet werden soll, wenn Sie Windows-Sockets auf einen Port auswählen möchten.  
  
 `nSocketType`  
 **SOCK_STREAM** oder **SOCK_DGRAM**.  
  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- **FD_READ maskiert** Bereitschaft zum Lesen benachrichtigt werden soll.  
  
- **FD_WRITE** Bereitschaft zum Schreiben benachrichtigt werden soll.  
  
- **FD_OOB** Benachrichtigung über den Eingang von Out-of-Band-Daten empfangen soll.  
  
- **FD_ACCEPT** Benachrichtigung von eingehenden Verbindungen empfangen möchten.  
  
- **FD_CONNECT** vervollständigte Verbindungszeichenfolge benachrichtigt werden soll.  
  
- **FD_CLOSE** Socket Closure benachrichtigt werden soll.  
  
 *lpszSockAddress*  
 Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets, eine gepunktete Zahl z. B. "128.56.22.8" enthält. Übergeben der **NULL** Zeichenfolge für die dieser Parameter gibt die **CAsyncSocket** Instanz Clientaktivität an allen Netzwerkschnittstellen überwachen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **** Die angegebenen Adressfamilie wird nicht unterstützt.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar. Der Socket kann nicht erstellt werden.  
  
- **WSAEPROTONOSUPPORT** der angegebene Port wird nicht unterstützt.  
  
- **WSAEPROTOTYPE** der angegebene Port ist der falsche Typ für diesen Socket.  
  
- **WSAESOCKTNOSUPPORT** der angegebenen Sockettyp wird in dieser Adressfamilie nicht unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** Aufrufe [Socket](#socket) und bei Erfolg ruft [binden](#bind) beim Binden des Sockets an die angegebene Adresse. Die folgenden Sockettypen werden unterstützt:  
  
- **SOCK_STREAM** sequenziert, bietet zuverlässige Vollduplex, verbindungsbasiertes Bytestreams. Verwendet das Protokoll TCP (Transmission Control) für die Internet-Adressfamilie.  
  
- **SOCK_DGRAM** Datagramme, die verbindungsloses und nicht zuverlässiges Pakete eine feste (normalerweise klein), maximale Länge werden unterstützt. Verwendet das User Datagram Protocol (UDP) für die Internet-Adressfamilie.  
  
    > [!NOTE]
    >  Die **annehmen** Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Sie müssen dieses Objekt erstellen, vor dem Aufruf von **annehmen**. Beachten Sie, dass, wenn dieses Socketobjekt des Bereichs an, die Verbindung geschlossen wird. Rufen Sie **erstellen** für dieses neue Socketobjekt.  
  
> [!IMPORTANT]
> **Erstellen Sie** ist **nicht** threadsicher.  Wenn Sie, es in einer Umgebung mit mehreren Threads aufrufen, könnten sie gleichzeitig von verschiedenen Threads aufgerufen werden, achten Sie darauf, dass jedem Aufruf einen Mutex oder andere Synchronisierungssperre geschützt wird.  
  
 Weitere Informationen zu Stream und Datagram Sockets, finden Sie in den Artikeln [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md) und [Windows Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md) und [API von Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 Rufen Sie diese Memberfunktion zum Trennen der **SOCKET** in behandelt die `m_hSocket` Datenmember aus der `CAsyncSocket` Objekt, und legen `m_hSocket` auf **NULL**.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>CAsyncSocket::FromHandle  
 Gibt einen Zeiger auf ein `CAsyncSocket` Objekt.  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parameter  
 `hSocket`  
 Enthält ein Handle für einen Socket.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CAsyncSocket` -Objekt, oder **NULL** ist keine `CAsyncSocket` Objekt angefügt, um `hSocket`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein **SOCKET** zu behandeln, wenn eine `CAsyncSocket` Objekt ist nicht auf das Handle verknüpft, die Memberfunktion gibt **NULL**.  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 Rufen Sie diese Memberfunktion um den Fehlerstatus für den letzten Vorgang zu erhalten, die nicht an.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt an, der Fehlercode für den letzten Windows Sockets-API-Routine, die von diesem Thread ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine bestimmten Member-Funktion gibt an, dass ein Fehler aufgetreten ist, `GetLastError` aufgerufen werden, um den entsprechenden Fehlercode abzurufen. Die einzelnen Member-Funktion Beschreibungen eine Liste der entsprechenden Fehlercodes angezeigt.  
  
 Weitere Informationen zu den Fehlercodes finden Sie unter [API von Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="getpeername"></a>CAsyncSocket::GetPeerName  
 Rufen Sie diese Memberfunktion erhalten die Adresse des Peer-Sockets, mit dem dieser Socket verbunden ist.  
  
```  
BOOL GetPeerName(
    CString& rPeerAddress,  
    UINT& rPeerPort);

 
BOOL GetPeerName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Parameter  
 `rPeerAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rPeerPort`  
 Ein Verweis auf eine **UINT** speichert einen Port.  
  
 `lpSockAddr`  
 Ein Zeiger auf die [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die den Namen des Peer-Socket empfängt.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Adresse im `lpSockAddr` in Bytes. Bei der Rückgabe der `lpSockAddrLen` -Argument enthält die tatsächliche Größe des `lpSockAddr` in Bytes zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **WSAEINPROGRESS** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAENOTCONN** der Socket ist nicht verbunden.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::GetPeerNameEx](#getpeernameex).  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 Rufen Sie diese Memberfunktion erhalten die Adresse für den Peer-Socket, zu dem dieser Socket verbunden ist (Handles IPv6-Adressen) ist.  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>Parameter  
 `rPeerAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rPeerPort`  
 Ein Verweis auf eine **UINT** speichert einen Port.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **WSAEINPROGRESS** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAENOTCONN** der Socket ist nicht verbunden.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist identisch mit [CAsyncSocket::GetPeerName](#getpeername) mit dem Unterschied, dass sie IPv6 behandelt Adressen als auch ältere Protokolle.  
  
##  <a name="getsockname"></a>CAsyncSocket::GetSockName  
 Rufen Sie diese Memberfunktion zum Abrufen des lokalen Namens für einen Socket.  
  
```  
BOOL GetSockName(
    CString& rSocketAddress,  
    UINT& rSocketPort);

 
BOOL GetSockName(
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen);
```  
  
### <a name="parameters"></a>Parameter  
 `rSocketAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rSocketPort`  
 Ein Verweis auf eine **UINT** speichert einen Port.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die die Adresse des Sockets empfängt.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Adresse im `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEINVAL** der Socket nicht mit einer Adresse gebunden wurde **binden**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf ist besonders nützlich, wenn eine **verbinden** aufgerufen wurde ohne einen **binden** zuerst dieser Aufruf stellt die einzige Möglichkeit, die mit dem können Sie bestimmen, lokale Zuordnung, die vom System festgelegt wurde.  
  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 Rufen Sie diese Memberfunktion zum Abrufen des lokalen Namens für einen Socket (Handles IPv6-Adressen).  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>Parameter  
 `rSocketAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rSocketPort`  
 Ein Verweis auf eine **UINT** speichert einen Port.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEINVAL** der Socket nicht mit einer Adresse gebunden wurde **binden**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf ist identisch mit [CAsyncSocket::GetSockName](#getsockname) mit dem Unterschied, dass sie IPv6 behandelt Adressen als auch ältere Protokolle.  
  
 Dieser Aufruf ist besonders nützlich, wenn eine **verbinden** aufgerufen wurde ohne einen **binden** zuerst dieser Aufruf stellt die einzige Möglichkeit, die mit dem können Sie bestimmen, lokale Zuordnung, die vom System festgelegt wurde.  
  
##  <a name="getsockopt"></a>CAsyncSocket::GetSockOpt  
 Rufen Sie diese Memberfunktion zum Abrufen einer Socket-Option.  
  
```  
BOOL GetSockOpt(
    int nOptionName,  
    void* lpOptionValue,  
    int* lpOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Parameter  
 `nOptionName`  
 Die Socketoption für die der Wert abgerufen werden soll.  
  
 `lpOptionValue`  
 Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option ist, zurückgegeben werden. Der Wert der ausgewählten Option wird im Puffer zurückgegeben `lpOptionValue`. Die ganze Zahl auf den `lpOptionLen` sollte die Größe dieses Puffers in Byte; ursprünglich enthalten und bei der Rückgabe wird es auf die Größe des zurückgegebenen Werts festgelegt werden. Für **SO_LINGER**, dabei handelt es sich um die Größe des ein `LINGER` -Struktur, die für alle anderen Optionen werden die Größe des ein **BOOL** oder `int`, abhängig von der Option. Finden Sie in der Liste der Optionen und deren Größen im Abschnitt "Hinweise".  
  
 `lpOptionLen`  
 Ein Zeiger auf die Größe der `lpOptionValue` -Puffers in Byte.  
  
 `nLevel`  
 Die Ebene, an der die Option definiert ist; Die einzigen unterstützte Ebenen sind **SOL_SOCKET** und **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Wenn eine Option nicht festgelegt wurde, mit `SetSockOpt`, dann `GetSockOpt` gibt den Standardwert für die Option zurück. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpOptionLen` Argument war ungültig.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAENOPROTOOPT** die Option ist unbekannt oder wird nicht unterstützt. Insbesondere **SO_BROADCAST** wird nicht unterstützt für Sockets vom Typ **SOCK_STREAM**, während **SO_ACCEPTCONN**, **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, und **SO_OOBINLINE** können nicht für Sockets vom Typ **SOCK_DGRAM**.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 `GetSockOpt`Ruft den aktuellen Wert für einen Socket-Option ein Socket eines beliebigen Typs, in jedem Zustand zugeordnet und speichert das Ergebnis in `lpOptionValue`. Die Optionen beeinflussen die Socketvorgänge, z. B. das routing von Paketen, Out-of-Band-Datenübertragung usw..  
  
 Die folgenden Optionen werden unterstützt, für die `GetSockOpt`. Der Typ gibt den Typ der Daten, die Gegenstand `lpOptionValue`. Die **TCP_NODELAY** Option verwendet Ebene **IPPROTO_TCP**; alle anderen Optionen verwenden, auf der **SOL_SOCKET**.  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Socket überwacht.|  
|**SO_BROADCAST**|**BOOL**|Socket für die Übermittlung von Nachrichten konfiguriert.|  
|**SO_DEBUG**|**BOOL**|Debuggen ist aktiviert.|  
|**SO_DONTLINGER**|**BOOL**|Wenn true, den **SO_LINGER** Option ist deaktiviert.|  
|**SO_DONTROUTE**|**BOOL**|Routing deaktiviert ist.|  
|**SO_ERROR**|`int`|Fehlerstatus abrufen und löschen.|  
|**SO_KEEPALIVE**|**BOOL**|Keep-Alives werden gesendet.|  
|**SO_LINGER**|**LINGER-Struktur**|Gibt die aktuellen Linger Optionen zurück.|  
|**SO_OOBINLINE**|**BOOL**|Out-of-Band-Daten wird im normalen Datenstream empfangen.|  
|**SO_RCVBUF**|`int`|Für die Größe des Puffers empfängt.|  
|**SO_REUSEADDR**|**BOOL**|Der Socket kann an eine Adresse gebunden werden, die bereits in Gebrauch ist.|  
|**SO_SNDBUF**|`int`|Puffergröße für sendet.|  
|**SO_TYPE**|`int`|Der Typ des Sockets (z. B. **SOCK_STREAM**).|  
|**TCP_NODELAY**|**BOOL**|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|  
  
 Nicht unterstützten Optionen der Berkeley Software Distribution (BSD) `GetSockOpt` sind:  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|Untergrenze zu empfangen.|  
|**SO_RCVTIMEO**|`int`|Timeout zu empfangen.|  
|**SO_SNDLOWAT**|`int`|Senden Sie die Untergrenze.|  
|**SO_SNDTIMEO**|`int`|Timeout des Sendevorgangs.|  
|**IP_OPTIONS**||Erhalten Sie Optionen im IP-Header.|  
|**TCP_MAXSEG**|`int`|Erhalten Sie maximale Segmentgröße TCP.|  
  
 Aufrufen von `GetSockOpt` mit einer nicht unterstützten Option führt zu einem Fehlercode von **WSAENOPROTOOPT** Rückgabe von `GetLastError`.  
  
##  <a name="ioctl"></a>CAsyncSocket::IOCtl  
 Rufen Sie diese Memberfunktion zum Steuern des Modus eines Sockets.  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>Parameter  
 `lCommand`  
 Der Befehl zum Ausführen auf dem Socket.  
  
 `lpArgument`  
 Ein Zeiger auf einen Parameter für `lCommand`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEINVAL** `lCommand` ist kein gültiger Befehl, oder `lpArgument` ist kein akzeptable Parameter für `lCommand`, oder der Befehl gilt nicht für den Typ der Socket angegeben.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Diese Routine kann auf einen Socket Status verwendet werden. Es dient zum Abrufen oder Abrufen von Betriebsparameter der Socket, unabhängig von der das Protokoll und die Kommunikation Subsystem zugeordnet. Die folgenden Befehle werden unterstützt:  
  
- **FIONBIO** aktivieren oder deaktivieren Sie nicht blockierenden Modus für den Socket. Die `lpArgument` Parameter verweist auf eine `DWORD`, also einen Wert ungleich NULL, wenn nicht blockierenden Modus aktiviert sein, und NULL, wenn es deaktiviert ist. Wenn `AsyncSelect` ausgegeben wurde auf einem Socket und ein Versuch, **IOCtl** für den Socket wieder blockierenden Modus festzulegen, schlägt mit **WSAEINVAL**. Richten Sie den Socket wieder in den blockierenden Modus und zu verhindern, dass die **WSAEINVAL** Fehler, eine Anwendung muss zunächst deaktivieren `AsyncSelect` durch Aufrufen von `AsyncSelect` mit der `lEvent` Parameter gleich 0 ist, rufen Sie dann **IOCtl**.  
  
- **FIONREAD** bestimmt die maximale Anzahl von Bytes, die mit einem gelesen werden kann **empfangen** aus diesem Socket aufrufen. Die `lpArgument` Parameter verweist auf eine `DWORD` in der **IOCtl** speichert das Ergebnis. Wenn diese Socket vom Typ **SOCK_STREAM**, **FIONREAD** gibt die Gesamtmenge der Daten, die gelesen werden können, in einer einzelnen **empfangen**; Dies ist normalerweise die gleiche wie die Gesamtmenge der Daten für den Socket in die Warteschlange. Wenn diese Socket vom Typ **SOCK_DGRAM**, **FIONREAD** gibt die Größe der das erste Datagramm in der Warteschlange für den Socket.  
  
- **SIOCATMARK** zu bestimmen, ob alle Out-of-Band-Daten gelesen wurden. Dies gilt nur für einen Socket vom Typ **SOCK_STREAM** die für den Inline-Empfang von Out-of-Band-Daten konfiguriert wurde ( **SO_OOBINLINE**). Wenn keine Out-of-Band-Daten gelesen werden wartet, gibt der Vorgang einen Wert ungleich NULL. Andernfalls wird 0 und dem nächsten **empfangen** oder `ReceiveFrom` ausgeführt wird, auf der Socket wird abgerufen, einige oder alle Daten vor der "Markierung" werden die Anwendung die **SIOCATMARK** Vorgang zu bestimmen, ob irgendwelche Daten verbleiben. Wenn die "dringenden" (Out-of-Band) Daten vor normalen Daten vorhanden sind, wird es in der Reihenfolge empfangen werden. (Beachten Sie, dass ein **empfangen** oder `ReceiveFrom` normale und Out-of-Band-Daten im selben Aufruf wird niemals mischen.) Die `lpArgument` Parameter verweist auf eine `DWORD` in der **IOCtl** speichert das Ergebnis.  
  
 Diese Funktion ist eine Teilmenge der **ioctl()** in Berkeley-Sockets verwendet. Es ist kein Befehl entspricht **FIOASYNC**, während **SIOCATMARK** ist der nur Socketebene-Befehl, der unterstützt wird.  
  
##  <a name="listen"></a>CAsyncSocket:: Listen  
 Rufen Sie diese Memberfunktion zum Lauschen auf eingehende Verbindungsanfragen an.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>Parameter  
 *nConnectionBacklog*  
 Die maximale Länge, zu der die Warteschlange der ausstehenden Verbindungen anwachsen kann. Gültige Bereich liegt zwischen 1 und 5.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEADDRINUSE** wurde versucht, die für die Überwachung einer Adresse verwendet.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden** oder ist bereits verbunden.  
  
- **WSAEISCONN** der Socket ist bereits verbunden.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP** referenzierte Socket ist nicht von einem Typ, unterstützt die `Listen` Vorgang.  
  
### <a name="remarks"></a>Hinweise  
 Um Verbindungen zu akzeptieren, wird zuerst der Socket mit erstellt **erstellen**, ein Backlog für eingehende Verbindungen mit angegeben wird `Listen`, und dann werden die Verbindungen mit akzeptiert **annehmen**. `Listen`gilt nur für Sockets, die Verbindungen, d. h. unterstützen die Typen **SOCK_STREAM**. Diesem Socket ist "passiven" Modus versetzen, in denen eingehende Verbindungen bestätigt und in der Warteschlange ausstehende Annahme durch den Prozess.  
  
 Diese Funktion wird meist von Servern (oder eine beliebige Anwendung, die zum Akzeptieren von Verbindungen), die möglicherweise mehr als eine Verbindungsanfrage zu einem Zeitpunkt: Wenn eine verbindungsanforderung mit der vollständigen Warteschlange eintrifft, empfängt der Client einen Fehler mit Angabe der **stark**.  
  
 `Listen`versucht, die weiterhin Rational funktionieren, wenn Sie keine verfügbaren Ports (Deskriptoren). Er akzeptiert Verbindungen, bis die Warteschlange leer ist. Wenn Ports verfügbar sind, zu einem späteren Aufruf `Listen` oder **annehmen** Warteschlange im aktuellen oder letzten "Backlog" möglichst aufgefüllt wird, und für eingehende Verbindungen Überwachung fort.  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 Enthält die **SOCKET** -handle für den Socket gekapselt, die von diesem `CAsyncSocket` Objekt.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 Aufgerufen, um ein Abhörsocket zu informieren, die sie ausstehende verbindungsanforderungen, durch Aufrufen akzeptieren kann der [annehmen](#accept) Member-Funktion.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Der letzte Fehler auf einem Socket. Die folgenden Fehlercodes gilt für die `OnAccept` Member-Funktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 Aufgerufen, um diesem Socket mitzuteilen, dass die verbundene Socket von einem Prozess geschlossen wird.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Der letzte Fehler auf einem Socket. Die folgenden Fehlercodes gelten für die `OnClose` Member-Funktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAECONNRESET** die Verbindung wurde von der Remoteseite zurückgesetzt.  
  
- **WSAECONNABORTED** die Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 Aufgerufen, um diese Verbindung Socket mitzuteilen, dass der Verbindungsversuch entweder erfolgreich oder Fehler abgeschlossen ist.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Der letzte Fehler auf einem Socket. Die folgenden Fehlercodes gelten für die `OnConnect` Member-Funktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAEADDRINUSE** die angegebene Adresse wird bereits verwendet.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.  
  
- **STARK** der Verbindungsversuch wurde absichtlich verweigert.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist falsch.  
  
- **WSAEINVAL** der Socket ist bereits an eine Adresse gebunden.  
  
- **WSAEISCONN** der Socket ist bereits verbunden.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- **WSAENETUNREACH** im Netzwerk nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar. Der Socket kann nicht verbunden werden.  
  
- **WSAENOTCONN** der Socket ist nicht verbunden.  
  
- **WSAENOTSOCK** Deskriptor ist eine Datei, die nicht von einem Socket.  
  
- **WSAETIMEDOUT** der Verbindungsversuch Timeout, ohne eine Verbindung herzustellen.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  In [CSocket](../../mfc/reference/csocket-class.md)die `OnConnect` -Benachrichtigungsfunktion wird nie aufgerufen. Für Verbindungen, rufen Sie einfach **verbinden**, die zurück, wenn die Verbindung hergestellt wird (entweder erfolgreich oder Fehler). Behandlung von Verbindung Benachrichtigungen ist ein Implementierungsdetail MFC.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAsyncSocket&#1;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 Vom Framework aufgerufen wird, den empfangenden Socket mitzuteilen, welche der sendende Socket Out-of-Band-Daten senden.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Der letzte Fehler auf einem Socket. Die folgenden Fehlercodes gelten für die `OnOutOfBandData` Member-Funktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Out-of-Band-Daten ist ein logisch unabhängigen Kanal, der jedes Paar von verbundenen Sockets des Typs zugeordnet ist **SOCK_STREAM**. Der Kanal wird in der Regel verwendet, um dringende Daten senden.  
  
 MFC unterstützt die Out-of-Band-Daten, aber die Benutzer der Klasse `CAsyncSocket` werden aus ihrer Verwendung abgeraten. Die einfacher ist, um einen zweiten Socket für die Weitergabe dieser Daten zu erstellen. Weitere Informationen über Out-of-Band-Daten finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 Aufgerufen, um diesem Socket zu benachrichtigen, dass Daten im Puffer, der durch Aufrufen von abgerufen werden kann der **empfangen** Member-Funktion.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Der letzte Fehler auf einem Socket. Die folgenden Fehlercodes gelten für die `OnReceive` Member-Funktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAsyncSocket&#2;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 Aufgerufen, um den Socket mitzuteilen, dass es jetzt Daten durch Aufrufen von senden kann die **senden** Member-Funktion.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Der letzte Fehler auf einem Socket. Die folgenden Fehlercodes gelten für die `OnSend` Member-Funktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAsyncSocket&3;](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>CAsyncSocket::operator =  
 Weist einen neuen Wert zu einem `CAsyncSocket` Objekt.  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Ein Verweis auf einen vorhandenen `CAsyncSocket` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Kopieren einer vorhandenen `CAsyncSocket` Objekt zu einem anderen `CAsyncSocket` Objekt.  
  
##  <a name="operator_socket"></a>CAsyncSocket::operator SOCKET  
 Verwenden Sie diesen Operator zum Abrufen der **SOCKET** Handles aus dem `CAsyncSocket` Objekt.  
  
```  
operator SOCKET() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle für die **SOCKET** Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Handle verwenden, Windows-APIs direkt aufrufen.  
  
##  <a name="receive"></a>CAsyncSocket::Receive  
 Rufen Sie diese Memberfunktion zum Empfangen von Daten von einem Socket.  
  
```  
virtual int Receive(
    void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer für die eingehenden Daten.  
  
 `nBufLen`  
 Die Länge des `lpBuf` in Bytes.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden bestimmt, indem der Socket-Optionen und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_PEEK** die eingehenden Daten einsehen. Die Daten in den Puffer kopiert werden jedoch nicht aus der Eingabewarteschlange entfernt.  
  
- **MSG_OOB** Out-of-Band-Daten verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, **empfangen** gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAENOTCONN** der Socket ist nicht verbunden.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket wurde heruntergefahren, nicht möglich ist, rufen Sie **empfangen** auf einem Socket nach `ShutDown` wurde mit aufgerufen `nHow` auf 0 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und **empfangen** Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** das Datagramm zu klein war zu groß für den angegebenen Puffer und wurde abgeschnitten.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist für verbundene Stream oder Datagrammsockets verwendet und wird verwendet, um eingehende Daten gelesen.  
  
 Für Sockets vom Typ **SOCK_STREAM**, wie viele Informationen, die derzeit verfügbaren bis zur Größe des Puffers angegeben zurückgegeben wird. Wenn der Socket für den Empfang von Inline-Out-of-Band-Daten konfiguriert wurde (Socketoption **SO_OOBINLINE**) und Out-of-Band-Daten ungelesene, nur Out-of-Band-Daten zurückgegeben werden. Kann die Anwendung anhand der **IOCtlSIOCATMARK** Option oder [OnOutOfBandData](#onoutofbanddata) zu bestimmen, ob alle mehr Out-of-Band-Daten bleibt gelesen werden.  
  
 Für Datagrammsockets werden Daten aus der erste Datagramm bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der angegebene Puffer ist, der Puffer voll ist, mit dem ersten Teil des Datagramms, die überzähligen Daten verloren, und **empfangen** gibt einen Wert von **SOCKET_ERROR** legen Sie mit dem Fehlercode auf **WSAEMSGSIZE**. Wenn keine eingehenden Daten verfügbar, an den Socket, der Wert sind **SOCKET_ERROR** wird zurückgegeben, mit dem Fehlercode **WSAEWOULDBLOCK**. Die [OnReceive](#onreceive) Callback-Funktion kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.  
  
 Wenn der Socket vom Typ **SOCK_STREAM** und die Remoteseite hat die Verbindung ordnungsgemäß heruntergefahren, ein **empfangen** mit 0 Byte empfangen sofort beendet wird. Wenn die Verbindung zurückgesetzt wurde, eine **empfangen** schlägt fehl mit Fehler **WSAECONNRESET**.  
  
 **Empfangen von** sollte nur einmal für jedes Mal aufgerufen werden [CAsyncSocket::OnReceive](#onreceive) aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="receivefrom"></a>CAsyncSocket::ReceiveFrom  
 Rufen Sie diese Memberfunktion ein Datagramm empfangen und zum Speichern der Quelladresse in der [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur oder im `rSocketAddress`.  
  
```  
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);

 
int ReceiveFrom(
    void* lpBuf,  
    int nBufLen,  
    SOCKADDR* lpSockAddr,  
    int* lpSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer für die eingehenden Daten.  
  
 `nBufLen`  
 Die Länge des `lpBuf` in Bytes.  
  
 `rSocketAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rSocketPort`  
 Ein Verweis auf eine **UINT** speichert einen Port.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur, die die Quelladresse bei der Rückgabe enthält.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Quelladresse in `lpSockAddr` in Bytes.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden bestimmt, indem der Socket-Optionen und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_PEEK** die eingehenden Daten einsehen. Die Daten in den Puffer kopiert werden jedoch nicht aus der Eingabewarteschlange entfernt.  
  
- **MSG_OOB** Out-of-Band-Daten verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `ReceiveFrom` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch Aufrufen von `GetLastError`. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument war ungültig: die `lpSockAddr` Puffer ist zu klein für die Peer-Adresse zugewiesen werden.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket wurde heruntergefahren, nicht möglich ist, rufen Sie `ReceiveFrom` auf einem Socket nach `ShutDown` wurde mit aufgerufen `nHow` auf 0 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und `ReceiveFrom` Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** das Datagramm zu klein war zu groß für den angegebenen Puffer und wurde abgeschnitten.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient zum Lesen von eingehender Daten auf einem Socket (möglicherweise verbunden) und die Adresse von dem die Daten gesendet wurden.  
  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::ReceiveFromEx](#receivefromex).  
  
 Für Sockets vom Typ **SOCK_STREAM**, wie viele Informationen, die derzeit verfügbaren bis zur Größe des Puffers angegeben zurückgegeben wird. Wenn der Socket für den Empfang von Inline-Out-of-Band-Daten konfiguriert wurde (Socketoption **SO_OOBINLINE**) und Out-of-Band-Daten ungelesene, nur Out-of-Band-Daten zurückgegeben werden. Kann die Anwendung anhand der **IOCtlSIOCATMARK** Option oder `OnOutOfBandData` zu bestimmen, ob alle mehr Out-of-Band-Daten bleibt gelesen werden. Die `lpSockAddr` und `lpSockAddrLen` Parameter werden ignoriert, für die **SOCK_STREAM** Sockets.  
  
 Für Datagrammsockets werden Daten aus der erste Datagramm bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der angegebene Puffer ist, der Puffer voll ist, mit dem ersten Teil der Nachricht, die überzähligen Daten verloren, und `ReceiveFrom` gibt einen Wert von **SOCKET_ERROR** legen Sie mit dem Fehlercode auf **WSAEMSGSIZE**.  
  
 Wenn `lpSockAddr` ungleich NULL ist, und der Socket ist vom Typ **SOCK_DGRAM**, die Netzwerkadresse des Sockets, die die Daten übertragen wird kopiert, auf die entsprechende [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur. Der Wert auf den `lpSockAddrLen` auf die Größe dieser Struktur initialisiert wird, und bei der Rückgabe an die tatsächliche Größe der gespeicherten Adresse geändert wird. Wenn keine eingehende Daten zu den Socket verfügbar ist die `ReceiveFrom` Aufruf wartet auf Daten eingehen, es sei denn, der Socket ist nicht blockierend. In diesem Fall wird ein Wert von **SOCKET_ERROR** wird zurückgegeben, mit dem Fehlercode **WSAEWOULDBLOCK**. Die `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.  
  
 Wenn der Socket vom Typ **SOCK_STREAM** und die Remoteseite hat die Verbindung ordnungsgemäß heruntergefahren, eine `ReceiveFrom` mit 0 Byte empfangen sofort beendet wird.  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 Rufen Sie diese Memberfunktion ein Datagramm empfangen und zum Speichern der Quelladresse in der [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur oder im `rSocketAddress` (handles IPv6-Adressen).  
  
```  
int ReceiveFromEx(
    void* lpBuf,  
    int nBufLen,  
    CString& rSocketAddress,  
    UINT& rSocketPort,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer für die eingehenden Daten.  
  
 `nBufLen`  
 Die Länge des `lpBuf` in Bytes.  
  
 `rSocketAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rSocketPort`  
 Ein Verweis auf eine **UINT** speichert einen Port.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden bestimmt, indem der Socket-Optionen und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_PEEK** die eingehenden Daten einsehen. Die Daten in den Puffer kopiert werden jedoch nicht aus der Eingabewarteschlange entfernt.  
  
- **MSG_OOB** Out-of-Band-Daten verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `ReceiveFromEx` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch Aufrufen von `GetLastError`. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument war ungültig: die `lpSockAddr` Puffer ist zu klein für die Peer-Adresse zugewiesen werden.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket wurde heruntergefahren, nicht möglich ist, rufen Sie `ReceiveFromEx` auf einem Socket nach `ShutDown` wurde mit aufgerufen `nHow` auf 0 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und `ReceiveFromEx` Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** das Datagramm zu klein war zu groß für den angegebenen Puffer und wurde abgeschnitten.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient zum Lesen von eingehender Daten auf einem Socket (möglicherweise verbunden) und die Adresse von dem die Daten gesendet wurden.  
  
 Diese Funktion ist identisch mit [CAsyncSocket::ReceiveFrom](#receivefrom) mit dem Unterschied, dass sie IPv6 behandelt Adressen als auch ältere Protokolle.  
  
 Für Sockets vom Typ **SOCK_STREAM**, wie viele Informationen, die derzeit verfügbaren bis zur Größe des Puffers angegeben zurückgegeben wird. Wenn der Socket für den Empfang von Inline-Out-of-Band-Daten konfiguriert wurde (Socketoption **SO_OOBINLINE**) und Out-of-Band-Daten ungelesene, nur Out-of-Band-Daten zurückgegeben werden. Kann die Anwendung anhand der **IOCtlSIOCATMARK** Option oder `OnOutOfBandData` zu bestimmen, ob alle mehr Out-of-Band-Daten bleibt gelesen werden. Die `lpSockAddr` und `lpSockAddrLen` Parameter werden ignoriert, für die **SOCK_STREAM** Sockets.  
  
 Für Datagrammsockets werden Daten aus der erste Datagramm bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der angegebene Puffer ist, der Puffer voll ist, mit dem ersten Teil der Nachricht, die überzähligen Daten verloren, und `ReceiveFromEx` gibt einen Wert von **SOCKET_ERROR** legen Sie mit dem Fehlercode auf **WSAEMSGSIZE**.  
  
 Wenn `lpSockAddr` ungleich NULL ist, und der Socket ist vom Typ **SOCK_DGRAM**, die Netzwerkadresse des Sockets, die die Daten übertragen wird kopiert, auf die entsprechende [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur. Der Wert auf den `lpSockAddrLen` auf die Größe dieser Struktur initialisiert wird, und bei der Rückgabe an die tatsächliche Größe der gespeicherten Adresse geändert wird. Wenn keine eingehende Daten zu den Socket verfügbar ist die `ReceiveFromEx` Aufruf wartet auf Daten eingehen, es sei denn, der Socket ist nicht blockierend. In diesem Fall wird ein Wert von **SOCKET_ERROR** wird zurückgegeben, mit dem Fehlercode **WSAEWOULDBLOCK**. Die `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.  
  
 Wenn der Socket vom Typ **SOCK_STREAM** und die Remoteseite hat die Verbindung ordnungsgemäß heruntergefahren, eine `ReceiveFromEx` mit 0 Byte empfangen sofort beendet wird.  
  
##  <a name="send"></a>CAsyncSocket::Send  
 Rufen Sie diese Memberfunktion zum Senden von Daten auf einem verbundenen Socket.  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer mit den Daten übertragen werden.  
  
 `nBufLen`  
 Die Länge der Daten im `lpBuf` in Bytes.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden bestimmt, indem der Socket-Optionen und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_DONTROUTE** gibt, die die Daten nicht weiterleiten soll. Ein Windows Sockets-Lieferanten können dieses Flag ignoriert.  
  
- **MSG_OOB** Senden von Out-of-Band-Daten ( **SOCK_STREAM** nur).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, **senden** gibt die Gesamtanzahl der Zeichen gesendet. (Beachten Sie, dass dies kleiner als die Zahl, `nBufLen`.) Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEACCES** die angeforderte Adresse ist eine broadcast-Adresse, aber das entsprechende Flag nicht festgelegt wurde.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEFAULT** der `lpBuf` Argument ist nicht in einem gültigen Teil des benutzeradressraums.  
  
- **WSAENETRESET** die Verbindung muss zurückgesetzt werden, da die Windows Sockets-Implementierung, die sie gelöscht.  
  
- `WSAENOBUFS`Die Windows Sockets-Implementierung eine Puffer-Deadlocks gemeldet.  
  
- **WSAENOTCONN** der Socket ist nicht verbunden.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket wurde heruntergefahren; es ist nicht möglich, rufen Sie **senden** auf einem Socket nach `ShutDown` wurde mit aufgerufen `nHow` auf 1 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und der angeforderte Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** der Socket ist vom Typ **SOCK_DGRAM**, und das Datagramm ist größer als die maximal von der Windows Sockets-Implementierung unterstützt werden.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 **Senden von** wird verwendet, um ausgehende Daten für verbundene Stream- oder Datagrammsocket Sockets geschrieben. Für Datagrammsockets, muss darauf geachtet werden nicht überschreiten die maximale Größe der IP-Paket von der zugrunde liegenden Subnetzen, die durch angegeben wird der **iMaxUdpDg** Element in der [WSADATA](../../mfc/reference/wsadata-structure.md) zurückgegebene Struktur `AfxSocketInit`. Wenn die Daten zu lang und automatisch über das zugrunde liegende Protokoll, den Fehler **WSAEMSGSIZE** wird zurückgegeben, über `GetLastError`, und keine Daten übertragen.  
  
 Beachten Sie, die für ein Datagramm den erfolgreichen Abschluss der socket eine **senden** bedeutet nicht, dass die Daten erfolgreich übermittelt wurden.  
  
 Auf `CAsyncSocket` Objekte des Typs **SOCK_STREAM**, die Anzahl der geschriebenen Bytes kann zwischen 1 und die angeforderte Länge, abhängig von der Verfügbarkeit der Puffer auf den lokalen und fremden Hosts sein.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAsyncSocket::OnSend](#onsend).  
  
##  <a name="sendto"></a>Einsatz  
 Rufen Sie diese Memberfunktion zum Senden von Daten an ein bestimmtes Ziel.  
  
```  
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);

 
int SendTo(
    const void* lpBuf,  
    int nBufLen,  
    const SOCKADDR* lpSockAddr,  
    int nSockAddrLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer mit den Daten übertragen werden.  
  
 `nBufLen`  
 Die Länge der Daten im `lpBuf` in Bytes.  
  
 `nHostPort`  
 Der Port, der die Socket-Anwendung angibt.  
  
 `lpszHostAddress`  
 Die Netzwerkadresse des Sockets, mit denen dieses Objekt verbunden ist: den Namen eines Computers, z. B. "ftp.microsoft.com", oder einer wie z. B. "128.56.22.8".  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden bestimmt, indem der Socket-Optionen und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_DONTROUTE** gibt, die die Daten nicht weiterleiten soll. Ein Windows Sockets-Lieferanten können dieses Flag ignoriert.  
  
- **MSG_OOB** Senden von Out-of-Band-Daten ( **SOCK_STREAM** nur).  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die die Adresse des Sockets Ziel enthält.  
  
 `nSockAddrLen`  
 Die Länge der Adresse im `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `SendTo` gibt die Gesamtanzahl der Zeichen gesendet. (Beachten Sie, dass dies kleiner als die Zahl, `nBufLen`.) Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEACCES** die angeforderte Adresse ist eine broadcast-Adresse, aber das entsprechende Flag nicht festgelegt wurde.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEFAULT** der `lpBuf` oder `lpSockAddr` Parameter sind nicht Teil des benutzeradressraums oder `lpSockAddr` Argument ist zu klein (kleiner als die Größe von einer [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **WSAEINVAL** der Hostname ist ungültig.  
  
- **WSAENETRESET** die Verbindung muss zurückgesetzt werden, da die Windows Sockets-Implementierung, die sie gelöscht.  
  
- `WSAENOBUFS`Die Windows Sockets-Implementierung eine Puffer-Deadlocks gemeldet.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket wurde heruntergefahren, nicht möglich ist, rufen Sie `SendTo` auf einem Socket nach `ShutDown` wurde mit aufgerufen `nHow` auf 1 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und der angeforderte Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** der Socket ist vom Typ **SOCK_DGRAM**, und das Datagramm ist größer als die maximal von der Windows Sockets-Implementierung unterstützt werden.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAENETUNREACH** im Netzwerk nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
### <a name="remarks"></a>Hinweise  
 `SendTo`auf Datagramm oder den Stream Sockets verwendet wird, und wird verwendet, um ausgehende Daten für einen Socket geschrieben. Für Datagrammsockets, muss darauf geachtet werden nicht überschreiten die maximale Größe der IP-Paket von der zugrunde liegenden Subnetzen, die durch angegeben wird der **iMaxUdpDg** Element in der [WSADATA](../../mfc/reference/wsadata-structure.md) Struktur ausgefüllt [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Wenn die Daten zu lang und automatisch über das zugrunde liegende Protokoll, den Fehler **WSAEMSGSIZE** zurückgegeben wird, und keine Daten übertragen.  
  
 Beachten Sie, dass der erfolgreiche Abschluss einer `SendTo` bedeutet nicht, dass die Daten erfolgreich übermittelt wurden.  
  
 `SendTo`wird nur verwendet, auf eine **SOCK_DGRAM** Socket ein Datagramm an einem bestimmten Socket identifizierten Senden der `lpSockAddr` Parameter.  
  
 Einen Broadcast gesendet (auf einem **SOCK_DGRAM** nur), die Adresse in der `lpSockAddr` Parameter sollten erstellt werden, die spezielle IP-Adresse **INADDR_BROADCAST** (definiert in der Windows Sockets-Headerdatei WINSOCK. (H) zusammen mit der gewünschten Portnummer. Oder, wenn die `lpszHostAddress` Parameter ist **NULL**, für die Übertragung der Socket konfiguriert ist. Es ist im Allgemeinen nicht empfehlenswert, für ein Datagramm broadcast, um die Größe nicht überschreiten, in denen Fragmentierung auftreten kann, d. h., dass der Datenteil das Datagramm (ausgenommen Header) 512 Byte nicht übersteigen darf.  
  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::SendToEx](#sendtoex).  
  
##  <a name="sendtoex"></a>CAsyncSocket::SendToEx  
 Rufen Sie diese Memberfunktion zum Senden von Daten an ein bestimmtes Ziel (Handles IPv6-Adressen).  
  
```  
int SendToEx(
    const void* lpBuf,  
    int nBufLen,  
    UINT nHostPort,  
    LPCTSTR lpszHostAddress = NULL,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer mit den Daten übertragen werden.  
  
 `nBufLen`  
 Die Länge der Daten im `lpBuf` in Bytes.  
  
 `nHostPort`  
 Der Port, der die Socket-Anwendung angibt.  
  
 `lpszHostAddress`  
 Die Netzwerkadresse des Sockets, mit denen dieses Objekt verbunden ist: den Namen eines Computers, z. B. "ftp.microsoft.com", oder einer wie z. B. "128.56.22.8".  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden bestimmt, indem der Socket-Optionen und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_DONTROUTE** gibt, die die Daten nicht weiterleiten soll. Ein Windows Sockets-Lieferanten können dieses Flag ignoriert.  
  
- **MSG_OOB** Senden von Out-of-Band-Daten ( **SOCK_STREAM** nur).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `SendToEx` gibt die Gesamtanzahl der Zeichen gesendet. (Beachten Sie, dass dies kleiner als die Zahl, `nBufLen`.) Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEACCES** die angeforderte Adresse ist eine broadcast-Adresse, aber das entsprechende Flag nicht festgelegt wurde.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEFAULT** der `lpBuf` oder `lpSockAddr` Parameter sind nicht Teil des benutzeradressraums oder `lpSockAddr` Argument ist zu klein (kleiner als die Größe von einer [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **WSAEINVAL** der Hostname ist ungültig.  
  
- **WSAENETRESET** die Verbindung muss zurückgesetzt werden, da die Windows Sockets-Implementierung, die sie gelöscht.  
  
- `WSAENOBUFS`Die Windows Sockets-Implementierung eine Puffer-Deadlocks gemeldet.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket wurde heruntergefahren, nicht möglich ist, rufen Sie `SendToEx` auf einem Socket nach `ShutDown` wurde mit aufgerufen `nHow` auf 1 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und der angeforderte Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** der Socket ist vom Typ **SOCK_DGRAM**, und das Datagramm ist größer als die maximal von der Windows Sockets-Implementierung unterstützt werden.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde abgebrochen, weil Timeout- oder anderer Fehler.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAENETUNREACH** im Netzwerk nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist identisch mit [Einsatz](#sendto) mit dem Unterschied, dass sie IPv6 behandelt Adressen als auch ältere Protokolle.  
  
 `SendToEx`auf Datagramm oder den Stream Sockets verwendet wird, und wird verwendet, um ausgehende Daten für einen Socket geschrieben. Für Datagrammsockets, muss darauf geachtet werden nicht überschreiten die maximale Größe der IP-Paket von der zugrunde liegenden Subnetzen, die durch angegeben wird der **iMaxUdpDg** Element in der [WSADATA](../../mfc/reference/wsadata-structure.md) Struktur ausgefüllt [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Wenn die Daten zu lang und automatisch über das zugrunde liegende Protokoll, den Fehler **WSAEMSGSIZE** zurückgegeben wird, und keine Daten übertragen.  
  
 Beachten Sie, dass der erfolgreiche Abschluss einer `SendToEx` bedeutet nicht, dass die Daten erfolgreich übermittelt wurden.  
  
 `SendToEx`wird nur verwendet, auf eine **SOCK_DGRAM** Socket ein Datagramm an einem bestimmten Socket identifizierten Senden der `lpSockAddr` Parameter.  
  
 Einen Broadcast gesendet (auf einem **SOCK_DGRAM** nur), die Adresse in der `lpSockAddr` Parameter sollten erstellt werden, die spezielle IP-Adresse **INADDR_BROADCAST** (definiert in der Windows Sockets-Headerdatei WINSOCK. (H) zusammen mit der gewünschten Portnummer. Oder, wenn die `lpszHostAddress` Parameter ist **NULL**, für die Übertragung der Socket konfiguriert ist. Es ist im Allgemeinen nicht empfehlenswert, für ein Datagramm broadcast, um die Größe nicht überschreiten, in denen Fragmentierung auftreten kann, d. h., dass der Datenteil das Datagramm (ausgenommen Header) 512 Byte nicht übersteigen darf.  
  
##  <a name="setsockopt"></a>CAsyncSocket::SetSockOpt  
 Rufen Sie diese Memberfunktion zum Festlegen einer Socketoption.  
  
```  
BOOL SetSockOpt(
    int nOptionName,  
    const void* lpOptionValue,  
    int nOptionLen,  
    int nLevel = SOL_SOCKET);
```  
  
### <a name="parameters"></a>Parameter  
 `nOptionName`  
 Die Socketoption für die der Wert festgelegt werden.  
  
 `lpOptionValue`  
 Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option bereitgestellt wird.  
  
 `nOptionLen`  
 Die Größe der `lpOptionValue` -Puffers in Byte.  
  
 `nLevel`  
 Die Ebene, an der die Option definiert ist; Die einzigen unterstützte Ebenen sind **SOL_SOCKET** und **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** `lpOptionValue` befindet sich nicht in einem gültigen Teil des Adressraums.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAEINVAL** `nLevel` ist ungültig, oder die Informationen in `lpOptionValue` ist ungültig.  
  
- **WSAENETRESET** Verbindung wurde abgebrochen, wenn **SO_KEEPALIVE** festgelegt ist.  
  
- **WSAENOPROTOOPT** die Option ist unbekannt oder wird nicht unterstützt. Insbesondere **SO_BROADCAST** wird nicht unterstützt für Sockets vom Typ **SOCK_STREAM**, während **SO_DONTLINGER**, **SO_KEEPALIVE**, **SO_LINGER**, und **SO_OOBINLINE** können nicht für Sockets vom Typ **SOCK_DGRAM**.  
  
- **WSAENOTCONN** Verbindung wurde zurückgesetzt, wenn **SO_KEEPALIVE** festgelegt ist.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 `SetSockOpt`Legt den aktuellen Wert für einen Socket-Option ein Socket eines beliebigen Typs, in den einzelnen Bundesstaaten zugeordnet. Obwohl Optionen auf mehreren Protokoll Ebenen vorhanden sein können, definiert dieser Spezifikation nur die Optionen, die sich auf der obersten "Socket" befinden. Die Optionen beeinflussen die Socketvorgänge, z. B., ob beschleunigte Daten im normalen Datenstream empfangen werden, ob Broadcastmeldungen für den Socket gesendet werden können und so weiter.  
  
 Es gibt zwei Arten von Socketoptionen: Boolean, das Aktivieren oder Deaktivieren einer Funktion oder ein Verhalten und Optionen für die ein Integer-Wert oder eine Struktur erfordern. So aktivieren Sie eine Option, Boolean, `lpOptionValue` verweist auf eine ganze Zahl ungleich NULL. Zum Deaktivieren der Option `lpOptionValue` verweist auf eine ganze Zahl gleich&0; (null). `nOptionLen`sollte gleich sein **sizeof(BOOL)** für boolesche Optionen. Weitere Optionen `lpOptionValue` verweist auf die ganze Zahl oder eine Struktur, die den gewünschten Wert für die Option enthält und `nOptionLen` ist die Länge der ganzen Zahlen oder Struktur.  
  
 **SO_LINGER** Steuerelemente, die die Aktion ausgeführt wird, wenn nicht gesendete Daten ist in der Warteschlange für einen Socket und **schließen** Funktion wird aufgerufen, um den Socket schließen.  
  
 Standardmäßig kann ein Socket kann nicht gebunden werden (finden Sie unter [binden](#bind)) in eine lokale Adresse bereits verwendet wird. In manchen Fällen kann jedoch es wünschenswert, eine Adresse auf diese Weise "wiederzuverwenden" sein. Da jede Verbindung durch die Kombination von lokalen und remoten Adressen eindeutig identifiziert wird, besteht kein Problem mit zwei Sockets an dieselbe lokale Adresse gebunden werden, solange die Remoteadressen unterschiedlich sind.  
  
 Informieren die Windows Sockets-Implementierung, die eine **binden** Aufruf für einen Socket sollte nicht werden nicht zulässig, da die gewünschte Adresse bereits von einem anderen Socket verwendet wird, sollte die Anwendung festlegen, die **SO_REUSEADDR** Socketoption für den Socket vor dem Ausgeben der **binden** aufrufen. Beachten Sie, dass die Option nur zum Zeitpunkt der interpretiert wird die **binden** aufrufen: ist es daher nicht erforderlich (aber harmlos) die Option für einen Socket fest sollte nicht in eine vorhandene Adresse gebunden werden und festlegen oder die Option nach dem Zurücksetzen der **binden** Aufruf hat keine Auswirkung auf diese oder beliebige andere Sockets.  
  
 Eine Anwendung kann anfordern, dass die Windows Sockets-Implementierung die Verwendung von "Keep-alive" Paketen Transmission Control Protocol (TCP)-Verbindungen aktivieren, durch Einschalten der **SO_KEEPALIVE** Socketoption. Windows Sockets-Implementierung muss nicht unterstützen die Verwendung von Keep-Alives: ist dies der Fall ist, wird die genaue Semantik sind spezifisch für die Implementierung jedoch sollte dem Abschnitt 4.2.3.6 RFC 1122: "Requirements for Internethosts – Communication Layers." Wenn eine Verbindung, als Ergebnis "Keep-Alive" Fehlercode getrennt wird: **WSAENETRESET** wird für den Socket keine Aufrufe in Bearbeitung zurückgegeben und alle nachfolgenden Aufrufe schlagen mit **WSAENOTCONN**.  
  
 Die **TCP_NODELAY** Option deaktiviert den Nagle-Algorithmus. Der Nagle-Algorithmus wird verwendet, reduzieren Sie die Anzahl der kleine Pakete von einem Host unbestätigten senden Daten gepuffert, bis ein Paket in voller Größe gesendet werden kann. Allerdings einige Anwendungsmöglichkeiten dieser Algorithmus kann beeinträchtigt, und **TCP_NODELAY** kann verwendet werden, um es zu deaktivieren. Anwendungsentwickler sollten nicht festgelegt **TCP_NODELAY** es sei denn, die Auswirkung auf diese Weise gut verstanden und gewünschte, da Einstellung **TCP_NODELAY** können erhebliche negative Auswirkungen auf die Leistung des Netzwerks. **TCP_NODELAY** ist die einzige unterstützte Socketoption der Ebene verwendet **IPPROTO_TCP**; alle anderen Optionen verwenden, auf der **SOL_SOCKET**.  
  
 Einige Implementierungen von Windows Sockets-Netzteils Debuginformationen ausgeben, wenn die **SO_DEBUG** Option wird von einer Anwendung festgelegt.  
  
 Die folgenden Optionen werden unterstützt, für die `SetSockOpt`. Der Typ gibt den Typ der Daten, die Gegenstand `lpOptionValue`.  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|Ermöglicht die Übertragung von Broadcastmeldungen für den Socket.|  
|**SO_DEBUG**|**BOOL**|Zeichnet Debuginformationen auf.|  
|**SO_DONTLINGER**|**BOOL**|Nicht blockieren **schließen** wartet nicht gesendete Daten gesendet werden. Durch Festlegen dieser Option entspricht dem Festlegen **SO_LINGER** mit **L_onoff** auf&0; (null) festgelegt.|  
|**SO_DONTROUTE**|**BOOL**|Nicht weiterleiten: direkt an der Schnittstelle senden.|  
|**SO_KEEPALIVE**|**BOOL**|Keep-Alive zu senden.|  
|**SO_LINGER**|**LINGER-Struktur**|Verzögert, **schließen** Wenn nicht gesendete Daten vorhanden ist.|  
|**SO_OOBINLINE**|**BOOL**|Empfangen von Out-of-Band-Daten im normalen Datenstream.|  
|**SO_RCVBUF**|`int`|Geben Sie für die Größe des Puffers empfängt.|  
|**SO_REUSEADDR**|**BOOL**|Ermöglichen des Sockets an eine Adresse gebunden sein, die bereits verwendet wird. (See [Bind](#bind).)|  
|**SO_SNDBUF**|`int`|Geben Sie die Puffergröße für sendet.|  
|**TCP_NODELAY**|**BOOL**|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|  
  
 Nicht unterstützten Optionen der Berkeley Software Distribution (BSD) `SetSockOpt` sind:  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Socket überwacht|  
|**SO_ERROR**|`int`|Fehlerstatus abrufen und löschen.|  
|**SO_RCVLOWAT**|`int`|Untergrenze zu empfangen.|  
|**SO_RCVTIMEO**|`int`|Empfangstimeout|  
|**SO_SNDLOWAT**|`int`|Senden Sie die Untergrenze.|  
|**SO_SNDTIMEO**|`int`|Timeout des Sendevorgangs.|  
|**SO_TYPE**|`int`|Der Typ des Sockets.|  
|**IP_OPTIONS**||SET-Optionen-Feld im IP-Header.|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 So deaktivieren Sie diese Memberfunktion sendet, Aufruf empfängt, oder beides für den Socket.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>Parameter  
 `nHow`  
 Ein Flag, das beschreibt, welche Arten des Vorgangs wird nicht mehr zulässig, mithilfe der folgenden Enumerationswerte:  
  
- **empfängt = 0**  
  
- **sendet = 1**  
  
- **sowohl = 2**  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** eine erfolgreiche [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerk-Subsystem fehlgeschlagen ist.  
  
- **WSAEINVAL** `nHow` ist ungültig.  
  
- **WSAEINPROGRESS** ein blockierender Windows Sockets-Vorgang wird ausgeführt.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 `ShutDown`wird für alle Typen von Sockets zum Empfang, Übermittlung oder beides deaktivieren. Wenn `nHow` gleich 0 ist, auf die nachfolgenden empfängt der Socket nicht zugelassen wird. Dies hat keine Auswirkung auf den unteren Protokollschichten.  
  
 Transmission Control Protocol (TCP) das TCP-Fenster wird nicht geändert und eingehende Daten werden (aber nicht bestätigt) akzeptiert werden, bis das Fenster erreicht wird. User Datagram Protocol (UDP) werden eingehende Datagramme akzeptiert und in die Warteschlange gestellt. In keinem Fall wird ein ICMP-Paket Fehler generiert. Wenn `nHow` 1, nachfolgende sendet sind nicht zulässig. Für TCP-Sockets wird eine FIN gesendet. Festlegen von `nHow` 2 deaktiviert sowohl senden und empfangen, wie oben beschrieben.  
  
 Beachten Sie, dass `ShutDown` ist nicht schließen der Socket und Ressourcen, die mit den Socket verbunden bleiben bis **schließen** aufgerufen wird. Eine Anwendung sollten nicht verlassen, können einen Socket wiederverwenden, nachdem es heruntergefahren wurde. Insbesondere ist eine Windows Sockets-Implementierung nicht erforderlich für die Unterstützung von **verbinden** solche Socket.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="socket"></a>CASyncSocket::Socket  
 Reserviert ein Sockethandle.  
  
```  
BOOL Socket(
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    int nProtocolType = 0,  
    int nAddressFormat = PF_INET);
```  
  
### <a name="parameters"></a>Parameter  
 `nSocketType`  
 Gibt an, `SOCK_STREAM` oder `SOCK_DGRAM`.  
  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- `FD_READ`: Der Bereitschaft zum Lesen Benachrichtigung erhalten möchten.  
  
- `FD_WRITE`: Der Bereitschaft für das Schreiben von Benachrichtigung erhalten möchten.  
  
- `FD_OOB`: Die Ankunft der Out-of-Band-Daten Benachrichtigung erhalten möchten.  
  
- `FD_ACCEPT`: Die Benachrichtigung von eingehenden Verbindungen empfangen möchten.  
  
- `FD_CONNECT`: Einer vervollständigte Verbindungszeichenfolge benachrichtigt werden möchten.  
  
- `FD_CLOSE`: Der Socket Closure Benachrichtigung erhalten möchten.  
  
 `nProtocolType`  
 Protokoll mit den Socket verwendet werden soll, die für die angegebene Adressfamilie spezifisch ist.  
  
 `nAddressFormat`  
 Familie Spezifikation zu beheben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` bei Erfolg bzw. `FALSE` bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode weist ein Socket-Handle. Wird nicht aufgerufen [CAsyncSocket::Bind](#bind) zum Binden des Sockets an eine angegebene Adresse, daher Sie aufrufen müssen `Bind` später zum Binden des Sockets an einer angegebenen Adresse. Sie können [CAsyncSocket::SetSockOpt](#setsockopt) die Socketoption festgelegt, bevor es gebunden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)   
 [CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)

