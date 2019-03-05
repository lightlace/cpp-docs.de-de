---
title: CAsyncSocket-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAsyncSocket [MFC], CAsyncSocket
- CAsyncSocket [MFC], Accept
- CAsyncSocket [MFC], AsyncSelect
- CAsyncSocket [MFC], Attach
- CAsyncSocket [MFC], Bind
- CAsyncSocket [MFC], Close
- CAsyncSocket [MFC], Connect
- CAsyncSocket [MFC], Create
- CAsyncSocket [MFC], Detach
- CAsyncSocket [MFC], FromHandle
- CAsyncSocket [MFC], GetLastError
- CAsyncSocket [MFC], GetPeerName
- CAsyncSocket [MFC], GetPeerNameEx
- CAsyncSocket [MFC], GetSockName
- CAsyncSocket [MFC], GetSockNameEx
- CAsyncSocket [MFC], GetSockOpt
- CAsyncSocket [MFC], IOCtl
- CAsyncSocket [MFC], Listen
- CAsyncSocket [MFC], Receive
- CAsyncSocket [MFC], ReceiveFrom
- CAsyncSocket [MFC], ReceiveFromEx
- CAsyncSocket [MFC], Send
- CAsyncSocket [MFC], SendTo
- CAsyncSocket [MFC], SendToEx
- CAsyncSocket [MFC], SetSockOpt
- CAsyncSocket [MFC], ShutDown
- CASyncSocket [MFC], Socket
- CAsyncSocket [MFC], OnAccept
- CAsyncSocket [MFC], OnClose
- CAsyncSocket [MFC], OnConnect
- CAsyncSocket [MFC], OnOutOfBandData
- CAsyncSocket [MFC], OnReceive
- CAsyncSocket [MFC], OnSend
- CAsyncSocket [MFC], m_hSocket
ms.assetid: cca4d5a1-aa0f-48bd-843e-ef0e2d7fc00b
ms.openlocfilehash: ef486e653eaf78914ea25663e0c1ab744ab30cd4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260009"
---
# <a name="casyncsocket-class"></a>CAsyncSocket-Klasse

Stellt ein Windows Socket dar – ein Endpunkt der Netzwerkkommunikation.

## <a name="syntax"></a>Syntax

```
class CAsyncSocket : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::CAsyncSocket](#casyncsocket)|Erstellt ein `CAsyncSocket`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::Accept](#accept)|Akzeptiert eine Verbindung für den Socket.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|Anforderungen die ereignisbenachrichtigung für den Socket.|
|[CAsyncSocket::Attach](#attach)|Fügt ein Sockethandle für ein `CAsyncSocket` Objekt.|
|[CAsyncSocket::Bind](#bind)|Ordnet eine lokale Adresse den Socket.|
|[CAsyncSocket::Close](#close)|Schließt den Socket.|
|[CAsyncSocket::Connect](#connect)|Herstellen einer Verbindung mit einem Peer-Socket.|
|[CAsyncSocket::Create](#create)|Erstellt einen Socket.|
|[CAsyncSocket::Detach](#detach)|Trennt ein Sockethandle von einem `CAsyncSocket` Objekt.|
|[CAsyncSocket::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CAsyncSocket` -Objekt, ein Socket-Handle.|
|[CAsyncSocket::GetLastError](#getlasterror)|Ruft den Status "Fehler" für den letzten Vorgang aus, die Fehler ab.|
|[CAsyncSocket::GetPeerName](#getpeername)|Ruft die Adresse für den Peer-Socket, der mit dem der Socket verbunden ist.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Ruft die Adresse für den Peer-Socket, den der Socket verbunden ist (Handles IPv6-Adressen) ist.|
|[CAsyncSocket::GetSockName](#getsockname)|Ruft ab, der lokale Name für einen Socket.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Ruft ab, der lokale Name für einen Socket (Handles IPv6-Adressen).|
|[CAsyncSocket::GetSockOpt](#getsockopt)|Ruft einen Socket-Option ab.|
|[CAsyncSocket::IOCtl](#ioctl)|Steuert den Modus des Sockets.|
|[CAsyncSocket::Listen](#listen)|Stellt ein Socket zum Lauschen auf eingehende verbindungsanforderungen her.|
|[CAsyncSocket::Receive](#receive)|Empfängt Daten von den Socket.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Empfängt ein Datagramm und speichert die Quelladresse.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Empfängt ein Datagramm und speichert die Quelladresse (Handles IPv6-Adressen).|
|[CAsyncSocket::Send](#send)|Sendet Daten an einen verbundenen Socket.|
|[CAsyncSocket::SendTo](#sendto)|Sendet Daten an ein bestimmtes Ziel.|
|[CAsyncSocket::SendToEx](#sendtoex)|Sendet Daten an ein bestimmtes Ziel (Handles IPv6-Adressen).|
|[CAsyncSocket::SetSockOpt](#setsockopt)|Eine Socketoption festgelegt.|
|[CAsyncSocket::ShutDown](#shutdown)|Deaktiviert die `Send` und/oder `Receive` Ruft für den Socket.|
|[CASyncSocket::Socket](#socket)|Reserviert ein Sockethandle.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::OnAccept](#onaccept)|Benachrichtigt ein Abhörsocket, den es ausstehende verbindungsanforderungen, durch den Aufruf annehmen kann `Accept`.|
|[CAsyncSocket::OnClose](#onclose)|Benachrichtigt, dass ein Socket, den der Socket verbunden geschlossen wurde.|
|[CAsyncSocket::OnConnect](#onconnect)|Benachrichtigt einem Sockets eine Verbindung herstellt, dass der Verbindungsversuch abgeschlossen ist, gibt an, ob erfolgreich oder fehlerhaft ist.|
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Benachrichtigt einem empfangenden Socket, dass Out-of-Band-Daten auf dem Socket, in der Regel eine dringende Nachricht gelesen werden.|
|[CAsyncSocket::OnReceive](#onreceive)|Benachrichtigt einem empfangsbereiten Sockets, dass es Daten durch den Aufruf abgerufen werden `Receive`.|
|[CAsyncSocket::OnSend](#onsend)|Benachrichtigt einem Socket, können sie Daten durch den Aufruf senden `Send`.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::operator =](#operator_eq)|Weist einen neuen Wert ein `CAsyncSocket` Objekt.|
|[CAsyncSocket::operator SOCKET](#operator_socket)|Verwenden Sie diesen Operator zum Abrufen der SOCKET-Handle, der die `CAsyncSocket` Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|Gibt an, die SOCKET-Handle, das angefügte `CAsyncSocket` Objekt.|

## <a name="remarks"></a>Hinweise

Klasse `CAsyncSocket` kapselt die Windows Sockets-Funktionen-API bereitstellen eine Abstraktion objektorientierte Programmierer, die Windows-Sockets in Verbindung mit MFC verwendet werden soll.

Diese Klasse basiert auf der Annahme, dass Sie verstehen, dass die Netzwerkkommunikation. Sie sind verantwortlich für die Behandlung von Blockierungen Bytereihenfolge Unterschiede, und legen Sie Konvertierungen zwischen Unicode- und multibyte-Zeichensätze (MBCS)-Zeichenfolgen. Eine besser geeignete Benutzeroberfläche, die diese Probleme für Sie verwaltet wird, finden Sie unter Klasse [CSocket](../../mfc/reference/csocket-class.md).

Verwenden einer `CAsyncSocket` Objekt, rufen Sie ihren Konstruktor rufen Sie dann die [erstellen](#create) Funktion, um die zugrunde liegenden Socket-Handle erstellen (Typ `SOCKET`), außer auf akzeptierte Sockets. Für einen Server Socket-Aufruf die [Lauschen](#listen) Member-Funktion, und für einen Client-Socket-Aufruf die [Connect](#connect) Member-Funktion. Der Serversocket sollten aufrufen, die [Accept](#accept) Funktion eine verbindungsanforderung eingeht. Verwenden Sie die verbleibenden `CAsyncSocket` Funktionen, um die Kommunikation zwischen Sockets durchzuführen. Nach Abschluss des Vorgangs zu zerstören der `CAsyncSocket` Objekt, wenn sie auf dem Heap erstellt wurde, ruft der Destruktor automatisch den [schließen](#close) Funktion. Der Datentyp SOCKET wird in diesem Artikel beschrieben [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).

> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC-Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jeder Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. In der Standardeinstellung `AfxSocketInit` nur im primären Thread aufgerufen wird.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden der CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) und zugehörigen Artikeln., als auch [Windows Sockets-2-API](/windows/desktop/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Anforderungen

**Header:** afxsock.h

##  <a name="accept"></a>  CAsyncSocket::Accept

Rufen Sie diese Memberfunktion, um eine Verbindung für einen Socket zu akzeptieren.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Parameter

*rConnectedSocket*<br/>
Ein Verweis, identifizieren einen neuen Socket, der für die Verbindung verfügbar ist.

*lpSockAddr*<br/>
Ein Zeiger auf eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) socket-Struktur, die die Adresse des verbindenden empfängt, als im Netzwerk bekannt. Das genaue Format der der *LpSockAddr* Argument richtet sich nach der Adressfamilie hergestellt, wenn der Socket erstellt wurde. Wenn *LpSockAddr* und/oder *LpSockAddrLen* für NULL-Werte gleich sind, und klicken Sie dann keine Informationen über die remote-Adresse von der angenommene Socket zurückgegeben wird.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Adresse im *LpSockAddr* in Byte. Die *LpSockAddrLen* ist ein Wert als Ergebnis Parameter: Er sollte zunächst die Menge des Speicherplatzes verweist enthalten *LpSockAddr*; bei der Rückgabe die tatsächliche Länge (in Byte), der die zurückgegebene Adresse enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument ist zu klein (weniger als die Größe des eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur).

- "WSAEINPROGRESS" zurück A, die blockierende Windows Sockets aufrufen wird ausgeführt.

- WSAEINVAL `Listen` war nicht aufgerufene vor dem akzeptieren.

- WSAEMFILE die Warteschlange ist leer, bei der Eingabe akzeptieren und es sind keine sicherheitsbeschreibungen verfügbar.

- WSAENOBUFS kein Pufferspeicher ist verfügbar.

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP der referenzierten Socket ist kein Typ, der mit verbindungsorientierten Dienst unterstützt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend sind keine Verbindungen vorhanden, um akzeptiert zu werden.

### <a name="remarks"></a>Hinweise

Extrahiert die erste Verbindung in der Warteschlange der ausstehenden Verbindungen, erstellt einen neuen Socket mit denselben Eigenschaften wie diesen Socket und fügt sie an diese Routine *rConnectedSocket*. Wenn keine ausstehenden Verbindungen in der Warteschlange vorhanden sind `Accept` gibt 0 (null) und `GetLastError` gibt einen Fehler zurück. Der angenommene Socket ( *rConnectedSocket)* kann nicht verwendet werden, um weitere Verbindungen zu akzeptieren. Der ursprüngliche Socket bleibt geöffnet ist und.

Das Argument *LpSockAddr* ist ein Ergebnisparameter, der mit der Adresse des Sockets eine Verbindung herstellt, gefüllt wird, da es sich bei der Kommunikation Ebene bezeichnet. `Accept` wird mit verbindungsorientierten Sockettypen, z. B. SOCK_STREAM verwendet.

##  <a name="asyncselect"></a>  CAsyncSocket::AsyncSelect

Rufen Sie diese Memberfunktion, um die ereignisbenachrichtigung für einen Socket anzufordern.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parameter

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.

- Empfangen von Benachrichtigungen über die Bereitschaft zum Lesen FD_READ maskiert werden soll.

- FD_WRITE möchten Benachrichtigung erhalten, wenn Daten gelesen werden können.

- FD_OOB den Eingang von Out-of-Band-Daten benachrichtigt werden soll.

- FD_ACCEPT soll zum Empfangen von Benachrichtigungen zu eingehenden Verbindungen.

- FD_CONNECT Verbindung bewirkt eine Benachrichtigung erhalten möchten.

- FD_CLOSE möchten Benachrichtigung erhalten, wenn ein Socket von einem Peer geschlossen wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEINVAL gibt an, dass eine der angegebenen Parameter war ungültig.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

### <a name="remarks"></a>Hinweise

Diese Funktion wird verwendet, um anzugeben, für den Socket Benachrichtigungsfunktionen der MFC-Rückruf aufgerufen werden. `AsyncSelect` legt automatisch diesen Socket in den nicht blockierenden Modus fest. Weitere Informationen finden Sie im Artikel [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="attach"></a>  CAsyncSocket::Attach

Rufen Sie diese Memberfunktion zum Anfügen der *hSocket* handle für ein `CAsyncSocket` Objekt.

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parameter

*hSocket*<br/>
Enthält ein Handle für einen Socket.

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.

- Empfangen von Benachrichtigungen über die Bereitschaft zum Lesen FD_READ maskiert werden soll.

- FD_WRITE möchten Benachrichtigung erhalten, wenn Daten gelesen werden können.

- FD_OOB den Eingang von Out-of-Band-Daten benachrichtigt werden soll.

- FD_ACCEPT soll zum Empfangen von Benachrichtigungen zu eingehenden Verbindungen.

- FD_CONNECT Verbindung bewirkt eine Benachrichtigung erhalten möchten.

- FD_CLOSE möchten Benachrichtigung erhalten, wenn ein Socket von einem Peer geschlossen wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich null, wenn die Funktion erfolgreich ist.

### <a name="remarks"></a>Hinweise

Der SOCKET-Handle befindet sich in den Objekteigenschaften [M_hSocket](#m_hsocket) -Datenmember.

##  <a name="bind"></a>  CAsyncSocket::Bind

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

*nSocketPort*<br/>
Der Port, der die Socket-Anwendung angibt.

*lpszSocketAddress*<br/>
Die Netzwerkadresse, ein durch Punkte getrennte Zahl wie z. B. "128.56.22.8". Übergeben das NULL-Zeichen Zeichenfolge, für die dieser Parameter gibt an, die `CAsyncSocket` Instanz Clientaktivität an allen Netzwerkschnittstellen überwachen soll.

*lpSockAddr*<br/>
Ein Zeiger auf eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) -Struktur, die Adresse enthält, die diesen Socket zuweisen.

*nSockAddrLen*<br/>
Die Länge der Adresse im *LpSockAddr* in Byte.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEADDRINUSE wird die angegebene Adresse bereits verwendet. (Finden Sie unter der Option SO_REUSEADDR Socket unter [SetSockOpt](#setsockopt).)

- WSAEFAULT der *nSockAddrLen* Argument ist zu klein (weniger als die Größe des eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur).

- "WSAEINPROGRESS" zurück A, die blockierende Windows Sockets aufrufen wird ausgeführt.

- Die angegebene Adressfamilie wird dieser Port nicht unterstützt.

- WSAEINVAL den Socket ist bereits an eine Adresse gebunden.

- Nicht WSAENOBUFS genug puffert verfügbar ist, zu viele Verbindungen.

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Diese Routine wird auf einem nicht verbundenen Datagramm oder den Streamsocket verwendet, vor dem nachfolgenden `Connect` oder `Listen` aufrufen. Bevor er verbindungsanforderungen annehmen kann, ein empfangsbereiten Serversockets muss wählen Sie eine Portnummer an, und stellen es bekannte auf Windows-Sockets durch Aufrufen `Bind`. `Bind` Stellt die lokalen Zuordnung (Host-Adresse/Port-Nummer) des Sockets durch Zuweisen von einem lokalen Namen zu einem unbenannten Socket her.

##  <a name="casyncsocket"></a>  CAsyncSocket::CAsyncSocket

Erstellt einen leeren Socketobjekt.

```
CAsyncSocket();
```

### <a name="remarks"></a>Hinweise

Sie müssen nach dem Erstellen des Objekts aufrufen seiner `Create` Memberfunktion versucht, die SOCKET-Datenstruktur zu erstellen und binden Sie die Adresse. (Auf der Serverseite einer Windows-Sockets-Kommunikation, beim Erstellen der Abhörsocket einen Socket für die Verwendung in der `Accept` aufrufen, Sie rufen nicht `Create` für diesen Socket.)

##  <a name="close"></a>  CAsyncSocket::Close

Schließt den Socket.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Diese Funktion gibt den Socket-Deskriptor, damit Weitere Verweise auf diese mit dem Fehler WSAENOTSOCK fehl. Wenn dies der letzte Verweis auf den zugrunde liegenden Socket ist, werden die zugehörigen Namensinformationen und die Daten in der Warteschlange verworfen. Das Socketobjekt-Destruktoraufrufe `Close` für Sie.

Für `CAsyncSocket`, aber nicht für `CSocket`, die Semantik der `Close` von den Socketoptionen SO_LINGER und SO_DONTLINGER betroffen sind. Weitere Informationen finden Sie unter Memberfunktion `GetSockOpt`.

##  <a name="connect"></a>  CAsyncSocket:: Connect

Rufen Sie diese Memberfunktion zum Herstellen einer Verbindung mit einer nicht verbundenen Stream oder die Datagrammsocket zeigt.

```
BOOL Connect(
    LPCTSTR lpszHostAddress,
    UINT nHostPort);

BOOL Connect(
    const SOCKADDR* lpSockAddr,
    int nSockAddrLen);
```

### <a name="parameters"></a>Parameter

*lpszHostAddress*<br/>
Die Netzwerkadresse für den Socket, der mit dem dieses Objekt verbunden ist: einen Computernamen ein, z. B. "ftp.microsoft.com" oder eine durch Punkte getrennte Zahl wie z. B. "128.56.22.8".

*nHostPort*<br/>
Der Port, der die Socket-Anwendung angibt.

*lpSockAddr*<br/>
Ein Zeiger auf eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) -Struktur, die die Adresse des verbundenen Sockets enthält.

*nSockAddrLen*<br/>
Die Länge der Adresse im *LpSockAddr* in Byte.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Wenn dies weist darauf hin, einem Fehlercode von WSAEWOULDBLOCK und Ihre Anwendung die überschreibbare Rückrufe verwendet, empfängt die Anwendung eine `OnConnect` Meldung, wenn der Verbindungsvorgang abgeschlossen ist. Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEADDRINUSE wird die angegebene Adresse bereits verwendet.

- "WSAEINPROGRESS" zurück A, die blockierende Windows Sockets aufrufen wird ausgeführt.

- WSAEADDRNOTAVAIL die angegebene Adresse ist nicht verfügbar, auf dem lokalen Computer.

- NICHT-Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.

- STARK, die beim Herstellen einer Verbindung wurde zurückgewiesen.

- Zieladresse WSAEDESTADDRREQ A ist erforderlich.

- WSAEFAULT der *nSockAddrLen* Argument ist falsch.

- Ungültige WSAEINVAL Hostadresse.

- WSAEISCONN der Socket ist bereits verbunden.

- WSAEMFILE keine sind die weiteren Dateideskriptoren verfügbar.

- WSAENETUNREACH kann nicht von diesem Host zu diesem Zeitpunkt das Netzwerk erreicht werden.

- WSAENOBUFS kein Pufferspeicher ist verfügbar. Der Socket kann nicht verbunden werden.

- WSAENOTSOCK Deskriptor ist kein Socket.

- Timeout bei der WSAETIMEDOUT beim Herstellen einer Verbindung, ohne eine Verbindung herzustellen.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und die Verbindung nicht sofort abgeschlossen werden.

### <a name="remarks"></a>Hinweise

Wenn der Socket aufgehoben wird, eindeutige Werte der lokalen Zuordnung vom System zugewiesen werden und der Socket ist als markiert gebunden. Beachten Sie, wenn das Feld "Adresse" die Name-Struktur ist ausschließlich Nullen `Connect` gibt 0 (null) zurück. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die `GetLastError` Member-Funktion.

Für Streamsockets (SOCK_STREAM-Typ) wird eine aktive Verbindung mit dem Fremdschlüssel Host initiiert. Wenn der Socket-Aufruf erfolgreich abgeschlossen wurde, ist der Socket zum Senden/Empfangen von Daten bereit.

Für einen Datagrammsocket (Typ SOCK_DGRAM), ein Standardziel festgelegt ist, und die wird in nachfolgenden verwendet `Send` und `Receive` aufrufen.

##  <a name="create"></a>  CAsyncSocket::Create

Rufen Sie die `Create` Memberfunktion nach dem Erstellen der ein Socketobjekt, um den Windows-Socket zu erstellen und anzufügen.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parameter

*nSocketPort*<br/>
Den bekannten Port mit der Socket, oder 0 verwendet werden, wenn Sie Windows-Sockets auf einen Port auswählen möchten.

*nSocketType*<br/>
SOCK_STREAM oder SOCK_DGRAM.

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.

- Empfangen von Benachrichtigungen über die Bereitschaft zum Lesen FD_READ maskiert werden soll.

- FD_WRITE soll zum Empfangen von Benachrichtigungen über die Bereitschaft zum Schreiben.

- FD_OOB den Eingang von Out-of-Band-Daten benachrichtigt werden soll.

- FD_ACCEPT soll zum Empfangen von Benachrichtigungen zu eingehenden Verbindungen.

- FD_CONNECT abgeschlossene Verbindung benachrichtigt werden soll.

- FD_CLOSE Socket Abschluss benachrichtigt werden soll.

*lpszSockAddress*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets, ein durch Punkte getrennte Zahl wie z. B. "128.56.22.8" enthält. Übergeben das NULL-Zeichen Zeichenfolge, für die dieser Parameter gibt an, die `CAsyncSocket` Instanz Clientaktivität an allen Netzwerkschnittstellen überwachen soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- Die angegebene Adressfamilie wird nicht unterstützt.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAEMFILE keine sind die weiteren Dateideskriptoren verfügbar.

- WSAENOBUFS kein Pufferspeicher ist verfügbar. Der Socket kann nicht erstellt werden.

- WSAEPROTONOSUPPORT der angegebene Port wird nicht unterstützt.

- WSAEPROTOTYPE der angegebene Port ist der falsche Typ für diesen Socket.

- WSAESOCKTNOSUPPORT den angegebenen Sockettyp wird in dieser Adressfamilie nicht unterstützt.

### <a name="remarks"></a>Hinweise

`Create` Aufrufe [Socket](#socket) und im Erfolgsfall ruft [binden](#bind) der Socket mit der angegebenen Adresse binden. Die folgenden Sockettypen werden unterstützt:

- SOCK_STREAM sequenziert, bietet zuverlässige, Vollduplex- und verbindungsbasierte Bytestreams. Verwendet das Protokoll TCP (Transmission Control) für die Internetadressenfamilie an.

- SOCK_DGRAM unterstützt Datagramme, die verbindungslose, unzuverlässige Pakete mit einer festen (i. d. r. kleinen) maximalen Länge sind. Verwendet das User Datagram Protocol (UDP) für die Internetadressenfamilie an.

    > [!NOTE]
    >  Die `Accept` Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Müssen Sie dieses Objekt erstellen, vor dem Aufruf `Accept`. Beachten Sie, dass wenn dieser Socketobjekt des Bereichs, die Verbindung geschlossen wird. Rufen Sie keine `Create` für dieses neuen Socketobjekt.

> [!IMPORTANT]
> `Create` ist **nicht** threadsicher.  Wenn der Aufruf es in einer Multithread-Umgebung, in dem können sie gleichzeitig von verschiedenen Threads aufgerufen werden, achten Sie darauf, dass Sie jeden Aufruf mit einem Mutex oder andere Synchronisierungssperre zu schützen.

Weitere Informationen zu Stream und Datagramm-Sockets, finden Sie in den Artikeln [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md) und [Windows Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md) und [Windows Sockets-2-API](/windows/desktop/WinSock/windows-sockets-start-page-2).

##  <a name="detach"></a>  CAsyncSocket::Detach

Rufen Sie diese Memberfunktion zum Trennen der SOCKET-Handle in die *M_hSocket* Datenmember aus der `CAsyncSocket` Objekt, und legen *M_hSocket* auf NULL.

```
SOCKET Detach();
```

##  <a name="fromhandle"></a>  CAsyncSocket::FromHandle

Gibt einen Zeiger auf eine `CAsyncSocket` Objekt.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parameter

*hSocket*<br/>
Enthält ein Handle für einen Socket.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CAsyncSocket` Objekt oder NULL, wenn es gibt keine `CAsyncSocket` Objekt angefügt, um *hSocket*.

### <a name="remarks"></a>Hinweise

Wenn ein SOCKET-Handle, wenn eine `CAsyncSocket` Objekt ist nicht auf das Handle angefügt, die Member-Funktion gibt NULL zurück.

##  <a name="getlasterror"></a>  CAsyncSocket::GetLastError

Rufen Sie diese Memberfunktion um den Status "Fehler" für den letzten Vorgang zu erhalten, die nicht an.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt an, der Fehlercode für die letzten Windows Sockets-API-Routine, die von diesem Thread ausgeführt wird.

### <a name="remarks"></a>Hinweise

Wenn eine bestimmte Member-Funktion gibt an, dass ein Fehler aufgetreten ist, `GetLastError` aufgerufen werden, um den entsprechenden Fehlercode abzurufen. Finden Sie unter den Beschreibungen der einzelnen Mitgliedsdatenbanken Funktionen für eine Liste der entsprechenden Fehlercodes.

Weitere Informationen zu den Fehlercodes finden Sie unter [Windows Sockets-2-API](/windows/desktop/WinSock/windows-sockets-start-page-2).

##  <a name="getpeername"></a>  CAsyncSocket::GetPeerName

Rufen Sie diese Memberfunktion zum Abrufen der Adresse für den Peer-Socket, mit dem diesen Socket verbunden ist.

```
BOOL GetPeerName(
    CString& rPeerAddress,
    UINT& rPeerPort);

BOOL GetPeerName(
    SOCKADDR* lpSockAddr,
    int* lpSockAddrLen);
```

### <a name="parameters"></a>Parameter

*rPeerAddress*<br/>
Ein Verweis auf eine `CString` Objekt, das eine gepunktete Anzahl IP-Adresse empfängt.

*rPeerPort*<br/>
Verweis auf eine "uint", in dem einen Port gespeichert.

*lpSockAddr*<br/>
Ein Zeiger auf die [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur, die den Namen für den Peer-Socket empfängt.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Adresse im *LpSockAddr* in Byte. Bei der Rückgabe der *LpSockAddrLen* Argument enthält die tatsächliche Größe der *LpSockAddr* in Bytes zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument ist nicht groß genug.

- "WSAEINPROGRESS" zurück A, die blockierende Windows Sockets aufrufen wird ausgeführt.

- WSAENOTCONN den Socket ist nicht verbunden.

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::GetPeerNameEx](#getpeernameex).

##  <a name="getpeernameex"></a>  CAsyncSocket::GetPeerNameEx

Rufen Sie diese Memberfunktion, um die Adresse für den Peer-Socket zu erhalten, der diesen Socket verbunden ist (Handles IPv6-Adressen) ist.

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Parameter

*rPeerAddress*<br/>
Ein Verweis auf eine `CString` Objekt, das eine gepunktete Anzahl IP-Adresse empfängt.

*rPeerPort*<br/>
Verweis auf eine "uint", in dem einen Port gespeichert.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument ist nicht groß genug.

- "WSAEINPROGRESS" zurück A, die blockierende Windows Sockets aufrufen wird ausgeführt.

- WSAENOTCONN den Socket ist nicht verbunden.

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Diese Funktion ist identisch mit [CAsyncSocket::GetPeerName](#getpeername) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen als auch ältere Protokolle.

##  <a name="getsockname"></a>  CAsyncSocket::GetSockName

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

*rSocketAddress*<br/>
Ein Verweis auf eine `CString` Objekt, das eine gepunktete Anzahl IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf eine "uint", in dem einen Port gespeichert.

*lpSockAddr*<br/>
Ein Zeiger auf eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) -Struktur, die die Adresse für den Socket empfängt.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Adresse im *LpSockAddr* in Byte.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument ist nicht groß genug.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAENOTSOCK Deskriptor ist kein Socket.

- Der Socket nicht gebunden wurde, eine Adresse mit WSAEINVAL `Bind`.

### <a name="remarks"></a>Hinweise

Dieser Aufruf ist besonders nützlich, wenn eine `Connect` Aufruf ohne eine `Bind` zuerst dieser Aufruf stellt die einzige Möglichkeit, die mit dem können Sie bestimmen, lokale Zuordnung, die vom System festgelegt wurde.

Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::GetSockNameEx](#getsocknameex)

##  <a name="getsocknameex"></a>  CAsyncSocket::GetSockNameEx

Rufen Sie diese Memberfunktion zum Abrufen des lokalen Namens für einen Socket (Handles IPv6-Adressen).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Parameter

*rSocketAddress*<br/>
Ein Verweis auf eine `CString` Objekt, das eine gepunktete Anzahl IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf eine "uint", in dem einen Port gespeichert.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument ist nicht groß genug.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAENOTSOCK Deskriptor ist kein Socket.

- Der Socket nicht gebunden wurde, eine Adresse mit WSAEINVAL `Bind`.

### <a name="remarks"></a>Hinweise

Dieser Aufruf ist identisch mit [CAsyncSocket::GetSockName](#getsockname) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen als auch ältere Protokolle.

Dieser Aufruf ist besonders nützlich, wenn eine `Connect` Aufruf ohne eine `Bind` zuerst dieser Aufruf stellt die einzige Möglichkeit, die mit dem können Sie bestimmen, lokale Zuordnung, die vom System festgelegt wurde.

##  <a name="getsockopt"></a>  CAsyncSocket::GetSockOpt

Rufen Sie diese Memberfunktion zum Abrufen von einer Socket-Option.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parameter

*nOptionName*<br/>
Die Socketoption für die der Wert abgerufen werden sollen.

*lpOptionValue*<br/>
Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option ist, zurückgegeben werden. Der Wert, der mit der ausgewählten Option verbundene wird zurückgegeben, in den Puffer *LpOptionValue*. Die ganze Zahl verweist *LpOptionLen* sollte die Größe dieses Puffers in Byte; ursprünglich enthalten und bei der Rückgabe wird diese auf die Größe des zurückgegebenen Werts festgelegt werden. In SO_LINGER, ist das die Größe des eine `LINGER` Struktur; für alle anderen Optionen werden sie die Größe der einen booleschen Wert oder ein **Int**, je nachdem, auf die Option. Finden Sie in der Liste der Optionen und ihre Größen im Abschnitt "Hinweise".

*lpOptionLen*<br/>
Ein Zeiger auf die Größe der *LpOptionValue* Puffers in Byte.

*nLevel*<br/>
Die Ebene, an der die Option definiert ist; die einzige unterstützte Grade sind SOL_SOCKET und IPPROTO_TCP.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Wenn Sie eine Option mit nie festgelegt wurde `SetSockOpt`, klicken Sie dann `GetSockOpt` gibt den Standardwert für die Option zurück. Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpOptionLen* Argument war ungültig.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAENOPROTOOPT die Option ist unbekannt oder nicht unterstützt. Insbesondere wird SO_BROADCAST für Sockets des Typs SOCK_STREAM, beim SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER und SO_OOBINLINE werden nicht unterstützt für Sockets des Typs SOCK_DGRAM nicht unterstützt.

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

`GetSockOpt` Ruft den aktuellen Wert für einen Socket-Option verknüpft ist, mit einem Socket eines beliebigen Typs, in einem beliebigen Zustand, und speichert das Ergebnis in *LpOptionValue*. Optionen beeinflussen die Socketvorgänge, z. B. das routing der Pakete Out-of-Band-Datenübertragung und So weiter.

Die folgenden Optionen werden unterstützt, für die `GetSockOpt`. Den Typ identifiziert den Typ der Daten behoben, indem *LpOptionValue*. Die Option TCP_NODELAY verwendet Ebene IPPROTO_TCP; Alle anderen Optionen verwenden Sie Stufe SOL_SOCKET.

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Socket überwacht.|
|SO_BROADCAST|BOOL|Socket ist für die Übertragung von Nachrichten konfiguriert.|
|SO_DEBUG|BOOL|Debuggen ist aktiviert.|
|SO_DONTLINGER|BOOL|Bei "true", ist die SO_LINGER-Option deaktiviert.|
|SO_DONTROUTE|BOOL|Routing ist deaktiviert.|
|SO_ERROR|**int**|Rufen Sie des Status "Fehler ab", und deaktivieren.|
|SO_KEEPALIVE|BOOL|Keep-Alives werden gesendet wird.|
|SO_LINGER|`struct LINGER`|Gibt die aktuellen Linger Optionen zurück.|
|SO_OOBINLINE|BOOL|Out-of-Band-Daten werden im normalen Datenstream empfangen wird.|
|SO_RCVBUF|int|Puffergröße für empfängt.|
|SO_REUSEADDR|BOOL|Der Socket kann zu einer Adresse gebunden werden, das bereits verwendet wird.|
|SO_SNDBUF|**int**|Puffergröße für sendet.|
|SO_TYPE|**int**|Der Typ des Sockets (z. B. SOCK_STREAM).|
|TCP_NODELAY|BOOL|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|

Optionen für die Berkeley Software Distribution (BSD) nicht unterstützt für `GetSockOpt` sind:

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Erhalten Sie die untere Grenze.|
|SO_RCVTIMEO|**int**|Timeout des Empfangsvorgangs.|
|SO_SNDLOWAT|**int**|Senden Sie die untere Grenze.|
|SO_SNDTIMEO|**int**|Timeout des Sendevorgangs.|
|IP_OPTIONS||Erhalten Sie Optionen im IP-Header.|
|TCP_MAXSEG|**int**|TCP, maximale Segmentgröße zu erhalten.|

Aufrufen von `GetSockOpt` mit einer nicht unterstützten Option führt zu einem Fehlercode von WSAENOPROTOOPT zurückgegeben werden aus der `GetLastError`.

##  <a name="ioctl"></a>  CAsyncSocket::IOCtl

Rufen Sie diese Memberfunktion um den Modus eines Sockets zu steuern.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Parameter

*lCommand*<br/>
Der Befehl zum Ausführen auf dem Socket.

*lpArgument*<br/>
Ein Zeiger auf einen Parameter für *lCommand*.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEINVAL *lCommand* ist kein gültiger Befehl, oder *LpArgument* ist kein zulässiger Parameter für *lCommand*, oder der Befehl gilt nicht für den Typ des angegebenen Sockets .

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Diese Routine kann auf jedem Socket in einem beliebigen Zustand verwendet werden. Es dient zum Abrufen oder Abrufen von Betriebsparameter der Socket, unabhängig von dem Protokoll und die Kommunikation Subsystem zugeordnet. Die folgenden Befehle werden unterstützt:

- FIONBIO aktivieren oder deaktivieren nicht blockierenden Modus für den Socket. Die *LpArgument* Parameter verweist auf eine `DWORD`ist ungleich NULL, wenn nicht blockierenden Modus aktiviert werden, und NULL, wenn es deaktiviert ist. Wenn `AsyncSelect` auf einen Socket ausgestellt wurde, und klicken Sie dann ein Versuch, `IOCtl` den Socket festzulegende zurück zu blockierenden Modus mit WSAEINVAL fehl. Um den Socket zurück in den blockierenden Modus festgelegt, und zu verhindern, dass des Fehlers WSAEINVAL, eine Anwendung muss zuerst deaktivieren `AsyncSelect` durch Aufrufen von `AsyncSelect` mit der *lEvent* Parameter gleich 0 ist, rufen Sie anschließend `IOCtl`.

- FIONREAD bestimmt die maximale Anzahl von Bytes, die mit einem gelesen werden kann `Receive` aus diesen Socket aufrufen. Die *LpArgument* Parameter verweist auf eine `DWORD` in der `IOCtl` speichert das Ergebnis. Wenn dieser Socket SOCK_STREAM-Typs ist, gibt FIONREAD die Gesamtmenge der Daten aus der gelesen werden kann in einem einzelnen `Receive`; Dies ist normalerweise der gleiche wie die Gesamtmenge der Daten auf dem Socket in die Warteschlange eingereiht. Wenn dieser Socket vom Typ SOCK_DGRAM ist, gibt FIONREAD, dass die Größe des ersten Datagramms auf dem Socket in die Warteschlange eingereiht.

- SIOCATMARK zu bestimmen, ob alle Out-of-Band-Daten gelesen wurden. Dies gilt nur für einen Socket vom Typ SOCK_STREAM, die für den Empfang von Inline-Out-of-Band-Daten (SO_OOBINLINE) konfiguriert wurde. Wenn keine Out-of-Band-Daten gelesen werden wartet, gibt der Vorgang ungleich NULL zurück. Andernfalls 0, und die nächste `Receive` oder `ReceiveFrom` ausgeführt wird, auf der Socket wird abgerufen, einige oder alle Daten vor der "Mark", sollte die Anwendung den SIOCATMARK-Vorgang verwenden, um festzustellen, ob irgendwelche Daten verbleiben. Wenn die "dringenden" (Out-of-Band-) Daten vor normalen Daten vorhanden sind, wird es in der Reihenfolge empfangen werden. (Beachten Sie, dass eine `Receive` oder `ReceiveFrom` normale und Out-of-Band-Daten in den gleichen Aufruf wird niemals mischen.) Die *LpArgument* Parameter verweist auf eine `DWORD` in der `IOCtl` speichert das Ergebnis.

Diese Funktion ist eine Teilmenge der `ioctl()` in Berkeley-Sockets verwendet. Es gibt insbesondere keinen Befehl entspricht der FIOASYNC,. SIOCATMARK ist der nur socketebenen--Befehl das unterstützt wird.

##  <a name="listen"></a>  CAsyncSocket:: Listen

Rufen Sie diese Memberfunktion zum Lauschen auf eingehende verbindungsanforderungen.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Parameter

*nConnectionBacklog*<br/>
Die maximale Länge, die auf der die Warteschlange der ausstehenden Verbindungen vergrößert werden kann. Gültige Bereich liegt zwischen 1 und 5.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEADDRINUSE ein Versuch wurde für das Lauschen an eine Adresse verwendet.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- Der Socket nicht mit gebundenen WSAEINVAL `Bind` oder bereits verbunden ist.

- WSAEISCONN der Socket ist bereits verbunden.

- WSAEMFILE keine sind die weiteren Dateideskriptoren verfügbar.

- WSAENOBUFS kein Pufferspeicher ist verfügbar.

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP der referenzierte Socket nicht vom ein Typ ist, unterstützt die `Listen` Vorgang.

### <a name="remarks"></a>Hinweise

Um Verbindungen zu akzeptieren, wird zuerst der Socket mit erstellt `Create`, ein Backlogs für eingehende Verbindungen wird angegeben, mit `Listen`, und klicken Sie dann die Verbindungen mit akzeptiert `Accept`. `Listen` gilt nur für Sockets, die Unterstützung von Verbindungen, d. h. die eines Typs SOCK_STREAM. Diesen Socket ist "Passiv" Modus versetzen, in denen eingehende Verbindungen bestätigt und in der Warteschlange ausstehender Zustimmung durch den Prozess.

Diese Funktion wird in der Regel von Servern (oder jede Anwendung, die Verbindungen akzeptieren möchte) verwendet, die möglicherweise mehr als eine verbindungsanforderung zu einem Zeitpunkt: Wenn eine verbindungsanforderung mit der vollständigen Warteschlange eintrifft, der Client wird eine Fehlermeldung mit Angabe der STARK.

`Listen` versucht, die weiterhin Rational funktionieren, wenn es keine Ports verfügbar (Deskriptoren sind). Es akzeptiert Verbindungen, bis die Warteschlange geleert wird. Wenn Ports verfügbar sind, ein späterer Aufruf von `Listen` oder `Accept` wird nach Möglichkeit Auffüllen der Warteschlange im aktuellen oder letzten "Backlog", und fortsetzen für eingehende Verbindungen lauscht.

##  <a name="m_hsocket"></a>  CAsyncSocket::m_hSocket

Enthält die SOCKET-Handle für den Socket, der von diesem gekapselt `CAsyncSocket` Objekt.

```
SOCKET m_hSocket;
```

##  <a name="onaccept"></a>  CAsyncSocket::OnAccept

Wird aufgerufen, durch das Framework zu einen überwachenden Socket zu informieren, die es ausstehende verbindungsanforderungen, durch den Aufruf annehmen kann der [Accept](#accept) Member-Funktion.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Das neueste Fehlerprotokoll für einen Socket. Die folgenden Fehlercodes gilt für die `OnAccept` Memberfunktion:

- **0** die Funktion erfolgreich ausgeführt wurde.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onclose"></a>  CAsyncSocket::OnClose

Vom Framework aufgerufen, der diesen Socket mitzuteilen, dass die verbundene Socket von einem Prozess geschlossen wird.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Das neueste Fehlerprotokoll für einen Socket. Die folgenden Fehlercodes gelten für die `OnClose` Memberfunktion:

- **0** die Funktion erfolgreich ausgeführt wurde.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAECONNRESET die Verbindung wurde von der Remoteseite zurückgesetzt.

- WSAECONNABORTED die Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onconnect"></a>  CAsyncSocket::OnConnect

Vom Framework aufgerufen, die diese verbinden Socket mitzuteilen, dass der Verbindungsversuch, ob erfolgreich oder Fehler abgeschlossen ist.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Das neueste Fehlerprotokoll für einen Socket. Die folgenden Fehlercodes gelten für die `OnConnect` Memberfunktion:

- **0** die Funktion erfolgreich ausgeführt wurde.

- WSAEADDRINUSE wird die angegebene Adresse bereits verwendet.

- WSAEADDRNOTAVAIL die angegebene Adresse ist nicht verfügbar, auf dem lokalen Computer.

- NICHT-Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.

- STARK des Verbindungsversuchs wurde erzwungen zurückgewiesen.

- Zieladresse WSAEDESTADDRREQ A ist erforderlich.

- WSAEFAULT der *LpSockAddrLen* Argument ist falsch.

- WSAEINVAL den Socket ist bereits an eine Adresse gebunden.

- WSAEISCONN der Socket ist bereits verbunden.

- WSAEMFILE keine sind die weiteren Dateideskriptoren verfügbar.

- WSAENETUNREACH kann nicht von diesem Host zu diesem Zeitpunkt das Netzwerk erreicht werden.

- WSAENOBUFS kein Pufferspeicher ist verfügbar. Der Socket kann nicht verbunden werden.

- WSAENOTCONN den Socket ist nicht verbunden.

- WSAENOTSOCK Deskriptor wird eine Datei, die nicht auf einen Socket.

- Timeout bei der WSAETIMEDOUT der Versuch, eine Verbindung herstellen, ohne eine Verbindung herzustellen.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  In [CSocket](../../mfc/reference/csocket-class.md), `OnConnect` Benachrichtigungsfunktion wird nie aufgerufen. Für Verbindungen, rufen Sie einfach `Connect`, die dann zurück, wenn die Verbindung (erfolgreich oder Fehler) erstellt wird. Behandlung von Benachrichtigungen von Verbindung ist ein Implementierungsdetail MFC.

Weitere Informationen finden Sie unter [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

##  <a name="onoutofbanddata"></a>  CAsyncSocket::OnOutOfBandData

Wird aufgerufen, durch das Framework des empfangenden Sockets zu benachrichtigen, die der sendende Socket Out-of-Band-Daten zu senden.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Das neueste Fehlerprotokoll für einen Socket. Die folgenden Fehlercodes gelten für die `OnOutOfBandData` Memberfunktion:

- **0** die Funktion erfolgreich ausgeführt wurde.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Out-of-Band-Daten sind logisch unabhängige Kanäle, die für jedes Paar an verbundene Sockets des Typs SOCK_STREAM verknüpft ist. Der Kanal wird in der Regel verwendet, um dringende Daten zu senden.

MFC unterstützt die Out-of-Band-Daten, aber die Benutzer der Klasse `CAsyncSocket` wird davon abgeraten, aus deren Nutzung. Die einfachste Methode besteht darin einen zweiten Socket für die Übergabe dieser Daten zu erstellen. Weitere Informationen über Out-of-Band-Daten finden Sie unter [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onreceive"></a>  CAsyncSocket::OnReceive

Aufgerufen, um diesen Socket zu benachrichtigen, dass Daten im Puffer, der durch den Aufruf abgerufen werden kann die `Receive` Member-Funktion.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Das neueste Fehlerprotokoll für einen Socket. Die folgenden Fehlercodes gelten für die `OnReceive` Memberfunktion:

- **0** die Funktion erfolgreich ausgeführt wurde.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

##  <a name="onsend"></a>  CAsyncSocket::OnSend

Wird aufgerufen, durch das Framework der Socket mitzuteilen, dass die Daten nun durch den Aufruf gesendet werden können die `Send` Member-Funktion.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Das neueste Fehlerprotokoll für einen Socket. Die folgenden Fehlercodes gelten für die `OnSend` Memberfunktion:

- **0** die Funktion erfolgreich ausgeführt wurde.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Windows Sockets: Socket-Benachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

##  <a name="operator_eq"></a>  CAsyncSocket::operator =

Weist einen neuen Wert ein `CAsyncSocket` Objekt.

```
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Parameter

*rSrc*<br/>
Ein Verweis auf einen vorhandenen `CAsyncSocket` Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Kopieren einer vorhandenen `CAsyncSocket` Objekt in ein anderes `CAsyncSocket` Objekt.

##  <a name="operator_socket"></a>  CAsyncSocket::operator SOCKET

Verwenden Sie diesen Operator zum Abrufen der SOCKET-Handle, der die `CAsyncSocket` Objekt.

```
operator SOCKET() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle des dem SOCKET-Objekt. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Sie können das Handle verwenden, um Windows-APIs direkt aufrufen.

##  <a name="receive"></a>  CAsyncSocket::Receive

Rufen Sie diese Memberfunktion zum Empfangen von Daten aus einem Socket.

```
virtual int Receive(
    void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Puffer für die eingehenden Daten.

*nBufLen*<br/>
Die Länge des *LpBuf* in Byte.

*nFlags*<br/>
Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden durch den Socketoptionen bestimmt und die *nFlags* Parameter. Letzteres wird erstellt, durch die Kombination eines der folgenden Werte mit dem C++- **oder** Operator:

- MSG_PEEK einen Blick auf die eingehenden Daten. Die Daten in den Puffer kopiert werden, jedoch nicht aus der Eingabewarteschlange entfernt.

- MSG_OOB Prozess Out-of-Band-Daten.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `Receive` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls SOCKET_ERROR Wert zurückgegeben und ein bestimmten Fehlercode, die durch den Aufruf abgerufen werden kann [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAENOTCONN den Socket ist nicht verbunden.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN der Socket wurde beendet.; Es ist nicht möglich, Sie rufen `Receive` für ein Socket nach `ShutDown` wurde aufgerufen mit *nHow* auf 0 oder 2 festgelegt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und `Receive` Vorgang würde blockieren.

- WSAEMSGSIZE das Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.

- Der Socket nicht mit gebundenen WSAEINVAL `Bind`.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Funktion für verbundene Stream oder Datagrammsockets verwendet und wird verwendet, um die eingehenden Daten lesen.

Für Sockets des Typs SOCK_STREAM wird so viele Informationen wie die derzeit verfügbar bis zur Größe des Puffers angegeben ist, zurückgegeben. Wenn der Socket für Inline-Empfang der Out-of-Band-Daten (Socketoption SO_OOBINLINE) konfiguriert wurde, und Out-of-Band-Daten ungelesene sind, werden nur die Out-of-Band-Daten zurückgegeben. Kann die Anwendung anhand der `IOCtlSIOCATMARK` Option oder [OnOutOfBandData](#onoutofbanddata) zu bestimmen, ob mehr Out-of-Band-Daten bleibt, die gelesen werden.

Für Datagrammsockets werden Daten aus der erste Datagramm, bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der angegebene Puffer ist, der Puffer voll ist, mit dem ersten Teil des Datagramms, überschüssigen Daten in die geht verloren, und `Receive` SOCKET_ERROR Wert mit dem Fehlercode auf WSAEMSGSIZE gibt. Wenn keine eingehenden Daten an den Socket verfügbar ist, wird der Wert SOCKET_ERROR mit dem Fehlercode WSAEWOULDBLOCK festgelegt zurückgegeben. Die [OnReceive](#onreceive) Callback-Funktion kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.

Wenn der Socket vom Typ SOCK_STREAM ist und die Remoteseite die Verbindung ordnungsgemäß heruntergefahren hat, eine `Receive` mit 0 Byte, empfangene sofort abgeschlossen. Wenn die Verbindung zurückgesetzt wurde, eine `Receive` schlägt fehl mit Fehler WSAECONNRESET.

`Receive` sollte nur einmal für jedes Mal aufgerufen werden [CAsyncSocket::OnReceive](#onreceive) aufgerufen wird.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CAsyncSocket::OnReceive](#onreceive).

##  <a name="receivefrom"></a>  CAsyncSocket::ReceiveFrom

Rufen Sie diese Memberfunktion, um ein Datagramm zu empfangen und speichern Sie die Quelladresse in die [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur oder im *rSocketAddress*.

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

*lpBuf*<br/>
Ein Puffer für die eingehenden Daten.

*nBufLen*<br/>
Die Länge des *LpBuf* in Byte.

*rSocketAddress*<br/>
Ein Verweis auf eine `CString` Objekt, das eine gepunktete Anzahl IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf eine "uint", in dem einen Port gespeichert.

*lpSockAddr*<br/>
Ein Zeiger auf eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) -Struktur, die die Quelladresse bei der Rückgabe enthält.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Quelladresse in *LpSockAddr* in Byte.

*nFlags*<br/>
Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden durch den Socketoptionen bestimmt und die *nFlags* Parameter. Letzteres wird erstellt, durch die Kombination eines der folgenden Werte mit dem C++- **oder** Operator:

- MSG_PEEK einen Blick auf die eingehenden Daten. Die Daten in den Puffer kopiert werden, jedoch nicht aus der Eingabewarteschlange entfernt.

- MSG_OOB Prozess Out-of-Band-Daten.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `ReceiveFrom` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls SOCKET_ERROR Wert zurückgegeben und ein bestimmten Fehlercode, die durch den Aufruf abgerufen werden kann `GetLastError`. Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument war ungültig: die *LpSockAddr* Puffer war zu klein für die Peeradresse zu ermöglichen.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- Der Socket nicht mit gebundenen WSAEINVAL `Bind`.

- WSAENOTCONN der Socket ist nicht verbunden (nur SOCK_STREAM).

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN der Socket wurde beendet.; Es ist nicht möglich, Sie rufen `ReceiveFrom` für ein Socket nach `ShutDown` wurde aufgerufen mit *nHow* auf 0 oder 2 festgelegt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und `ReceiveFrom` Vorgang würde blockieren.

- WSAEMSGSIZE das Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Funktion dient zum Lesen von eingehender Daten für einen Socket (möglicherweise verbunden), und erfassen die Adresse, von der die Daten gesendet wurde.

Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::ReceiveFromEx](#receivefromex).

Für Sockets des Typs SOCK_STREAM wird so viele Informationen wie die derzeit verfügbar bis zur Größe des Puffers angegeben ist, zurückgegeben. Wenn der Socket für Inline-Empfang der Out-of-Band-Daten (Socketoption SO_OOBINLINE) konfiguriert wurde, und Out-of-Band-Daten ungelesene sind, werden nur die Out-of-Band-Daten zurückgegeben. Kann die Anwendung anhand der `IOCtlSIOCATMARK` Option oder `OnOutOfBandData` zu bestimmen, ob mehr Out-of-Band-Daten bleibt, die gelesen werden. Die *LpSockAddr* und *LpSockAddrLen* SOCK_STREAM Sockets Parameter werden ignoriert.

Für Datagrammsockets werden Daten aus der erste Datagramm, bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der angegebene Puffer ist, der Puffer voll ist, mit dem ersten Teil der Nachricht, die überzähligen Daten verloren, und `ReceiveFrom` SOCKET_ERROR Wert mit dem Fehlercode auf WSAEMSGSIZE gibt.

Wenn *LpSockAddr* ungleich NULL ist, und der Socket ist vom Typ SOCK_DGRAM, die Netzwerkadresse für den Socket, der die Daten gesendet werden in den entsprechenden kopiert [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur. Der Wert verweist *LpSockAddrLen* auf die Größe dieser Struktur initialisiert wird und bei der Rückgabe an die tatsächliche Größe der dort gespeicherten Adresse geändert wird. Wenn keine eingehenden Daten verfügbar, auf den Socket sind, der `ReceiveFrom` Aufruf wartet auf Daten auf das eingehen, es sei denn, das Socket ist nicht blockierend. In diesem Fall wird der Wert SOCKET_ERROR mit dem Fehlercode WSAEWOULDBLOCK zurückgegeben. Die `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.

Wenn der Socket vom Typ SOCK_STREAM ist und die Remoteseite die Verbindung ordnungsgemäß heruntergefahren hat, eine `ReceiveFrom` mit 0 Byte, empfangene sofort abgeschlossen.

##  <a name="receivefromex"></a>  CAsyncSocket::ReceiveFromEx

Rufen Sie diese Memberfunktion, um ein Datagramm zu empfangen und speichern Sie die Quelladresse in die [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur oder im *rSocketAddress* (verarbeitet IPv6-Adressen).

```
int ReceiveFromEx(
    void* lpBuf,
    int nBufLen,
    CString& rSocketAddress,
    UINT& rSocketPort,
    int nFlags = 0);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Puffer für die eingehenden Daten.

*nBufLen*<br/>
Die Länge des *LpBuf* in Byte.

*rSocketAddress*<br/>
Ein Verweis auf eine `CString` Objekt, das eine gepunktete Anzahl IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf eine "uint", in dem einen Port gespeichert.

*nFlags*<br/>
Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden durch den Socketoptionen bestimmt und die *nFlags* Parameter. Letzteres wird erstellt, durch die Kombination eines der folgenden Werte mit dem C++- **oder** Operator:

- MSG_PEEK einen Blick auf die eingehenden Daten. Die Daten in den Puffer kopiert werden, jedoch nicht aus der Eingabewarteschlange entfernt.

- MSG_OOB Prozess Out-of-Band-Daten.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `ReceiveFromEx` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls SOCKET_ERROR Wert zurückgegeben und ein bestimmten Fehlercode, die durch den Aufruf abgerufen werden kann `GetLastError`. Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT der *LpSockAddrLen* Argument war ungültig: die *LpSockAddr* Puffer war zu klein für die Peeradresse zu ermöglichen.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- Der Socket nicht mit gebundenen WSAEINVAL `Bind`.

- WSAENOTCONN der Socket ist nicht verbunden (nur SOCK_STREAM).

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN der Socket wurde beendet.; Es ist nicht möglich, Sie rufen `ReceiveFromEx` für ein Socket nach `ShutDown` wurde aufgerufen mit *nHow* auf 0 oder 2 festgelegt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und `ReceiveFromEx` Vorgang würde blockieren.

- WSAEMSGSIZE das Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Funktion dient zum Lesen von eingehender Daten für einen Socket (möglicherweise verbunden), und erfassen die Adresse, von der die Daten gesendet wurde.

Diese Funktion ist identisch mit [CAsyncSocket::ReceiveFrom](#receivefrom) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen als auch ältere Protokolle.

Für Sockets des Typs SOCK_STREAM wird so viele Informationen wie die derzeit verfügbar bis zur Größe des Puffers angegeben ist, zurückgegeben. Wenn der Socket für Inline-Empfang der Out-of-Band-Daten (Socketoption SO_OOBINLINE) konfiguriert wurde, und Out-of-Band-Daten ungelesene sind, werden nur die Out-of-Band-Daten zurückgegeben. Kann die Anwendung anhand der `IOCtlSIOCATMARK` Option oder `OnOutOfBandData` zu bestimmen, ob mehr Out-of-Band-Daten bleibt, die gelesen werden. Die *LpSockAddr* und *LpSockAddrLen* SOCK_STREAM Sockets Parameter werden ignoriert.

Für Datagrammsockets werden Daten aus der erste Datagramm, bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der angegebene Puffer ist, der Puffer voll ist, mit dem ersten Teil der Nachricht, die überzähligen Daten verloren, und `ReceiveFromEx` SOCKET_ERROR Wert mit dem Fehlercode auf WSAEMSGSIZE gibt.

Wenn *LpSockAddr* ungleich NULL ist, und der Socket ist vom Typ SOCK_DGRAM, die Netzwerkadresse für den Socket, der die Daten gesendet werden in den entsprechenden kopiert [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur. Der Wert verweist *LpSockAddrLen* auf die Größe dieser Struktur initialisiert wird und bei der Rückgabe an die tatsächliche Größe der dort gespeicherten Adresse geändert wird. Wenn keine eingehenden Daten verfügbar, auf den Socket sind, der `ReceiveFromEx` Aufruf wartet auf Daten auf das eingehen, es sei denn, das Socket ist nicht blockierend. In diesem Fall wird der Wert SOCKET_ERROR mit dem Fehlercode WSAEWOULDBLOCK zurückgegeben. Die `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.

Wenn der Socket vom Typ SOCK_STREAM ist und die Remoteseite die Verbindung ordnungsgemäß heruntergefahren hat, eine `ReceiveFromEx` mit 0 Byte, empfangene sofort abgeschlossen.

##  <a name="send"></a>  CAsyncSocket::Send

Rufen Sie diese Memberfunktion zum Senden von Daten auf einem verbundenen Socket.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Puffer mit den Daten übertragen werden.

*nBufLen*<br/>
Die Länge der Daten in *LpBuf* in Byte.

*nFlags*<br/>
Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden durch den Socketoptionen bestimmt und die *nFlags* Parameter. Letzteres wird erstellt, durch die Kombination eines der folgenden Werte mit dem C++- **oder** Operator:

- MSG_DONTROUTE gibt an, die die Daten nicht unterliegt routing werden sollen. Ein Anbieter der Windows-Sockets können dieses Flag ignoriert werden sollen.

- MSG_OOB Out-of-Band-Daten senden (nur SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `Send` gibt die Gesamtzahl der Zeichen gesendet zurück. (Beachten Sie, dass dies weniger als die Zahl, die *nBufLen*.) Andernfalls SOCKET_ERROR Wert zurückgegeben und ein bestimmten Fehlercode, die durch den Aufruf abgerufen werden kann [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEACCES der angeforderten Adresse ist eine Broadcastadresse allerdings das entsprechende Flag nicht festgelegt wurde.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAEFAULT der *LpBuf* Argument ist nicht in einem gültigen Teil des benutzeradressraums.

- WSAENETRESET die Verbindung muss zurückgesetzt werden, da die Windows Sockets-Implementierung, die sie gelöscht.

- WSAENOBUFS der Windows Sockets-Implementierung meldet einen Deadlock Puffer.

- WSAENOTCONN den Socket ist nicht verbunden.

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN der Socket wurde beendet.; Es ist nicht möglich, Sie rufen `Send` für ein Socket nach `ShutDown` wurde aufgerufen mit *nHow* auf 1 oder 2 festgelegt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und der angeforderte Vorgang würde blockieren.

- WSAEMSGSIZE den Socket ist vom Typ SOCK_DGRAM; das Datagramm ist größer als die maximal unterstützte, von der Windows Sockets-Implementierung.

- Der Socket nicht mit gebundenen WSAEINVAL `Bind`.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.

### <a name="remarks"></a>Hinweise

`Send` wird verwendet, ausgehende Daten auf dem verbundenen Stream oder Datagrammsockets geschrieben. Für Datagrammsockets, Vorsicht, nicht zu überschreiten die maximale Größe der IP-Paket von der zugrunde liegenden Subnetzen, die von angegeben wird die `iMaxUdpDg` Element in der [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) vom zurückgegebene Struktur `AfxSocketInit`. Wenn die Daten zu lang, um das zugrunde liegende Protokoll atomar zu durchlaufen, den Fehler WSAEMSGSIZE zurückgegeben über `GetLastError`, und keine Daten übertragen.

Beachten Sie, die für ein Datagramm socket vom erfolgreichen Abschluss einer `Send` nicht, dass die Daten erfolgreich übermittelt wurde.

Auf `CAsyncSocket` Objekte des Typs SOCK_STREAM, die Anzahl der geschriebenen Bytes kann zwischen 1 und die erforderliche Mindestlänge, je nach Verfügbarkeit der Puffer auf den lokalen und Fremdschlüssel Hosts sein.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CAsyncSocket::OnSend](#onsend).

##  <a name="sendto"></a>  Einsatz

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

*lpBuf*<br/>
Ein Puffer mit den Daten übertragen werden.

*nBufLen*<br/>
Die Länge der Daten in *LpBuf* in Byte.

*nHostPort*<br/>
Der Port, der die Socket-Anwendung angibt.

*lpszHostAddress*<br/>
Die Netzwerkadresse für den Socket, der mit dem dieses Objekt verbunden ist: einen Computernamen ein, z. B. "ftp.microsoft.com" oder eine durch Punkte getrennte Zahl wie z. B. "128.56.22.8".

*nFlags*<br/>
Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden durch den Socketoptionen bestimmt und die *nFlags* Parameter. Letzteres wird erstellt, durch die Kombination eines der folgenden Werte mit dem C++- **oder** Operator:

- MSG_DONTROUTE gibt an, die die Daten nicht unterliegt routing werden sollen. Ein Anbieter der Windows-Sockets können dieses Flag ignoriert werden sollen.

- MSG_OOB Out-of-Band-Daten senden (nur SOCK_STREAM).

*lpSockAddr*<br/>
Ein Zeiger auf eine [SOCKADDR](/windows/desktop/winsock/sockaddr-2) -Struktur, die die Adresse des Ziel-Sockets enthält.

*nSockAddrLen*<br/>
Die Länge der Adresse im *LpSockAddr* in Byte.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `SendTo` gibt die Gesamtzahl der Zeichen gesendet zurück. (Beachten Sie, dass dies weniger als die Zahl, die *nBufLen*.) Andernfalls SOCKET_ERROR Wert zurückgegeben und ein bestimmten Fehlercode, die durch den Aufruf abgerufen werden kann [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEACCES der angeforderten Adresse ist eine Broadcastadresse allerdings das entsprechende Flag nicht festgelegt wurde.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAEFAULT der *LpBuf* oder *LpSockAddr* Parameter sind nicht Teil des benutzeradressraums, oder die *LpSockAddr* Argument ist zu klein ist (kleiner als die Größe von einem [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur).

- WSAEINVAL der Hostname ist ungültig.

- WSAENETRESET die Verbindung muss zurückgesetzt werden, da die Windows Sockets-Implementierung, die sie gelöscht.

- WSAENOBUFS der Windows Sockets-Implementierung meldet einen Deadlock Puffer.

- WSAENOTCONN der Socket ist nicht verbunden (nur SOCK_STREAM).

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN der Socket wurde beendet.; Es ist nicht möglich, Sie rufen `SendTo` für ein Socket nach `ShutDown` wurde aufgerufen mit *nHow* auf 1 oder 2 festgelegt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und der angeforderte Vorgang würde blockieren.

- WSAEMSGSIZE den Socket ist vom Typ SOCK_DGRAM; das Datagramm ist größer als die maximal unterstützte, von der Windows Sockets-Implementierung.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.

- WSAEADDRNOTAVAIL die angegebene Adresse ist nicht verfügbar, auf dem lokalen Computer.

- NICHT-Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.

- Zieladresse WSAEDESTADDRREQ A ist erforderlich.

- WSAENETUNREACH kann nicht von diesem Host zu diesem Zeitpunkt das Netzwerk erreicht werden.

### <a name="remarks"></a>Hinweise

`SendTo` in-Datagramm oder den Stream-Sockets verwendet wird, und wird verwendet, um ausgehende Daten für einen Socket zu schreiben. Für Datagrammsockets, Vorsicht, nicht zu überschreiten die maximale Größe der IP-Paket von der zugrunde liegenden Subnetzen, die von angegeben wird die `iMaxUdpDg` Element in der [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) Struktur ausgefüllt, indem [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Wenn die Daten zu lang, um das zugrunde liegende Protokoll atomar übergeben, der Fehler WSAEMSGSIZE wird zurückgegeben, und keine Daten übertragen.

Beachten Sie, dass vom erfolgreichen Abschluss einer `SendTo` nicht, dass die Daten erfolgreich übermittelt wurde.

`SendTo` wird nur für einen Socket SOCK_DGRAM verwendet, um ein Datagramm an einen bestimmten Socket identifizierte senden die *LpSockAddr* Parameter.

Senden Sie eine Übertragung (auf einer SOCK_DGRAM nur), die Adresse in der *LpSockAddr* Parameter sollten erstellt werden, die spezielle IP-Adresse INADDR_BROADCAST (definiert in der Windows Sockets-Headerdatei WINSOCK. H) zusammen mit der gewünschten Portnummer. Oder, wenn Sie die *LpszHostAddress* Parameter NULL ist, der Socket für die Übertragung konfiguriert ist. Es wird im Allgemeinen davon abgeraten, für ein Datagramm broadcast, um die Größe nicht überschreiten, in denen Fragmentierung auftreten kann, was bedeutet, dass der Datenteil für das Datagramm (mit Ausnahme von Headern) 512 Byte nicht übersteigen darf.

Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::SendToEx](#sendtoex).

##  <a name="sendtoex"></a>  CAsyncSocket::SendToEx

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

*lpBuf*<br/>
Ein Puffer mit den Daten übertragen werden.

*nBufLen*<br/>
Die Länge der Daten in *LpBuf* in Byte.

*nHostPort*<br/>
Der Port, der die Socket-Anwendung angibt.

*lpszHostAddress*<br/>
Die Netzwerkadresse für den Socket, der mit dem dieses Objekt verbunden ist: einen Computernamen ein, z. B. "ftp.microsoft.com" oder eine durch Punkte getrennte Zahl wie z. B. "128.56.22.8".

*nFlags*<br/>
Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion werden durch den Socketoptionen bestimmt und die *nFlags* Parameter. Letzteres wird erstellt, durch die Kombination eines der folgenden Werte mit dem C++- **oder** Operator:

- MSG_DONTROUTE gibt an, die die Daten nicht unterliegt routing werden sollen. Ein Anbieter der Windows-Sockets können dieses Flag ignoriert werden sollen.

- MSG_OOB Out-of-Band-Daten senden (nur SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `SendToEx` gibt die Gesamtzahl der Zeichen gesendet zurück. (Beachten Sie, dass dies weniger als die Zahl, die *nBufLen*.) Andernfalls SOCKET_ERROR Wert zurückgegeben und ein bestimmten Fehlercode, die durch den Aufruf abgerufen werden kann [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEACCES der angeforderten Adresse ist eine Broadcastadresse allerdings das entsprechende Flag nicht festgelegt wurde.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAEFAULT der *LpBuf* oder *LpSockAddr* Parameter sind nicht Teil des benutzeradressraums, oder die *LpSockAddr* Argument ist zu klein ist (kleiner als die Größe von einem [SOCKADDR](/windows/desktop/winsock/sockaddr-2) Struktur).

- WSAEINVAL der Hostname ist ungültig.

- WSAENETRESET die Verbindung muss zurückgesetzt werden, da die Windows Sockets-Implementierung, die sie gelöscht.

- WSAENOBUFS der Windows Sockets-Implementierung meldet einen Deadlock Puffer.

- WSAENOTCONN der Socket ist nicht verbunden (nur SOCK_STREAM).

- WSAENOTSOCK Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN der Socket wurde beendet.; Es ist nicht möglich, Sie rufen `SendToEx` für ein Socket nach `ShutDown` wurde aufgerufen mit *nHow* auf 1 oder 2 festgelegt.

- WSAEWOULDBLOCK der Socket markiert ist nicht als blockierend und der angeforderte Vorgang würde blockieren.

- WSAEMSGSIZE den Socket ist vom Typ SOCK_DGRAM; das Datagramm ist größer als die maximal unterstützte, von der Windows Sockets-Implementierung.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.

- WSAEADDRNOTAVAIL die angegebene Adresse ist nicht verfügbar, auf dem lokalen Computer.

- NICHT-Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.

- Zieladresse WSAEDESTADDRREQ A ist erforderlich.

- WSAENETUNREACH kann nicht von diesem Host zu diesem Zeitpunkt das Netzwerk erreicht werden.

### <a name="remarks"></a>Hinweise

Diese Methode ist identisch mit [Einsatz](#sendto) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen als auch ältere Protokolle.

`SendToEx` in-Datagramm oder den Stream-Sockets verwendet wird, und wird verwendet, um ausgehende Daten für einen Socket zu schreiben. Für Datagrammsockets, Vorsicht, nicht zu überschreiten die maximale Größe der IP-Paket von der zugrunde liegenden Subnetzen, die von angegeben wird die `iMaxUdpDg` Element in der [WSADATA](/windows/desktop/api/winsock2/ns-winsock2-wsadata) Struktur ausgefüllt, indem [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Wenn die Daten zu lang, um das zugrunde liegende Protokoll atomar übergeben, der Fehler WSAEMSGSIZE wird zurückgegeben, und keine Daten übertragen.

Beachten Sie, dass vom erfolgreichen Abschluss einer `SendToEx` nicht, dass die Daten erfolgreich übermittelt wurde.

`SendToEx` wird nur für einen Socket SOCK_DGRAM verwendet, um ein Datagramm an einen bestimmten Socket identifizierte senden die *LpSockAddr* Parameter.

Senden Sie eine Übertragung (auf einer SOCK_DGRAM nur), die Adresse in der *LpSockAddr* Parameter sollten erstellt werden, die spezielle IP-Adresse INADDR_BROADCAST (definiert in der Windows Sockets-Headerdatei WINSOCK. H) zusammen mit der gewünschten Portnummer. Oder, wenn Sie die *LpszHostAddress* Parameter NULL ist, der Socket für die Übertragung konfiguriert ist. Es wird im Allgemeinen davon abgeraten, für ein Datagramm broadcast, um die Größe nicht überschreiten, in denen Fragmentierung auftreten kann, was bedeutet, dass der Datenteil für das Datagramm (mit Ausnahme von Headern) 512 Byte nicht übersteigen darf.

##  <a name="setsockopt"></a>  CAsyncSocket::SetSockOpt

Rufen Sie diese Memberfunktion zum Festlegen einer Socketoption.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parameter

*nOptionName*<br/>
Die Socketoption für die der Wert festgelegt werden.

*lpOptionValue*<br/>
Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option angegeben wird.

*nOptionLen*<br/>
Die Größe der *LpOptionValue* Puffers in Byte.

*nLevel*<br/>
Die Ebene, an der die Option definiert ist; die einzige unterstützte Grade sind SOL_SOCKET und IPPROTO_TCP.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEFAULT *LpOptionValue* befindet sich nicht in einem gültigen Teil des Adressraums.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAEINVAL *nLevel* ist ungültig, oder die Informationen in *LpOptionValue* ist ungültig.

- WSAENETRESET Verbindung wurde überschritten, wenn SO_KEEPALIVE festgelegt ist.

- WSAENOPROTOOPT die Option ist unbekannt oder nicht unterstützt. Insbesondere wird SO_BROADCAST für Sockets des Typs SOCK_STREAM, beim SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER und SO_OOBINLINE werden nicht unterstützt für Sockets des Typs SOCK_DGRAM nicht unterstützt.

- WSAENOTCONN Verbindung wurde zurückgesetzt, wenn SO_KEEPALIVE festgelegt ist.

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

`SetSockOpt` Legt den aktuellen Wert für einen Socket-Option, einen Socket eines beliebigen Typs, in einem beliebigen Zustand zugeordnet. Obwohl Optionen auf mehreren Ebenen von Protokoll vorhanden sind, definiert dieser Spezifikation nur die Optionen, die auf der obersten "Socket"-Ebene vorhanden sind. Optionen beeinflussen die Socketvorgänge, z. B. an, ob beschleunigte Daten dem normalen Datenstream, empfangen werden, ob Nachrichten auf dem Socket gesendet werden können und so weiter.

Es gibt zwei Arten von Socket-Optionen aus: Boolesche Optionen aktivieren oder Deaktivieren einer Funktion oder ein Verhalten, und Optionen zur Verfügung, die ein ganzzahliger Wert oder eine Struktur erforderlich. So aktivieren Sie eine boolesche Option, *LpOptionValue* verweist auf eine ganze Zahl ungleich NULL. So deaktivieren Sie die Option *LpOptionValue* verweist auf eine ganze Zahl gleich 0 (null). *nOptionLen* muss `sizeof(BOOL)` für boolesche Optionen. Informationen zu anderen Optionen *LpOptionValue* verweist auf die ganze Zahl oder eine Struktur, die den gewünschten Wert für die Option enthält und *nOptionLen* ist die Länge der ganze Zahl oder Struktur.

SO_LINGER steuert die Aktion ausgeführt, wenn nicht gesendete Daten für einen Socket in der Warteschlange befindet und die `Close` Funktion wird aufgerufen, um den Socket schließen.

Standardmäßig kann ein Socket kann nicht gebunden werden (finden Sie unter [binden](#bind)) auf eine lokale Adresse bereits verwendet wird. Gelegentlich kann allerdings es wünschenswert, eine Adresse auf diese Weise "wiederzuverwenden" sein. Da jede Verbindung durch die Kombination aus lokalen und remote Adressen eindeutig identifiziert wird, besteht kein Problem mit zwei Sockets, die an die gleiche lokale Adresse gebunden werden, solange die remote-Adressen unterscheiden.

Um die Windows Sockets-Implementierung zu informieren, die eine `Bind` Aufruf an einem Socket sollte nicht als unzulässig erklärt werden, da die gewünschte Adresse bereits von einem anderen Socket verwendet wird, die Anwendung sollte die Option für den Socket SO_REUSEADDR für den Socket vor dem Ausstellen Festlegen der `Bind` aufrufen. Beachten Sie, dass die Option nur zum Zeitpunkt der interpretiert wird die `Bind` aufrufen: daher ist es nicht erforderlich (aber ungefährlich) die Option für einen Socket festzulegende handelt es sich nicht an eine vorhandene Adresse gebunden werden und festlegen, oder die Option nach dem Zurücksetzen der `Bind` Aufruf hat keine Auswirkung auf diesem oder einen anderen Socket.

Die Windows Sockets-Implementierung die Verwendung von "Keep-alive-Pakete (TCP, Transmission Control Protocol)-Verbindungen aktivieren, indem die Socketoption SO_KEEPALIVE einschalten kann eine Anwendung anfordern. Eine Windows Sockets-Implementierung muss nicht die Verwendung von Keep-Alives unterstützen: Wenn dies der Fall ist, wird die genaue Semantik sind jedoch sollte dem RFC 1122, Abschnitt 4.2.3.6: "Anforderungen für Internethosts – Kommunikationsschichten." Wenn Sie eine Verbindung getrennt wird, als Ergebnis von "Keep-Alives" Fehlercode: WSAENETRESET zurückgegeben keine Aufrufe in Bearbeitung auf dem Socket, und alle nachfolgenden Aufrufe schlagen mit WSAENOTCONN.

Die Option TCP_NODELAY deaktiviert den Nagle-Algorithmus. Der Nagle-Algorithmus wird zum Reduzieren der Anzahl von kleine Pakete, die von einem Host gesendet werden, durch die Pufferung unbestätigten Senden von Daten, bis ein Paket in voller Größe gesendet werden kann. Allerdings für einige Anwendungen kann diesen Algorithmus die Leistung beeinträchtigen, und TCP_NODELAY können verwendet werden, um diese Funktion zu deaktivieren. Anwendungsentwickler sollten TCP_NODELAY nicht festgelegt, es sei denn, die Auswirkungen dieser Vorgehensweise nachvollziehbarer und gewünschten, also da festlegen TCP_NODELAY erhebliche negative Auswirkungen auf die netzwerkleistung aufweisen kann. TCP_NODELAY ist die einzige unterstützte Socketoption Ebene IPPROTO_TCP; verwendet Alle anderen Optionen verwenden Sie Stufe SOL_SOCKET.

Einigen Implementierungen von Windows Sockets-Netzteils Debuginformationen ausgegeben, wenn von einer Anwendung die SO_DEBUG-Option festgelegt ist.

Die folgenden Optionen werden unterstützt, für die `SetSockOpt`. Den Typ identifiziert den Typ der Daten behoben, indem *LpOptionValue*.

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|Ermöglicht die Übertragung von Nachrichten für den Socket.|
|SO_DEBUG|BOOL|Zeichnet Debuginformationen auf.|
|SO_DONTLINGER|BOOL|Blockieren keine `Close` warten nicht gesendeten Daten gesendet werden sollen. Das Festlegen dieser Option entspricht dem Festlegen von SO_LINGER mit `l_onoff` auf 0 (null) festgelegt.|
|SO_DONTROUTE|BOOL|Nicht weiterleiten: direkt an die Schnittstelle gesendet.|
|SO_KEEPALIVE|BOOL|Senden von Keep-Alives.|
|SO_LINGER|`struct LINGER`|Wird verzögert, `Close` Wenn nicht gesendete Daten vorhanden ist.|
|SO_OOBINLINE|BOOL|Empfangen von Out-of-Band-Daten im normalen Datenstream.|
|SO_RCVBUF|**int**|Geben Sie die Puffergröße für empfängt.|
|SO_REUSEADDR|BOOL|Ermöglichen des Sockets, auf die in eine Adresse gebunden werden, das bereits verwendet wird. (Finden Sie unter [binden](#bind).)|
|SO_SNDBUF|**int**|Geben Sie die Puffergröße für Sendevorgänge an.|
|TCP_NODELAY|BOOL|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|

Optionen für die Berkeley Software Distribution (BSD) nicht unterstützt für `SetSockOpt` sind:

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Socket überwacht|
|SO_ERROR|**int**|Status "Fehler" abrufen und löschen.|
|SO_RCVLOWAT|**int**|Erhalten Sie die untere Grenze.|
|SO_RCVTIMEO|**int**|Timeout des Empfangsvorgangs|
|SO_SNDLOWAT|**int**|Senden Sie die untere Grenze.|
|SO_SNDTIMEO|**int**|Timeout des Sendevorgangs.|
|SO_TYPE|**int**|Der Typ des Sockets.|
|IP_OPTIONS||SET-Optionen-Feld in den IP-Header.|

##  <a name="shutdown"></a>  CAsyncSocket::ShutDown

Anruf sendet diese Member-Funktion zu deaktivieren, oder beides für den Socket.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Parameter

*nHow*<br/>
Ein Flag, das beschreibt, welche Typen von Vorgängen wird nicht mehr zulässig, mit der folgenden Enumerationswerte:

- **receives = 0**

- **sends = 1**

- **both = 2**

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:

- WSANOTINITIALISED A erfolgreich [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.

- WSAENETDOWN der Windows Sockets-Implementierung hat erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.

- WSAEINVAL *nHow* ist ungültig.

- A "WSAEINPROGRESS" zurück, die blockierender Windows Sockets-Vorgang ausgeführt wird.

- WSAENOTCONN der Socket ist nicht verbunden (nur SOCK_STREAM).

- WSAENOTSOCK Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

`ShutDown` wird für alle Typen von Sockets verwendet, um Empfang, Übertragung oder beides deaktivieren. Wenn *nHow* gleich 0 ist, auf die nachfolgenden erhält der Socket wird als unzulässig erklärt werden. Dies hat keine Auswirkungen auf den unteren Protokollschichten.

Für Protokoll TCP (Transmission Control), die TCP-Fenster wird nicht geändert und die eingehende Daten werden (aber nicht bestätigt) akzeptiert werden, bis das Fenster erreicht wird. Für die User Datagram Protocol (UDP), werden eingehende Datagramme akzeptiert und in die Warteschlange eingereiht. In keinem Fall wird ein ICMP-Paket Fehler generiert. Wenn *nHow* ist 1, nachfolgende sendet sind nicht zulässig. Für TCP-Sockets wird eine FIN gesendet werden. Festlegen von *nHow* auf 2 deaktiviert Sie beide senden und empfangen werden, wie oben beschrieben.

Beachten Sie, dass `ShutDown` ist nicht schließen der Socket, und klicken Sie auf Ressourcen, die an den Socket angefügt wird nicht reserviert, bis `Close` aufgerufen wird. Eine Anwendung sollten nicht verlassen, können einen Socket wiederverwendet werden, nachdem es heruntergefahren wurde. Eine Windows Sockets-Implementierung ist vor allem nicht erforderlich, für die Unterstützung von `Connect` auf solche einem Socket.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CAsyncSocket::OnReceive](#onreceive).

##  <a name="socket"></a>  CASyncSocket::Socket

Reserviert ein Sockethandle.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>Parameter

*nSocketType*<br/>
Gibt an, `SOCK_STREAM` oder `SOCK_DGRAM`.

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.

- `FD_READ`: Bereitschaft zum Lesen benachrichtigt werden soll.

- `FD_WRITE`: Bereitschaft für das Schreiben von benachrichtigt werden soll.

- `FD_OOB`: Der Eingang der Out-of-Band-Daten benachrichtigt werden soll.

- `FD_ACCEPT`: Benachrichtigung über eingehende Verbindungen empfangen werden soll.

- `FD_CONNECT`: Abgeschlossene Verbindung benachrichtigt werden soll.

- `FD_CLOSE`: Socket-Abschluss benachrichtigt werden soll.

*nProtocolType*<br/>
Protokoll, das mit der Socket verwendet werden, die spezifisch für die angegebene Adressfamilie ist.

*nAddressFormat*<br/>
Familie Spezifikation zu beheben.

### <a name="return-value"></a>Rückgabewert

Gibt `TRUE` bei Erfolg bzw. `FALSE` bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode weist ein Socket-Handle. Wird nicht aufgerufen [CAsyncSocket::Bind](#bind) zum Binden des Sockets an eine bestimmte Adresse, daher Sie zum Aufrufen müssen `Bind` später zu einer bestimmten Adresse der Socket gebunden werden. Sie können [CAsyncSocket::SetSockOpt](#setsockopt) die Socketoption festlegen, bevor er gebunden ist.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CSocket-Klasse](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)
