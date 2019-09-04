---
title: CAsyncSocket-Klasse
ms.date: 09/03/2019
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
ms.openlocfilehash: 4e14052d400268a8852298113ba9b51fda713dc8
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273792"
---
# <a name="casyncsocket-class"></a>CAsyncSocket-Klasse

Stellt einen Windows-Socket dar – einen Endpunkt der Netzwerkkommunikation.

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
|[CAsyncSocket::Accept](#accept)|Akzeptiert eine Verbindung im Socket.|
|[CAsyncSocket::AsyncSelect](#asyncselect)|Fordert die Ereignis Benachrichtigung für den Socket an.|
|[CAsyncSocket::Attach](#attach)|Fügt ein Sockethandle an `CAsyncSocket` ein-Objekt an.|
|[CAsyncSocket::Bind](#bind)|Ordnet dem Socket eine lokale Adresse zu.|
|[CAsyncSocket:: Close](#close)|Schließt den Socket.|
|[CAsyncSocket:: Connect](#connect)|Stellt eine Verbindung mit einem peersocket her.|
|[CAsyncSocket::Create](#create)|Erstellt einen Socket.|
|[CAsyncSocket::Detach](#detach)|Trennt ein Sockethandle von einem `CAsyncSocket` -Objekt.|
|[CAsyncSocket:: FromHandle](#fromhandle)|Gibt einen Zeiger auf ein `CAsyncSocket` -Objekt zurück, wenn ein Sockethandle angegeben ist.|
|[CAsyncSocket::GetLastError](#getlasterror)|Ruft den Fehlerstatus für den letzten fehlgeschlagenen Vorgang ab.|
|[CAsyncSocket::GetPeerName](#getpeername)|Ruft die Adresse des peersockets ab, mit dem der Socket verbunden ist.|
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Ruft die Adresse des peersockets ab, mit dem der Socket verbunden ist (verarbeitet IPv6-Adressen).|
|[CAsyncSocket::GetSockName](#getsockname)|Ruft den lokalen Namen für einen Socket ab.|
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Ruft den lokalen Namen für einen Socket ab (verarbeitet IPv6-Adressen).|
|[CAsyncSocket::GetSockOpt](#getsockopt)|Ruft eine Socketoption ab.|
|[CAsyncSocket::IOCtl](#ioctl)|Steuert den Modus des Sockets.|
|[CAsyncSocket::Listen](#listen)|Richtet einen Socket zum lauschen auf eingehende Verbindungsanforderungen ein.|
|[CAsyncSocket::Receive](#receive)|Empfängt Daten vom Socket.|
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Empfängt ein Datagramm und speichert die Quelladresse.|
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Empfängt ein Datagramm und speichert die Quelladresse (verarbeitet IPv6-Adressen).|
|[CAsyncSocket::Send](#send)|Sendet Daten an einen verbundenen Socket.|
|[CAsyncSocket::SendTo](#sendto)|Sendet Daten an ein bestimmtes Ziel.|
|[CAsyncSocket::SendToEx](#sendtoex)|Sendet Daten an ein bestimmtes Ziel (verarbeitet IPv6-Adressen).|
|[CAsyncSocket::SetSockOpt](#setsockopt)|Legt eine Socketoption fest.|
|[CAsyncSocket::ShutDown](#shutdown)|Deaktiviert und/oder `Receive` Ruft für den Socket auf. `Send`|
|[CASyncSocket::Socket](#socket)|Ordnet ein Sockethandle zu.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::OnAccept](#onaccept)|Benachrichtigt einen lauschenden Socket, dass ausstehende Verbindungsanforderungen durch Aufrufen `Accept`von akzeptiert werden können.|
|[CAsyncSocket::OnClose](#onclose)|Benachrichtigt einen Socket, dass der verbundene Socket geschlossen wurde.|
|[CAsyncSocket::OnConnect](#onconnect)|Benachrichtigt einen Verbindungs-Socket, dass der Verbindungsversuch abgeschlossen ist, ob erfolgreich oder fehlerhaft.|
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Benachrichtigt einen empfangenden Socket, dass im Socket Out-of-Band-Daten gelesen werden müssen, normalerweise eine dringende Nachricht.|
|[CAsyncSocket::OnReceive](#onreceive)|Benachrichtigt einen lauschenden Socket, dass Daten durch Aufrufen `Receive`von abgerufen werden müssen.|
|[CAsyncSocket::OnSend](#onsend)|Benachrichtigt einen Socket, dass er Daten senden kann, indem `Send`aufgerufen wird.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket:: Operator =](#operator_eq)|Weist einem- `CAsyncSocket` Objekt einen neuen Wert zu.|
|[CAsyncSocket:: Operator Socket](#operator_socket)|Verwenden Sie diesen Operator, um das Sockethandle `CAsyncSocket` des-Objekts abzurufen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAsyncSocket::m_hSocket](#m_hsocket)|Gibt das an dieses `CAsyncSocket` Objekt angefügte Sockethandle an.|

## <a name="remarks"></a>Hinweise

Die `CAsyncSocket` -Klasse kapselt die API der Windows-Socket-Funktionen und stellt eine objektorientierte Abstraktion für Programmierer bereit, die Windows Sockets in Verbindung mit MFC verwenden möchten.

Diese Klasse basiert auf der Annahme, dass Sie die Netzwerkkommunikation verstehen. Sie sind verantwortlich für die Behandlung von Blockierungen, Byte Reihen folgen unterschieden und Konvertierungen zwischen Unicode-und MBCS-Zeichen folgen (Multibytezeichen-Zeichensatz). Wenn Sie eine benutzerfreundliche Schnittstelle wünschen, die diese Probleme für Sie verwaltet, finden Sie weitere Informationen unter Class [CSocket](../../mfc/reference/csocket-class.md).

Um ein `CAsyncSocket` -Objekt zu verwenden, rufen Sie seinen Konstruktor auf, und rufen Sie dann die [Create](#create) -Funktion auf `SOCKET`, um das zugrunde liegende Sockethandle (Type) zu erstellen Bei einem Serversocket wird die Funktion zum [lauschen](#listen) von Membern aufgerufen, und für einen Clientsocket wird die [Connect](#connect) -Member-Funktion aufgerufen. Der Server Socket sollte beim Empfangen einer Verbindungsanforderung die [Accept](#accept) -Funktion aufruft. Verwenden Sie die `CAsyncSocket` verbleibenden Funktionen, um die Kommunikation zwischen Sockets auszuführen. Wenn der Vorgang abgeschlossen ist `CAsyncSocket` , zerstören Sie das Objekt, wenn es auf dem Heap erstellt wurde. der Dekonstruktor ruft automatisch die [Close](#close) -Funktion auf. Der Socket-Datentyp wird im Artikel [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).

> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC-Anwendung verwenden `AfxSocketInit` , müssen Sie in jedem Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. Standardmäßig `AfxSocketInit` wird nur im primären Thread aufgerufen.

Weitere Informationen finden [Sie unter Windows Sockets: Mithilfe der CAsyncSocket](../../mfc/windows-sockets-using-class-casyncsocket.md) -Klasse und verwandter Artikel, sowie der [Windows Sockets 2-API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CAsyncSocket`

## <a name="requirements"></a>Anforderungen

**Header:** AfxSock. h

##  <a name="accept"></a>CAsyncSocket:: Accept

Diese Member-Funktion wird aufgerufen, um eine Verbindung für einen Socket zu akzeptieren.

```
virtual BOOL Accept(
    CAsyncSocket& rConnectedSocket,
    SOCKADDR* lpSockAddr = NULL,
    int* lpSockAddrLen = NULL);
```

### <a name="parameters"></a>Parameter

*rConnectedSocket*<br/>
Ein Verweis, der einen neuen Socket identifiziert, der für die Verbindung verfügbar ist.

*lpSockAddr*<br/>
Ein Zeiger auf eine [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die die Adresse des Verbindungs-Sockets erhält, wie im Netzwerk bekannt. Das genaue Format des *lpsockaddr* -Arguments wird von der Adressfamilie bestimmt, die beim Erstellen des Sockets festgelegt wurde. Wenn *lpsockaddr* und/oder *lpsockaddrlen* gleich NULL sind, werden keine Informationen über die Remote Adresse des akzeptierten Sockets zurückgegeben.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Adresse in *lpsockaddr* (in Bytes). Die *lpsockaddrlen* ist ein Value-Result-Parameter: er sollte anfänglich den Speicherplatz enthalten, auf den *lpsockaddr*verweist. bei der Rückgabe enthält Sie die tatsächliche Länge der zurückgegebenen Adresse (in Bytes).

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument ist zu klein (weniger als die Größe einer [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur).

- WSAEINPROGRESS ein blockierender Windows Sockets-Befehl wird ausgeführt.

- Wsaabval `Listen` wurde nicht vor dem akzeptieren aufgerufen.

- Wsaemfile die Warteschlange ist nach dem Eintrag leer, um akzeptiert zu werden, und es sind keine Deskriptoren verfügbar.

- WSAENOBUFS ist kein Pufferspeicher verfügbar.

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP der Socket, auf den verwiesen wird, ist kein Typ, der Verbindungs orientierten Dienst unterstützt.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend gekennzeichnet, und es sind keine Verbindungen vorhanden, die akzeptiert werden können.

### <a name="remarks"></a>Hinweise

Diese Routine extrahiert die erste Verbindung in der Warteschlange für ausstehende Verbindungen, erstellt einen neuen Socket mit denselben Eigenschaften wie dieser Socket und fügt ihn an *rconnectedsocket*an. Wenn keine ausstehenden Verbindungen in der Warteschlange vorhanden sind `Accept` , wird NULL `GetLastError` zurückgegeben, und es wird ein Fehler zurückgegeben. Der akzeptierte Socket ( *rconnectedsocket)* kann nicht verwendet werden, um mehr Verbindungen zu akzeptieren. Der ursprüngliche Socket bleibt geöffnet und lauscht an.

Das Argument *lpsockaddr* ist ein Ergebnis Parameter, der mit der Adresse des Verbindungs-Sockets ausgefüllt wird, wie es der Kommunikationsschicht bekannt ist. `Accept`wird mit verbindungsbasierten Socketypen wie z. b. SOCK_STREAM verwendet.

##  <a name="asyncselect"></a>CAsyncSocket:: ASyncSelect

Mit dieser Member-Funktion können Sie die Ereignis Benachrichtigung für einen Socket anfordern.

```
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parameter

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerk Ereignissen angibt, an denen die Anwendung interessiert ist.

- FD_READ möchte eine Benachrichtigung über die Bereitschaft zum Lesen erhalten.

- FD_WRITE möchten eine Benachrichtigung erhalten, wenn Daten zum Lesen verfügbar sind.

- FD_OOB möchte eine Benachrichtigung über die Ankunft von Out-of-Band-Daten erhalten.

- FD_ACCEPT möchte Benachrichtigungen über eingehende Verbindungen erhalten.

- FD_CONNECT möchten eine Benachrichtigung über Verbindungs Ergebnisse erhalten.

- FD_CLOSE möchte eine Benachrichtigung erhalten, wenn ein Socket von einem Peer geschlossen wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEINVAL gibt an, dass einer der angegebenen Parameter ungültig war.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

### <a name="remarks"></a>Hinweise

Diese Funktion wird verwendet, um anzugeben, welche MFC-Rückruf Benachrichtigungsfunktionen für den Socket aufgerufen werden. `AsyncSelect`legt diesen Socket automatisch auf den nicht blockierenden Modus fest. Weitere Informationen finden Sie im Artikel [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="attach"></a>CAsyncSocket:: Attach

Mit dieser Member-Funktion können Sie das *hsocket* -Handle `CAsyncSocket` an ein-Objekt anfügen.

```
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```

### <a name="parameters"></a>Parameter

*hSocket*<br/>
Enthält ein Handle für einen Socket.

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerk Ereignissen angibt, an denen die Anwendung interessiert ist.

- FD_READ möchte eine Benachrichtigung über die Bereitschaft zum Lesen erhalten.

- FD_WRITE möchten eine Benachrichtigung erhalten, wenn Daten zum Lesen verfügbar sind.

- FD_OOB möchte eine Benachrichtigung über die Ankunft von Out-of-Band-Daten erhalten.

- FD_ACCEPT möchte Benachrichtigungen über eingehende Verbindungen erhalten.

- FD_CONNECT möchten eine Benachrichtigung über Verbindungs Ergebnisse erhalten.

- FD_CLOSE möchte eine Benachrichtigung erhalten, wenn ein Socket von einem Peer geschlossen wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich null, wenn die Funktion erfolgreich ist.

### <a name="remarks"></a>Hinweise

Das Sockethandle wird im [m_hSocket](#m_hsocket) -Datenmember des Objekts gespeichert.

##  <a name="bind"></a>CAsyncSocket:: Bind

Mit dieser Member-Funktion wird dem Socket eine lokale Adresse zugeordnet.

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
Der Port, der die socketanwendung identifiziert.

*lpszSocketAddress*<br/>
Die Netzwerkadresse, eine gepunktete Zahl, z. b. "128.56.22.8". Durch das übergeben der NULL-Zeichenfolge für `CAsyncSocket` diesen Parameter wird angegeben, dass die Instanz auf allen Netzwerkschnittstellen auf Client Aktivitäten lauschen soll.

*lpSockAddr*<br/>
Ein Zeiger auf eine [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die die Adresse enthält, die diesem Socket zugewiesen werden soll.

*nSockAddrLen*<br/>
Die Länge der Adresse in " *lpsockaddr* " in Bytes.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. In der folgenden Liste werden einige der Fehler aufgeführt, die zurückgegeben werden können. Eine umfassende Liste finden Sie unter [Windows Sockets-Fehler Codes](/windows/win32/winsock/windows-sockets-error-codes-2).

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEADDRINUSE die angegebene Adresse wird bereits verwendet. (Weitere Informationen finden Sie unter " [setsockopt](#setsockopt)" unter der Option SO_REUSEADDR Socket.)

- Wsaefault das *nsockaddrlen* -Argument ist zu klein (weniger als die Größe einer [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur).

- WSAEINPROGRESS ein blockierender Windows Sockets-Befehl wird ausgeführt.

- WSAEAFNOSUPPORT die angegebene Adressfamilie wird von diesem Port nicht unterstützt.

- Wsaeingeval: der Socket ist bereits an eine Adresse gebunden.

- WSAENOBUFS ist nicht genügend Puffer verfügbar, zu viele Verbindungen.

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Diese Routine wird für ein nicht verbundenes Datagramm oder einen Streamsocket verwendet `Connect` , `Listen` bevor nachfolgende-oder-Aufrufe ausgeführt werden. Bevor Verbindungsanforderungen akzeptiert werden können, muss ein überwachungsserversocket eine Portnummer auswählen und Windows Sockets durch Aufrufen `Bind`von bekannt machen. `Bind`legt die lokale Zuordnung (Host Adresse/Portnummer) des Sockets fest, indem einem unbenannten Socket ein lokaler Name zugewiesen wird.

##  <a name="casyncsocket"></a>CAsyncSocket:: CAsyncSocket

Erstellt ein leeres Socketobjekt.

```
CAsyncSocket();
```

### <a name="remarks"></a>Hinweise

Nachdem Sie das-Objekt erstellt haben, müssen `Create` Sie seine Member-Funktion zum Erstellen der socketdatenstruktur und zum Binden Ihrer Adresse aufruft. (Auf der Serverseite einer Windows Sockets-Kommunikation, wenn der lausch Ende Socket einen Socket erstellt, der `Accept` im-Befehl verwendet werden soll `Create` , wird für diesen Socket nicht aufgerufen.)

##  <a name="close"></a>CAsyncSocket:: Close

Schließt den Socket.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Diese Funktion gibt den socketdeskriptor frei, sodass weitere Verweise darauf mit dem Fehler wsaenotsock fehlschlagen. Wenn dies der letzte Verweis auf den zugrunde liegenden Socket ist, werden die zugeordneten Benennungs Informationen und in der Warteschlange befindlichen Daten verworfen. Der Dekonstruktor des Socket- `Close` Objekts Ruft für Sie auf.

Für `CAsyncSocket`, aber nicht für `CSocket`, ist die-Semantik von `Close` den Socketoptionen SO_LINGER und SO_DONTLINGER betroffen. Weitere Informationen finden Sie unter Member- `GetSockOpt`Funktion.

##  <a name="connect"></a>CAsyncSocket:: Connect

Mit dieser Member-Funktion können Sie eine Verbindung mit einem nicht verbundenen Stream oder Datagramm-Socket herstellen.

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
Die Netzwerkadresse des Sockets, mit dem dieses Objekt verbunden ist: ein Computername wie "FTP.Microsoft.com" oder eine gepunktete Zahl, z. b. "128.56.22.8".

*nHostPort*<br/>
Der Port, der die socketanwendung identifiziert.

*lpSockAddr*<br/>
Ein Zeiger auf eine [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die die Adresse des verbundenen Sockets enthält.

*nSockAddrLen*<br/>
Die Länge der Adresse in " *lpsockaddr* " in Bytes.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Wenn dies auf einen Fehlercode von WSAEWOULDBLOCK hinweist und die Anwendung die über schreibbaren Rückrufe verwendet, empfängt Ihre Anwendung eine `OnConnect` Meldung, wenn der Verbindungsvorgang beendet ist. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEADDRINUSE die angegebene Adresse wird bereits verwendet.

- WSAEINPROGRESS ein blockierender Windows Sockets-Befehl wird ausgeführt.

- Wsaeaddrnotavail die angegebene Adresse ist auf dem lokalen Computer nicht verfügbar.

- WSAEAFNOSUPPORT-Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.

- Wsaeconnverweigerte der Verbindungsversuch wurde zurückgewiesen.

- WSAEDESTADDRREQ eine Zieladresse ist erforderlich.

- Wsaefault das *nsockaddrlen* -Argument ist falsch.

- Wsaein Val ungültige Host Adresse.

- Wsaeisconn der Socket ist bereits verbunden.

- Wsaemfile es sind keine Dateideskriptoren mehr verfügbar.

- Wsaumetunreach das Netzwerk kann von diesem Host zurzeit nicht erreicht werden.

- WSAENOBUFS ist kein Pufferspeicher verfügbar. Der Socket kann nicht verbunden werden.

- Wsaenotsock der Deskriptor ist kein Socket.

- Timeout beim Versuch, eine Verbindung herzustellen, ohne eine Verbindung herzustellen.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend gekennzeichnet, und die Verbindung kann nicht sofort abgeschlossen werden.

### <a name="remarks"></a>Hinweise

Wenn der Socket nicht gebunden ist, werden eindeutige Werte der lokalen Zuordnung vom System zugewiesen, und der Socket wird als gebunden gekennzeichnet. Beachten Sie Folgendes: Wenn das Adressfeld der namens Struktur alle Nullen ist `Connect` , gibt 0 (null) zurück. Um erweiterte Fehlerinformationen abzurufen, nennen Sie `GetLastError` die Member-Funktion.

Bei Stream Sockets (Typ SOCK_STREAM) wird eine aktive Verbindung mit dem fremden Host initiiert. Wenn der Socket-Befehl erfolgreich abgeschlossen wird, ist der Socket bereit zum Senden/Empfangen von Daten.

Für einen Datagramm-Socket (Type SOCK_DGRAM) wird ein Standardziel festgelegt, das bei nachfolgenden `Send` - `Receive` und-Aufrufen verwendet wird.

##  <a name="create"></a>CAsyncSocket:: Create

Rufen Sie `Create` die Member-Funktion nach dem Erstellen eines Socket-Objekts auf, um den Windows-Socket zu erstellen und anzufügen

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parameter

*nSocketPort*<br/>
Ein bekannter Port, der mit dem Socket verwendet werden soll, oder 0, wenn Sie möchten, dass Windows Sockets einen Port auswählt.

*nSocketType*<br/>
SOCK_STREAM oder SOCK_DGRAM.

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerk Ereignissen angibt, an denen die Anwendung interessiert ist.

- FD_READ möchte eine Benachrichtigung über die Bereitschaft zum Lesen erhalten.

- FD_WRITE möchte eine Benachrichtigung über die Bereitschaft zum Schreiben erhalten.

- FD_OOB möchte eine Benachrichtigung über die Ankunft von Out-of-Band-Daten erhalten.

- FD_ACCEPT möchte Benachrichtigungen über eingehende Verbindungen erhalten.

- FD_CONNECT möchte eine Benachrichtigung über die abgeschlossene Verbindung erhalten.

- FD_CLOSE will eine Benachrichtigung über den Socket-Abschluss erhalten.

*lpszSockAddress*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets enthält, eine gepunktete Zahl wie z. b. "128.56.22.8". Durch das übergeben der NULL-Zeichenfolge für `CAsyncSocket` diesen Parameter wird angegeben, dass die Instanz auf allen Netzwerkschnittstellen auf Client Aktivitäten lauschen soll.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEAFNOSUPPORT die angegebene Adressfamilie wird nicht unterstützt.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaemfile es sind keine Dateideskriptoren mehr verfügbar.

- WSAENOBUFS ist kein Pufferspeicher verfügbar. Der Socket kann nicht erstellt werden.

- Wsaeprotonosupport der angegebene Port wird nicht unterstützt.

- WSAEPROTOTYPE der angegebene Port ist der falsche Typ für diesen Socket.

- Wsaesocktnosupport der angegebene Sockettyp wird in dieser Adressfamilie nicht unterstützt.

### <a name="remarks"></a>Hinweise

`Create`Ruft den [Socket](#socket) auf, und bei erfolgreicher Ausführung wird [Bind](#bind) aufgerufen, um den Socket an die angegebene Adresse zu binden. Die folgenden sockettypen werden unterstützt:

- SOCK_STREAM bietet sequenzierte, zuverlässige, Vollduplex und Verbindungs basierte Bytestreams. Verwendet das Transmission Control Protocol (TCP) für die Internet Adressfamilie.

- SOCK_DGRAM unterstützt Datagramme, bei denen es sich um verbindungslose, unzuverlässige Pakete mit einer festgelegten (normalerweise kleinen) maximalen Länge handelt. Verwendet das User Datagram-Protokoll (UDP) für die Internet Adressfamilie.

    > [!NOTE]
    >  Die `Accept` Member-Funktion nimmt einen Verweis auf ein neues, `CSocket` leeres-Objekt als Parameter auf. Sie müssen dieses Objekt erstellen, bevor Sie `Accept`aufzurufen. Beachten Sie, dass die Verbindung geschlossen wird, wenn dieses Socketobjekt den Gültigkeitsbereich verlässt. Für dieses neue `Create` Socketobjekt nicht aufzurufen.

> [!IMPORTANT]
> `Create`ist **nicht** Thread sicher.  Wenn Sie ihn in einer Multithreadumgebung aufrufen, in der er gleichzeitig von verschiedenen Threads aufgerufen werden kann, achten Sie darauf, jeden Aufruf mit einem Mutex oder einer anderen Synchronisierungs Sperre zu schützen.

Weitere Informationen zu Stream-und Datagramm-Sockets finden Sie [in den Artikeln Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md) und [Windows-Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md) und [Windows Sockets 2-API](/windows/win32/WinSock/windows-sockets-start-page-2).

##  <a name="detach"></a>CAsyncSocket::D Etach

Mit dieser Member-Funktion trennen Sie das Sockethandle im *m_hSocket* -Datenmember vom `CAsyncSocket` -Objekt und legen *m_hSocket* auf NULL fest.

```
SOCKET Detach();
```

##  <a name="fromhandle"></a>CAsyncSocket:: FromHandle

Gibt einen Zeiger auf ein `CAsyncSocket` -Objekt zurück.

```
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parameter

*hSocket*<br/>
Enthält ein Handle für einen Socket.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CAsyncSocket` -Objekt oder NULL, wenn kein `CAsyncSocket` -Objekt an *hsocket*angefügt ist.

### <a name="remarks"></a>Hinweise

Wenn ein Sockethandle angegeben ist und `CAsyncSocket` ein-Objekt nicht an das Handle angefügt ist, gibt die Member-Funktion NULL zurück.

##  <a name="getlasterror"></a>CAsyncSocket:: GetLastError

Mit dieser Member-Funktion können Sie den Fehlerstatus für den letzten fehlgeschlagenen Vorgang abrufen.

```
static int PASCAL GetLastError();
```

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert gibt den Fehlercode für die letzte Windows Sockets-API-Routine an, die von diesem Thread ausgeführt wird.

### <a name="remarks"></a>Hinweise

Wenn eine bestimmte Member-Funktion anzeigt, dass ein Fehler aufgetreten `GetLastError` ist, sollte aufgerufen werden, um den entsprechenden Fehlercode abzurufen. Eine Liste der entsprechenden Fehlercodes finden Sie in den Beschreibungen der einzelnen Member-Funktionen.

Weitere Informationen zu den Fehlercodes finden Sie unter [Windows Sockets 2-API](/windows/win32/WinSock/windows-sockets-start-page-2).

##  <a name="getpeername"></a>CAsyncSocket:: getPeer Name

Mit dieser Member-Funktion können Sie die Adresse des peersockets abrufen, mit dem dieser Socket verbunden ist.

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
Verweis auf ein `CString` -Objekt, das eine gepunktete Zahl-IP-Adresse empfängt.

*rPeerPort*<br/>
Verweis auf einen uint, der einen Port speichert.

*lpSockAddr*<br/>
Ein Zeiger auf die [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die den Namen des Peer Sockets empfängt.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Adresse in *lpsockaddr* (in Bytes). Bei der Rückgabe enthält das *lpsockaddrlen* -Argument die tatsächliche Größe von *lpsockaddr* , die in Bytes zurückgegeben wurde.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument ist nicht groß genug.

- WSAEINPROGRESS ein blockierender Windows Sockets-Befehl wird ausgeführt.

- Wsaumotconn der Socket ist nicht verbunden.

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Verarbeiten von IPv6-Adressen [CAsyncSocket:: geteternameex](#getpeernameex).

##  <a name="getpeernameex"></a>CAsyncSocket:: geteternameex

Mit dieser Member-Funktion können Sie die Adresse des peersockets abrufen, mit dem dieser Socket verbunden ist (verarbeitet IPv6-Adressen).

```
BOOL GetPeerNameEx(
    CString& rPeerAddress,
    UINT& rPeerPort);
```

### <a name="parameters"></a>Parameter

*rPeerAddress*<br/>
Verweis auf ein `CString` -Objekt, das eine gepunktete Zahl-IP-Adresse empfängt.

*rPeerPort*<br/>
Verweis auf einen uint, der einen Port speichert.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument ist nicht groß genug.

- WSAEINPROGRESS ein blockierender Windows Sockets-Befehl wird ausgeführt.

- Wsaumotconn der Socket ist nicht verbunden.

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Diese Funktion ist mit [CAsyncSocket:: getPeer Name](#getpeername) identisch, mit der Ausnahme, dass Sie sowohl IPv6-Adressen als auch ältere Protokolle verarbeitet.

##  <a name="getsockname"></a>CAsyncSocket:: getsockname

Mit dieser Member-Funktion können Sie den lokalen Namen für einen Socket abrufen.

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
Verweis auf ein `CString` -Objekt, das eine gepunktete Zahl-IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf einen uint, der einen Port speichert.

*lpSockAddr*<br/>
Ein Zeiger auf eine [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die die Adresse des Sockets empfängt.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Adresse in *lpsockaddr* (in Bytes).

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument ist nicht groß genug.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaenotsock der Deskriptor ist kein Socket.

- Wsaein Val: der Socket wurde nicht an eine Adresse mit `Bind`gebunden.

### <a name="remarks"></a>Hinweise

Dieser-Befehl ist besonders nützlich, `Connect` wenn ein-Befehl aufgerufen wurde, `Bind` ohne zuerst eine zu tun. dieser-Befehl stellt die einzige Möglichkeit dar, mit der Sie die lokale Zuordnung ermitteln können, die vom System festgelegt wurde.

Verwenden Sie zum Verarbeiten von IPv6-Adressen [CAsyncSocket:: GetSockNameEx](#getsocknameex) .

##  <a name="getsocknameex"></a>CAsyncSocket:: GetSockNameEx

Mit dieser Member-Funktion können Sie den lokalen Namen für einen Socket abrufen (verarbeitet IPv6-Adressen).

```
BOOL GetSockNameEx(
    CString& rSocketAddress,
    UINT& rSocketPort);
```

### <a name="parameters"></a>Parameter

*rSocketAddress*<br/>
Verweis auf ein `CString` -Objekt, das eine gepunktete Zahl-IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf einen uint, der einen Port speichert.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument ist nicht groß genug.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaenotsock der Deskriptor ist kein Socket.

- Wsaein Val: der Socket wurde nicht an eine Adresse mit `Bind`gebunden.

### <a name="remarks"></a>Hinweise

Dieser Befehl ist identisch mit [CAsyncSocket:: getsockname](#getsockname) , mit dem Unterschied, dass er IPv6-Adressen und ältere Protokolle verarbeitet.

Dieser-Befehl ist besonders nützlich, `Connect` wenn ein-Befehl aufgerufen wurde, `Bind` ohne zuerst eine zu tun. dieser-Befehl stellt die einzige Möglichkeit dar, mit der Sie die lokale Zuordnung ermitteln können, die vom System festgelegt wurde.

##  <a name="getsockopt"></a>CAsyncSocket:: getsockopt

Rufen Sie diese Member-Funktion auf, um eine Socketoption abzurufen.

```
BOOL GetSockOpt(
    int nOptionName,
    void* lpOptionValue,
    int* lpOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parameter

*nOptionName*<br/>
Die Socketoption, für die der Wert abgerufen werden soll.

*lpOptionValue*<br/>
Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option zurückgegeben werden soll. Der Wert, der der ausgewählten Option zugeordnet ist, wird im Puffer *lpoptionvalue*zurückgegeben. Die Ganzzahl, auf die *lpoptionlen* verweist, sollte ursprünglich die Größe dieses Puffers in Bytes enthalten. und bei der Rückgabe wird der Wert auf die Größe des zurückgegebenen Werts festgelegt. Bei SO_LINGER ist dies die Größe einer `LINGER` Struktur. bei allen anderen Optionen ist dies abhängig von der Option die Größe eines booleschen Werts oder eines **int**-Werts. Weitere Informationen finden Sie in der Liste der Optionen und deren Größen im Abschnitt "Hinweise".

*lpOptionLen*<br/>
Ein Zeiger auf die Größe des *lpoptionvalue* -Puffers in Bytes.

*nLevel*<br/>
Die Ebene, auf der die Option definiert ist. die einzigen unterstützten Ebenen sind SOL_SOCKET und IPPROTO_TCP.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Wenn eine Option nie mit `SetSockOpt`festgelegt wurde `GetSockOpt` , wird der Standardwert für die Option zurückgegeben. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpoptionlen* -Argument war ungültig.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsakooprodeopt die Option ist unbekannt oder wird nicht unterstützt. SO_BROADCAST wird insbesondere für Sockets vom Typ SOCK_STREAM nicht unterstützt, während SO_ACCEPTCONN, SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER und SO_OOBINLINE bei Sockets vom Typ SOCK_DGRAM nicht unterstützt werden.

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

`GetSockOpt`Ruft den aktuellen Wert für eine Socketoption ab, die einem Socket eines beliebigen Typs in einem beliebigen Zustand zugeordnet ist, und speichert das Ergebnis in *lpoptionvalue*. Optionen wirken sich auf Socketvorgänge aus, z. b. das Routing von Paketen, out-of-Band-Datenübertragungen usw.

Die folgenden Optionen werden für `GetSockOpt`unterstützt. Der Typ identifiziert den Typ der Daten, die von *lpoptionvalue*adressiert werden. Die TCP_NODELAY-Option verwendet Level IPPROTO_TCP; alle anderen Optionen verwenden Ebene SOL_SOCKET.

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Der Socket lauscht.|
|SO_BROADCAST|BOOL|Socket ist für die Übertragung von Broadcast Nachrichten konfiguriert.|
|SO_DEBUG|BOOL|Debuggen ist aktiviert.|
|SO_DONTLINGER|BOOL|True gibt an, dass die Option SO_LINGER deaktiviert ist.|
|SO_DONTROUTE|BOOL|Das Routing ist deaktiviert.|
|SO_ERROR|**int**|Fehlerstatus abrufen und löschen.|
|SO_KEEPALIVE|BOOL|Keep-Alives werden gesendet.|
|SO_LINGER|`struct LINGER`|Gibt die aktuellen Linger-Optionen zurück.|
|SO_OOBINLINE|BOOL|Out-of-Band-Daten werden im normalen Datenstrom empfangen.|
|SO_RCVBUF|ssNoversion|Die Puffergröße für Empfangs Vorgänge.|
|SO_REUSEADDR|BOOL|Der Socket kann an eine Adresse gebunden werden, die bereits verwendet wird.|
|SO_SNDBUF|**int**|Die Puffergröße für Sendungen.|
|SO_TYPE|**int**|Der Typ des Sockets (z. b. SOCK_STREAM).|
|TCP_NODELAY|BOOL|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|

Die Optionen von Berkeley Software Distribution (BSD) werden `GetSockOpt` für nicht unterstützt:

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_RCVLOWAT|**int**|Niedrige Wasser Grenze empfangen.|
|SO_RCVTIMEO|**int**|Empfangs Timeout.|
|SO_SNDLOWAT|**int**|Niedrige Wasser Grenze senden.|
|SO_SNDTIMEO|**int**|Timeout für Sendevorgang.|
|IP_OPTIONS||Optionen im IP-Header erhalten.|
|TCP_MAXSEG|**int**|Maximale TCP-Segmentgröße erhalten.|

Wenn `GetSockOpt` Sie mit einer nicht unterstützten Option aufrufen, führt dies zu einem Fehlercode von WSA-oprotoopt, der von `GetLastError`zurückgegeben wird.

##  <a name="ioctl"></a>CAsyncSocket:: ioctl

Mit dieser Member-Funktion können Sie den Modus eines Sockets steuern.

```
BOOL IOCtl(
    long lCommand,
    DWORD* lpArgument);
```

### <a name="parameters"></a>Parameter

*lCommand*<br/>
Der Befehl, der für den Socket auszuführen ist.

*lpArgument*<br/>
Ein Zeiger auf einen Parameter für *lcommand*.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEINVAL *lcommand* ist kein gültiger Befehl, oder *lzigument* ist kein zulässiger Parameter für *lcommand*, oder der Befehl ist nicht auf den Typ des bereitgestellten Sockets anwendbar.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

Diese Routine kann für beliebige Sockets in jedem Zustand verwendet werden. Sie wird verwendet, um die dem Socket zugeordneten Betriebsparameter unabhängig vom Protokoll-und Kommunikations Subsystem abzurufen oder abzurufen. Die folgenden Befehle werden unterstützt:

- "Atonbio" aktiviert oder deaktiviert den nicht blockierenden Modus für den Socket. Der *lzigument* -Parameter verweist auf `DWORD`einen, der ungleich NULL ist, wenn der nicht blockierende Modus aktiviert werden soll, und 0 (null), wenn er deaktiviert werden soll. Wenn `AsyncSelect` für einen Socket ausgegeben wurde, schlägt jeder Versuch `IOCtl` , den Socket wieder in den Blockierungs Modus zu setzen, mit WSAEINVAL fehl. Damit der Socket wieder in den Blockierungs Modus wechselt und den WSAEINVAL-Fehler verhindert, muss eine `AsyncSelect` Anwendung zunächst `AsyncSelect` durch Aufrufen von mit dem *Levent* -Parameter auf 0 `IOCtl`(null) und anschließendem Aufrufen von deaktiviert werden.

- "Fonread" bestimmt die maximale Anzahl von Bytes, die mit einem `Receive` von diesem Socket aufzurufenden Befehl gelesen werden kann. Der *lzigument* -Parameter verweist auf `DWORD` ein- `IOCtl` Element, in dem das Ergebnis speichert. Wenn dieser Socket den Typ "SOCK_STREAM" hat, gibt "atonread" die Gesamtmenge der Daten zurück, die `Receive`in einem einzelnen gelesen werden können. Dies ist normalerweise identisch mit der Gesamtmenge der Daten, die im Socket in die Warteschlange eingereiht wurden. Wenn dieser Socket den Typ "SOCK_DGRAM" hat, gibt "fonread" die Größe des ersten Datagramms zurück, das in die Warteschlange des Sockets eingefügt wurde

- Siocatmark bestimmt, ob alle out-of-Band-Daten gelesen wurden. Dies gilt nur für einen Socket vom Typ SOCK_STREAM, der für den Inline Empfang von Out-of-Band-Daten (SO_OOBINLINE) konfiguriert wurde. Wenn keine Out-of-Band-Daten darauf warten, gelesen zu werden, gibt der Vorgang einen Wert ungleich 0 (null) zurück. Andernfalls wird 0 zurückgegeben, und der `Receive` nächste `ReceiveFrom` oder durchgeführte Vorgang für den Socket ruft einige oder alle Daten ab, die der Markierung vorangestellt sind. die Anwendung sollte den siocatmark-Vorgang verwenden, um zu bestimmen, ob Daten verbleiben. Wenn normale Daten vor den "dringenden" (Out-of-Band-) Daten vorliegen, werden Sie in der richtigen Reihenfolge empfangen. (Beachten Sie, `Receive` dass `ReceiveFrom` ein oder nie out-of-Band-und normale Daten im selben-aufrufmix kombiniert.) Der *lzigument* -Parameter verweist auf `DWORD` ein- `IOCtl` Element, in dem das Ergebnis speichert.

Diese Funktion ist eine Teilmenge von `ioctl()` , wie Sie in Berkeley Sockets verwendet wird. Insbesondere gibt es keinen Befehl, der mit "foasync" identisch ist, während "siocatmark" der einzige Befehl auf Socketebene ist, der unterstützt wird.

##  <a name="listen"></a>CAsyncSocket:: lauschen

Diese Member-Funktion zum lauschen auf eingehende Verbindungsanforderungen aufzurufen.

```
BOOL Listen(int nConnectionBacklog = 5);
```

### <a name="parameters"></a>Parameter

*nConnectionBacklog*<br/>
Die maximale Länge, auf die die Warteschlange ausstehender Verbindungen anwachsen kann. Der gültige Bereich liegt zwischen 1 und 5.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEADDRINUSE es wurde versucht, eine verwendete Adresse abzuhören.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaeingeval der Socket wurde nicht an gebunden `Bind` oder ist bereits verbunden.

- Wsaeisconn der Socket ist bereits verbunden.

- Wsaemfile es sind keine Dateideskriptoren mehr verfügbar.

- WSAENOBUFS ist kein Pufferspeicher verfügbar.

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP der referenzierte Socket weist keinen Typ auf, der den `Listen` Vorgang unterstützt.

### <a name="remarks"></a>Hinweise

Um Verbindungen zu akzeptieren, wird der Socket zuerst mit `Create`erstellt, ein Rückstand für eingehende Verbindungen wird `Listen`mit angegeben, und anschließend werden die Verbindungen `Accept`mit akzeptiert. `Listen`gilt nur für Sockets, die Verbindungen unterstützen, d. h. die des Typs SOCK_STREAM. Dieser Socket wird in den "passiven" Modus versetzt, in dem eingehende Verbindungen bestätigt werden und ausstehende Akzeptanz durch den Prozess in eine Warteschlange eingereiht wird.

Diese Funktion wird in der Regel von Servern (oder einer beliebigen Anwendung, die Verbindungen akzeptieren möchte) verwendet, die mehrere Verbindungsanforderungen gleichzeitig haben können: Wenn eine Verbindungsanforderung mit der Warteschlange voll ist, erhält der Client einen Fehler mit der Angabe, dass Wsaeconnabgelehnt.

`Listen`versucht, weiterhin vernünftig zu funktionieren, wenn keine Ports (Deskriptoren) vorhanden sind. Verbindungen werden bis zur leeren Warteschlange akzeptiert. Wenn Ports verfügbar werden, wird die Warteschlange `Listen` durch `Accept` einen späteren-oder-Rückruf erneut zum aktuellen oder letzten "Rückstand" aufgefüllt, sofern möglich, und das Lauschen auf eingehende Verbindungen fortgesetzt.

##  <a name="m_hsocket"></a>CAsyncSocket:: m_hSocket

Enthält das Sockethandle für den von diesem `CAsyncSocket` -Objekt gekapselten Socket.

```
SOCKET m_hSocket;
```

##  <a name="onaccept"></a>CAsyncSocket:: OnAccept

Wird von Framework aufgerufen, um einen Abhör Socket zu benachrichtigen, dass er ausstehende Verbindungsanforderungen annehmen kann, indem er die [Accept](#accept) -Member-Funktion aufruft.

```
virtual void OnAccept(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Der letzte Fehler in einem Socket. Die folgenden Fehlercodes gelten für die `OnAccept` Member-Funktion:

- **0** die Funktion wurde erfolgreich ausgeführt.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onclose"></a>CAsyncSocket:: OnClose

Wird von Framework aufgerufen, um diesen Socket zu benachrichtigen, dass der verbundene Socket durch seinen Prozess geschlossen wird.

```
virtual void OnClose(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Der letzte Fehler in einem Socket. Die folgenden Fehlercodes gelten für die `OnClose` Member-Funktion:

- **0** die Funktion wurde erfolgreich ausgeführt.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAECONNRESET die Verbindung wurde von der Remote Seite zurückgesetzt.

- WSAECONNABORTED die Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onconnect"></a>CAsyncSocket:: OnConnect

Wird von Framework aufgerufen, um den Verbindungsversuch zu benachrichtigen, dass der Verbindungsversuch abgeschlossen ist, ob erfolgreich oder fehlerhaft.

```
virtual void OnConnect(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Der letzte Fehler in einem Socket. Die folgenden Fehlercodes gelten für die `OnConnect` Member-Funktion:

- **0** die Funktion wurde erfolgreich ausgeführt.

- WSAEADDRINUSE die angegebene Adresse wird bereits verwendet.

- Wsaeaddrnotavail die angegebene Adresse ist auf dem lokalen Computer nicht verfügbar.

- WSAEAFNOSUPPORT-Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.

- Wsaeconnverweigerte der Verbindungsversuch wurde zurückgewiesen.

- WSAEDESTADDRREQ eine Zieladresse ist erforderlich.

- Wsaefault das *lpsockaddrlen* -Argument ist falsch.

- Wsaeingeval: der Socket ist bereits an eine Adresse gebunden.

- Wsaeisconn der Socket ist bereits verbunden.

- Wsaemfile es sind keine Dateideskriptoren mehr verfügbar.

- Wsaumetunreach das Netzwerk kann von diesem Host zurzeit nicht erreicht werden.

- WSAENOBUFS ist kein Pufferspeicher verfügbar. Der Socket kann nicht verbunden werden.

- Wsaumotconn der Socket ist nicht verbunden.

- Wsaenotsock der Deskriptor ist eine Datei und kein Socket.

- WSAETIMEDOUT: Timeout beim Verbindungsversuch, ohne eine Verbindung herzustellen.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  In [CSocket](../../mfc/reference/csocket-class.md)wird die `OnConnect` Benachrichtigungsfunktion niemals aufgerufen. Bei Verbindungen wird einfach aufgerufen `Connect`, was zurückgegeben wird, wenn die Verbindung abgeschlossen ist (entweder erfolgreich oder fehlerhaft). Wie Verbindungs Benachrichtigungen behandelt werden, ist ein MFC-Implementierungsdetail.

Weitere Informationen finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]

##  <a name="onoutofbanddata"></a>CAsyncSocket:: onoudebbanddata

Wird von Framework aufgerufen, um den empfangenden Socket zu benachrichtigen, dass der sendende Socket über Out-of-Band-Daten zum Senden verfügt.

```
virtual void OnOutOfBandData(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Der letzte Fehler in einem Socket. Die folgenden Fehlercodes gelten für die `OnOutOfBandData` Member-Funktion:

- **0** die Funktion wurde erfolgreich ausgeführt.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

### <a name="remarks"></a>Hinweise

Out-of-Band-Daten sind logisch unabhängige Kanäle, die jedem Paar verbundener Sockets vom Typ SOCK_STREAM zugeordnet sind. Der Kanal wird im Allgemeinen verwendet, um dringende Daten zu senden.

MFC unterstützt out-of-Band-Daten, aber Benutzer `CAsyncSocket` der Klasse werden davon abgeraten, Sie zu verwenden. Der einfachere Weg besteht darin, einen zweiten Socket zum Übergeben dieser Daten zu erstellen. Weitere Informationen zu out-of-Band-Daten finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

##  <a name="onreceive"></a>CAsyncSocket:: OnReceive

Wird von Framework aufgerufen, um diesen Socket zu benachrichtigen, dass Daten im Puffer vorhanden sind, die durch Aufrufen der `Receive` Member-Funktion abgerufen werden können.

```
virtual void OnReceive(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Der letzte Fehler in einem Socket. Die folgenden Fehlercodes gelten für die `OnReceive` Member-Funktion:

- **0** die Funktion wurde erfolgreich ausgeführt.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]

##  <a name="onsend"></a>CAsyncSocket:: OnSend

Wird von Framework aufgerufen, um den Socket zu benachrichtigen, dass er nun durch Aufrufen der `Send` Member-Funktion Daten senden kann.

```
virtual void OnSend(int nErrorCode);
```

### <a name="parameters"></a>Parameter

*nErrorCode*<br/>
Der letzte Fehler in einem Socket. Die folgenden Fehlercodes gelten für die `OnSend` Member-Funktion:

- **0** die Funktion wurde erfolgreich ausgeführt.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden [Sie unter Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]

##  <a name="operator_eq"></a>CAsyncSocket:: Operator =

Weist einem- `CAsyncSocket` Objekt einen neuen Wert zu.

```
void operator=(const CAsyncSocket& rSrc);
```

### <a name="parameters"></a>Parameter

*rSrc*<br/>
Ein Verweis auf ein vorhandenes `CAsyncSocket` -Objekt.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird ein vorhandenes `CAsyncSocket` Objekt in ein `CAsyncSocket` anderes Objekt kopiert.

##  <a name="operator_socket"></a>CAsyncSocket:: Operator Socket

Verwenden Sie diesen Operator, um das Sockethandle `CAsyncSocket` des-Objekts abzurufen.

```
operator SOCKET() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle des Socket-Objekts. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Sie können das Handle verwenden, um Windows-APIs direkt aufzurufen.

##  <a name="receive"></a>CAsyncSocket:: Receive

Mit dieser Member-Funktion können Sie Daten von einem Socket empfangen.

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
Die Länge von *lpbuf* in Bytes.

*nFlags*<br/>
Gibt an, wie der-Befehl aufgerufen wird. Die Semantik dieser Funktion wird durch die Socketoptionen und den *nFlags* -Parameter bestimmt. Letzteres wird erstellt, indem die folgenden Werte mit dem C++ **or** -Operator kombiniert werden:

- MSG_PEEK werfen Sie einen Blick auf die eingehenden Daten. Die Daten werden in den Puffer kopiert, jedoch nicht aus der Eingabe Warteschlange entfernt.

- MSG_OOB out-of-Band-Daten verarbeiten.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `Receive` wird die Anzahl der empfangenen Bytes zurückgegeben. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls wird der Wert "SOCKET_ERROR" zurückgegeben, und ein bestimmter Fehlercode kann durch Aufrufen von " [GetLastError](#getlasterror)" abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaumotconn der Socket ist nicht verbunden.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN: der Socket wurde heruntergefahren. Es ist nicht möglich, für `Receive` einen Socket aufzurufen `ShutDown` , nachdem aufgerufen wurde, wobei *Nhow* auf 0 oder 2 festgelegt wurde.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend markiert `Receive` , und der Vorgang wird blockiert.

- Wsaemsgsize: das Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.

- Wsaeingeval der Socket wurde nicht an gebunden `Bind`.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remote Seite zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Funktion wird für verbundene Datenstrom-oder Datagramm-Sockets verwendet und zum Lesen eingehender Daten verwendet.

Bei Sockets vom Typ SOCK_STREAM wird eine Menge an Informationen zurückgegeben, die derzeit bis zur Größe des bereitgestellten Puffers verfügbar ist. Wenn der Socket für den Inline Empfang von Out-of-Band-Daten (Socketoption SO_OOBINLINE) und Out-of-Band-Daten nicht gelesen wurde, werden nur Out-of-Band-Daten zurückgegeben. Die Anwendung kann mithilfe der `IOCtlSIOCATMARK` -Option oder der [onouto fbanddata](#onoutofbanddata) -Option ermitteln, ob noch mehr out-of-Band-Daten gelesen werden sollen.

Bei Datagramm-Sockets werden Daten aus dem ersten in die Warteschlange eingereihten Datagramm extrahiert, bis zur Größe des angegebenen Puffers. Wenn das Datagramm größer als der angegebene Puffer ist, wird der Puffer mit dem ersten Teil des Datagramms aufgefüllt, die überschüssigen Daten gehen verloren, `Receive` und der Wert SOCKET_ERROR wird zurückgegeben, wobei der Fehlercode auf wsaemsgsize festgelegt ist. Wenn im Socket keine eingehenden Daten verfügbar sind, wird der Wert SOCKET_ERROR zurückgegeben, wobei der Fehlercode auf WSAEWOULDBLOCK festgelegt ist. Die [OnReceive](#onreceive) -Rückruffunktion kann verwendet werden, um zu bestimmen, wann weitere Daten eintreffen.

Wenn der Socket den Typ SOCK_STREAM aufweist und die Verbindung von der Remote Seite ordnungsgemäß beendet wurde, wird `Receive` eine sofort mit 0 Bytes empfangen. Wenn die Verbindung zurückgesetzt wurde, schlägt `Receive` ein mit dem Fehler "WSAECONNRESET" fehl.

`Receive`sollte nur einmal für jedes Mal aufgerufen werden, wenn [CAsyncSocket:: OnReceive](#onreceive) aufgerufen wird.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CAsyncSocket:: OnReceive](#onreceive).

##  <a name="receivefrom"></a>CAsyncSocket:: ReceiveFrom

Mit dieser Member-Funktion können Sie ein Datagramm empfangen und die Quelladresse in der [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur oder in *rsocketaddress*speichern.

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
Die Länge von *lpbuf* in Bytes.

*rSocketAddress*<br/>
Verweis auf ein `CString` -Objekt, das eine gepunktete Zahl-IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf einen uint, der einen Port speichert.

*lpSockAddr*<br/>
Ein Zeiger auf eine [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die die Quelladresse bei der Rückgabe enthält.

*lpSockAddrLen*<br/>
Ein Zeiger auf die Länge der Quelladresse in *lpsockaddr* in Bytes.

*nFlags*<br/>
Gibt an, wie der-Befehl aufgerufen wird. Die Semantik dieser Funktion wird durch die Socketoptionen und den *nFlags* -Parameter bestimmt. Letzteres wird erstellt, indem die folgenden Werte mit dem C++ **or** -Operator kombiniert werden:

- MSG_PEEK werfen Sie einen Blick auf die eingehenden Daten. Die Daten werden in den Puffer kopiert, jedoch nicht aus der Eingabe Warteschlange entfernt.

- MSG_OOB out-of-Band-Daten verarbeiten.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `ReceiveFrom` wird die Anzahl der empfangenen Bytes zurückgegeben. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls wird ein Wert von SOCKET_ERROR zurückgegeben, und ein bestimmter Fehlercode kann abgerufen werden, indem `GetLastError`aufgerufen wird. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument war ungültig: der *lpsockaddr* -Puffer war zu klein, um die Peer Adresse aufnehmen zu können.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaeingeval der Socket wurde nicht an gebunden `Bind`.

- Wsaumotconn der Socket ist nicht verbunden (nur SOCK_STREAM).

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN: der Socket wurde heruntergefahren. Es ist nicht möglich, für `ReceiveFrom` einen Socket aufzurufen `ShutDown` , nachdem aufgerufen wurde, wobei *Nhow* auf 0 oder 2 festgelegt wurde.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend markiert `ReceiveFrom` , und der Vorgang wird blockiert.

- Wsaemsgsize: das Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remote Seite zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Funktion wird verwendet, um eingehende Daten in einem (möglicherweise verbundenen) Socket zu lesen und die Adresse aufzuzeichnen, von der die Daten gesendet wurden.

Verwenden Sie zum Verarbeiten von IPv6-Adressen [CAsyncSocket:: ReceiveFromEx](#receivefromex).

Bei Sockets vom Typ SOCK_STREAM wird eine Menge an Informationen zurückgegeben, die derzeit bis zur Größe des bereitgestellten Puffers verfügbar ist. Wenn der Socket für den Inline Empfang von Out-of-Band-Daten (Socketoption SO_OOBINLINE) und Out-of-Band-Daten nicht gelesen wurde, werden nur Out-of-Band-Daten zurückgegeben. Die Anwendung kann die `IOCtlSIOCATMARK` Option oder `OnOutOfBandData` verwenden, um zu bestimmen, ob weitere out-of-Band-Daten gelesen werden sollen. Die Parameter " *lpsockaddr* " und " *lpsockaddrlen* " werden bei SOCK_STREAM Sockets ignoriert.

Bei Datagramm-Sockets werden Daten aus dem ersten in die Warteschlange eingereihten Datagramm extrahiert, bis zur Größe des angegebenen Puffers. Wenn das Datagramm größer als der angegebene Puffer ist, wird der Puffer mit dem ersten Teil der Nachricht aufgefüllt, die überschüssigen Daten gehen verloren, und `ReceiveFrom` der Wert SOCKET_ERROR wird zurückgegeben, wobei der Fehlercode auf wsaemsgsize festgelegt ist.

Wenn *lpsockaddr* ungleich 0 (null) ist und der Socket den Typ SOCK_DGRAM aufweist, wird die Netzwerkadresse des Sockets, der die Daten gesendet hat, in die entsprechende [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur kopiert. Der Wert, auf den von *lpsockaddrlen* verwiesen wird, wird mit der Größe dieser Struktur initialisiert und bei Rückgabe geändert, um die tatsächliche Größe der dort gespeicherten Adresse anzugeben. Wenn keine eingehenden Daten im Socket verfügbar sind, wartet `ReceiveFrom` der-Befehl, bis Daten eintreffen, es sei denn, der Socket ist nicht blockierend. In diesem Fall wird der Wert SOCKET_ERROR mit dem Fehlercode zurückgegeben, der auf WSAEWOULDBLOCK festgelegt ist. Der `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wann weitere Daten eintreffen.

Wenn der Socket den Typ SOCK_STREAM aufweist und die Verbindung von der Remote Seite ordnungsgemäß beendet wurde, wird `ReceiveFrom` eine sofort mit 0 Bytes empfangen.

##  <a name="receivefromex"></a>CAsyncSocket:: ReceiveFromEx

Diese Member-Funktion wird aufgerufen, um ein Datagramm zu empfangen und die Quelladresse in der [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur oder in *rsocketaddress* (verarbeitet IPv6-Adressen) zu speichern.

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
Die Länge von *lpbuf* in Bytes.

*rSocketAddress*<br/>
Verweis auf ein `CString` -Objekt, das eine gepunktete Zahl-IP-Adresse empfängt.

*rSocketPort*<br/>
Verweis auf einen uint, der einen Port speichert.

*nFlags*<br/>
Gibt an, wie der-Befehl aufgerufen wird. Die Semantik dieser Funktion wird durch die Socketoptionen und den *nFlags* -Parameter bestimmt. Letzteres wird erstellt, indem die folgenden Werte mit dem C++ **or** -Operator kombiniert werden:

- MSG_PEEK werfen Sie einen Blick auf die eingehenden Daten. Die Daten werden in den Puffer kopiert, jedoch nicht aus der Eingabe Warteschlange entfernt.

- MSG_OOB out-of-Band-Daten verarbeiten.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `ReceiveFromEx` wird die Anzahl der empfangenen Bytes zurückgegeben. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls wird ein Wert von SOCKET_ERROR zurückgegeben, und ein bestimmter Fehlercode kann abgerufen werden, indem `GetLastError`aufgerufen wird. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault das *lpsockaddrlen* -Argument war ungültig: der *lpsockaddr* -Puffer war zu klein, um die Peer Adresse aufnehmen zu können.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaeingeval der Socket wurde nicht an gebunden `Bind`.

- Wsaumotconn der Socket ist nicht verbunden (nur SOCK_STREAM).

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN: der Socket wurde heruntergefahren. Es ist nicht möglich, für `ReceiveFromEx` einen Socket aufzurufen `ShutDown` , nachdem aufgerufen wurde, wobei *Nhow* auf 0 oder 2 festgelegt wurde.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend markiert `ReceiveFromEx` , und der Vorgang wird blockiert.

- Wsaemsgsize: das Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remote Seite zurückgesetzt.

### <a name="remarks"></a>Hinweise

Diese Funktion wird verwendet, um eingehende Daten in einem (möglicherweise verbundenen) Socket zu lesen und die Adresse aufzuzeichnen, von der die Daten gesendet wurden.

Diese Funktion ist mit [CAsyncSocket:: ReceiveFrom](#receivefrom) identisch, mit der Ausnahme, dass Sie sowohl IPv6-Adressen als auch ältere Protokolle verarbeitet.

Bei Sockets vom Typ SOCK_STREAM wird eine Menge an Informationen zurückgegeben, die derzeit bis zur Größe des bereitgestellten Puffers verfügbar ist. Wenn der Socket für den Inline Empfang von Out-of-Band-Daten (Socketoption SO_OOBINLINE) und Out-of-Band-Daten nicht gelesen wurde, werden nur Out-of-Band-Daten zurückgegeben. Die Anwendung kann die `IOCtlSIOCATMARK` Option oder `OnOutOfBandData` verwenden, um zu bestimmen, ob weitere out-of-Band-Daten gelesen werden sollen. Die Parameter " *lpsockaddr* " und " *lpsockaddrlen* " werden bei SOCK_STREAM Sockets ignoriert.

Bei Datagramm-Sockets werden Daten aus dem ersten in die Warteschlange eingereihten Datagramm extrahiert, bis zur Größe des angegebenen Puffers. Wenn das Datagramm größer als der angegebene Puffer ist, wird der Puffer mit dem ersten Teil der Nachricht aufgefüllt, die überschüssigen Daten gehen verloren, und `ReceiveFromEx` der Wert SOCKET_ERROR wird zurückgegeben, wobei der Fehlercode auf wsaemsgsize festgelegt ist.

Wenn *lpsockaddr* ungleich 0 (null) ist und der Socket den Typ SOCK_DGRAM aufweist, wird die Netzwerkadresse des Sockets, der die Daten gesendet hat, in die entsprechende [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur kopiert. Der Wert, auf den von *lpsockaddrlen* verwiesen wird, wird mit der Größe dieser Struktur initialisiert und bei Rückgabe geändert, um die tatsächliche Größe der dort gespeicherten Adresse anzugeben. Wenn keine eingehenden Daten im Socket verfügbar sind, wartet `ReceiveFromEx` der-Befehl, bis Daten eintreffen, es sei denn, der Socket ist nicht blockierend. In diesem Fall wird der Wert SOCKET_ERROR mit dem Fehlercode zurückgegeben, der auf WSAEWOULDBLOCK festgelegt ist. Der `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wann weitere Daten eintreffen.

Wenn der Socket den Typ SOCK_STREAM aufweist und die Verbindung von der Remote Seite ordnungsgemäß beendet wurde, wird `ReceiveFromEx` eine sofort mit 0 Bytes empfangen.

##  <a name="send"></a>CAsyncSocket:: Send

Mit dieser Member-Funktion können Sie Daten auf einem verbundenen Socket senden.

```
virtual int Send(
    const void* lpBuf,
    int nBufLen,
    int nFlags = 0);
```

### <a name="parameters"></a>Parameter

*lpBuf*<br/>
Ein Puffer, der die zu übertragenden Daten enthält.

*nBufLen*<br/>
Die Länge der Daten in *lpbuf* (in Bytes).

*nFlags*<br/>
Gibt an, wie der-Befehl aufgerufen wird. Die Semantik dieser Funktion wird durch die Socketoptionen und den *nFlags* -Parameter bestimmt. Letzteres wird erstellt, indem die folgenden Werte mit dem C++ **or** -Operator kombiniert werden:

- MSG_DONTROUTE gibt an, dass für die Daten kein Routing unterliegen soll. Ein Windows Sockets-Lieferant kann dieses Flag ignorieren.

- MSG_OOB Senden von Out-of-Band-Daten (nur SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `Send` wird die Gesamtzahl der gesendeten Zeichen zurückgegeben. (Beachten Sie, dass dies kleiner als die Zahl sein kann, die durch *nbuslen*angegeben wird.) Andernfalls wird der Wert "SOCKET_ERROR" zurückgegeben, und ein bestimmter Fehlercode kann durch Aufrufen von " [GetLastError](#getlasterror)" abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEACCES die angeforderte Adresse ist eine Broadcast Adresse, das entsprechende Flag wurde jedoch nicht festgelegt.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaefault das *lpbuf* -Argument befindet sich nicht in einem gültigen Teil des Benutzer Adressraums.

- Wsaenetreset die Verbindung muss zurückgesetzt werden, da Sie von der Windows Sockets-Implementierung gelöscht wurde.

- WSAENOBUFS die Windows Sockets-Implementierung meldet einen Puffer Deadlock.

- Wsaumotconn der Socket ist nicht verbunden.

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN: der Socket wurde heruntergefahren. Es ist nicht möglich, für `Send` einen Socket aufzurufen `ShutDown` , nachdem mit *Nhow* aufgerufen wurde, der auf 1 oder 2 festgelegt ist.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend markiert, und der angeforderte Vorgang würde blockieren.

- Wsaemsgsize der Socket weist den Typ SOCK_DGRAM auf, und das Datagramm ist größer als das Maximum, das von der Windows Sockets-Implementierung unterstützt wird.

- Wsaeingeval der Socket wurde nicht an gebunden `Bind`.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remote Seite zurückgesetzt.

### <a name="remarks"></a>Hinweise

`Send`wird verwendet, um ausgehende Daten in verknüpften Datenströmen oder Datagrammsockets zu schreiben. Für Datagrammsockets muss darauf geachtet werden, dass die maximale IP-Paketgröße der zugrunde liegenden Subnetze nicht überschritten wird, die `iMaxUdpDg` durch das-Element in der [wsadata](/windows/win32/api/winsock2/ns-winsock2-wsadata) -Struktur angegeben werden, die von `AfxSocketInit`zurückgegeben wird. Wenn die Daten zu lang sind, um atomisch durch das zugrunde liegende Protokoll zu übergeben, wird der Fehler "wsaemsgsize" über `GetLastError`zurückgegeben, und es werden keine Daten übertragen.

Beachten Sie, dass der erfolgreiche Abschluss `Send` eines für einen Datagramm-Socket nicht anzeigt, dass die Daten erfolgreich übermittelt wurden.

Bei `CAsyncSocket` Objekten vom Typ SOCK_STREAM kann die Anzahl der geschriebenen Bytes zwischen 1 und der angeforderten Länge liegen, abhängig von der Puffer Verfügbarkeit auf den lokalen und den fremd Hosts.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CAsyncSocket:: OnSend](#onsend).

##  <a name="sendto"></a>CAsyncSocket:: sendto

Mit dieser Member-Funktion können Sie Daten an ein bestimmtes Ziel senden.

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
Ein Puffer, der die zu übertragenden Daten enthält.

*nBufLen*<br/>
Die Länge der Daten in *lpbuf* (in Bytes).

*nHostPort*<br/>
Der Port, der die socketanwendung identifiziert.

*lpszHostAddress*<br/>
Die Netzwerkadresse des Sockets, mit dem dieses Objekt verbunden ist: ein Computername wie z. b. "FTP.Microsoft.com" oder eine gepunktete Zahl, wie z. b. "128.56.22.8".

*nFlags*<br/>
Gibt an, wie der-Befehl aufgerufen wird. Die Semantik dieser Funktion wird durch die Socketoptionen und den *nFlags* -Parameter bestimmt. Letzteres wird erstellt, indem die folgenden Werte mit dem C++ **or** -Operator kombiniert werden:

- MSG_DONTROUTE gibt an, dass für die Daten kein Routing unterliegen soll. Ein Windows Sockets-Lieferant kann dieses Flag ignorieren.

- MSG_OOB Senden von Out-of-Band-Daten (nur SOCK_STREAM).

*lpSockAddr*<br/>
Ein Zeiger auf eine [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur, die die Adresse des Ziel Sockets enthält.

*nSockAddrLen*<br/>
Die Länge der Adresse in " *lpsockaddr* " in Bytes.

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `SendTo` wird die Gesamtzahl der gesendeten Zeichen zurückgegeben. (Beachten Sie, dass dies kleiner als die Zahl sein kann, die durch *nbuslen*angegeben wird.) Andernfalls wird der Wert "SOCKET_ERROR" zurückgegeben, und ein bestimmter Fehlercode kann durch Aufrufen von " [GetLastError](#getlasterror)" abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEACCES die angeforderte Adresse ist eine Broadcast Adresse, das entsprechende Flag wurde jedoch nicht festgelegt.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaefault die *lpbuf* -oder *lpsockaddr* -Parameter sind nicht Teil des Benutzer Adressraums, oder das *lpsockaddr* -Argument ist zu klein (weniger als die Größe einer [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur).

- WSAEINVAL der Hostname ist ungültig.

- Wsaenetreset die Verbindung muss zurückgesetzt werden, da Sie von der Windows Sockets-Implementierung gelöscht wurde.

- WSAENOBUFS die Windows Sockets-Implementierung meldet einen Puffer Deadlock.

- Wsaumotconn der Socket ist nicht verbunden (nur SOCK_STREAM).

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN: der Socket wurde heruntergefahren. Es ist nicht möglich, für `SendTo` einen Socket aufzurufen `ShutDown` , nachdem mit *Nhow* aufgerufen wurde, der auf 1 oder 2 festgelegt ist.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend markiert, und der angeforderte Vorgang würde blockieren.

- Wsaemsgsize der Socket weist den Typ SOCK_DGRAM auf, und das Datagramm ist größer als das Maximum, das von der Windows Sockets-Implementierung unterstützt wird.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remote Seite zurückgesetzt.

- Wsaeaddrnotavail die angegebene Adresse ist auf dem lokalen Computer nicht verfügbar.

- WSAEAFNOSUPPORT-Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.

- WSAEDESTADDRREQ eine Zieladresse ist erforderlich.

- Wsaumetunreach das Netzwerk kann von diesem Host zurzeit nicht erreicht werden.

### <a name="remarks"></a>Hinweise

`SendTo`wird für Datagramm oder Streamsockets verwendet und zum Schreiben von ausgehenden Daten in einem Socket verwendet. Für Datagramm-Sockets muss die maximale IP-Paketgröße der zugrunde liegenden Subnetze, die durch das `iMaxUdpDg` -Element in der [wsadata](/windows/win32/api/winsock2/ns-winsock2-wsadata) -Struktur, die von [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)ausgefüllt wird, nicht überschritten werden. Wenn die Daten zu lang sind, um atomisch über das zugrunde liegende Protokoll zu übergeben, wird der Fehler "wsaemsgsize" zurückgegeben, und es werden keine Daten übertragen.

Beachten Sie, dass der erfolgreiche Abschluss `SendTo` eines-Befehls nicht anzeigt, dass die Daten erfolgreich übermittelt wurden.

`SendTo`wird nur in einem SOCK_DGRAM-Socket verwendet, um ein Datagramm an einen bestimmten Socket zu senden, der durch den *lpsockaddr* -Parameter identifiziert wird.

Um eine Übertragung zu senden (nur auf einem SOCK_DGRAM), sollte die Adresse im *lpsockaddr* -Parameter mit der speziellen IP-Adresse INADDR_BROADCAST (definiert in der Windows Sockets-Header Datei Winsock) erstellt werden. H) in Verbindung mit der vorgesehenen Portnummer. Wenn der *lpszhustaddress* -Parameter den Wert NULL hat, wird der Socket für die Übertragung konfiguriert. Es ist in der Regel nicht ratsam, dass ein Broadcast Datagramm die Größe überschreitet, mit der die Fragmentierung auftreten kann. Dies impliziert, dass der Datentyp des Datagramms (ausgenommen Header) 512 Bytes nicht überschreiten darf.

Verwenden Sie zum Verarbeiten von IPv6-Adressen [CAsyncSocket:: SendToEx](#sendtoex).

##  <a name="sendtoex"></a>CAsyncSocket:: sendjeex

Diese Member-Funktion zum Senden von Daten an ein bestimmtes Ziel (verarbeitet IPv6-Adressen).

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
Ein Puffer, der die zu übertragenden Daten enthält.

*nBufLen*<br/>
Die Länge der Daten in *lpbuf* (in Bytes).

*nHostPort*<br/>
Der Port, der die socketanwendung identifiziert.

*lpszHostAddress*<br/>
Die Netzwerkadresse des Sockets, mit dem dieses Objekt verbunden ist: ein Computername wie z. b. "FTP.Microsoft.com" oder eine gepunktete Zahl, wie z. b. "128.56.22.8".

*nFlags*<br/>
Gibt an, wie der-Befehl aufgerufen wird. Die Semantik dieser Funktion wird durch die Socketoptionen und den *nFlags* -Parameter bestimmt. Letzteres wird erstellt, indem die folgenden Werte mit dem C++ **or** -Operator kombiniert werden:

- MSG_DONTROUTE gibt an, dass für die Daten kein Routing unterliegen soll. Ein Windows Sockets-Lieferant kann dieses Flag ignorieren.

- MSG_OOB Senden von Out-of-Band-Daten (nur SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Wenn kein Fehler auftritt, `SendToEx` wird die Gesamtzahl der gesendeten Zeichen zurückgegeben. (Beachten Sie, dass dies kleiner als die Zahl sein kann, die durch *nbuslen*angegeben wird.) Andernfalls wird der Wert "SOCKET_ERROR" zurückgegeben, und ein bestimmter Fehlercode kann durch Aufrufen von " [GetLastError](#getlasterror)" abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- WSAEACCES die angeforderte Adresse ist eine Broadcast Adresse, das entsprechende Flag wurde jedoch nicht festgelegt.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaefault die *lpbuf* -oder *lpsockaddr* -Parameter sind nicht Teil des Benutzer Adressraums, oder das *lpsockaddr* -Argument ist zu klein (weniger als die Größe einer [sockaddr](/windows/win32/winsock/sockaddr-2) -Struktur).

- WSAEINVAL der Hostname ist ungültig.

- Wsaenetreset die Verbindung muss zurückgesetzt werden, da Sie von der Windows Sockets-Implementierung gelöscht wurde.

- WSAENOBUFS die Windows Sockets-Implementierung meldet einen Puffer Deadlock.

- Wsaumotconn der Socket ist nicht verbunden (nur SOCK_STREAM).

- Wsaenotsock der Deskriptor ist kein Socket.

- WSAEOPNOTSUPP MSG_OOB wurde angegeben, aber der Socket ist nicht vom Typ SOCK_STREAM.

- WSAESHUTDOWN: der Socket wurde heruntergefahren. Es ist nicht möglich, für `SendToEx` einen Socket aufzurufen `ShutDown` , nachdem mit *Nhow* aufgerufen wurde, der auf 1 oder 2 festgelegt ist.

- WSAEWOULDBLOCK der Socket ist als nicht blockierend markiert, und der angeforderte Vorgang würde blockieren.

- Wsaemsgsize der Socket weist den Typ SOCK_DGRAM auf, und das Datagramm ist größer als das Maximum, das von der Windows Sockets-Implementierung unterstützt wird.

- WSAECONNABORTED die virtuelle Verbindung wurde aufgrund eines Timeouts oder eines anderen Fehlers abgebrochen.

- WSAECONNRESET die virtuelle Verbindung wurde von der Remote Seite zurückgesetzt.

- Wsaeaddrnotavail die angegebene Adresse ist auf dem lokalen Computer nicht verfügbar.

- WSAEAFNOSUPPORT-Adressen in der angegebenen Familie können nicht mit diesem Socket verwendet werden.

- WSAEDESTADDRREQ eine Zieladresse ist erforderlich.

- Wsaumetunreach das Netzwerk kann von diesem Host zurzeit nicht erreicht werden.

### <a name="remarks"></a>Hinweise

Diese Methode ist mit [CAsyncSocket:: sendto](#sendto) identisch, mit der Ausnahme, dass Sie sowohl IPv6-Adressen als auch ältere Protokolle verarbeitet.

`SendToEx`wird für Datagramm oder Streamsockets verwendet und zum Schreiben von ausgehenden Daten in einem Socket verwendet. Für Datagramm-Sockets muss die maximale IP-Paketgröße der zugrunde liegenden Subnetze, die durch das `iMaxUdpDg` -Element in der [wsadata](/windows/win32/api/winsock2/ns-winsock2-wsadata) -Struktur, die von [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)ausgefüllt wird, nicht überschritten werden. Wenn die Daten zu lang sind, um atomisch über das zugrunde liegende Protokoll zu übergeben, wird der Fehler "wsaemsgsize" zurückgegeben, und es werden keine Daten übertragen.

Beachten Sie, dass der erfolgreiche Abschluss `SendToEx` eines-Befehls nicht anzeigt, dass die Daten erfolgreich übermittelt wurden.

`SendToEx`wird nur in einem SOCK_DGRAM-Socket verwendet, um ein Datagramm an einen bestimmten Socket zu senden, der durch den *lpsockaddr* -Parameter identifiziert wird.

Um eine Übertragung zu senden (nur auf einem SOCK_DGRAM), sollte die Adresse im *lpsockaddr* -Parameter mit der speziellen IP-Adresse INADDR_BROADCAST (definiert in der Windows Sockets-Header Datei Winsock) erstellt werden. H) in Verbindung mit der vorgesehenen Portnummer. Wenn der *lpszhustaddress* -Parameter den Wert NULL hat, wird der Socket für die Übertragung konfiguriert. Es ist in der Regel nicht ratsam, dass ein Broadcast Datagramm die Größe überschreitet, mit der die Fragmentierung auftreten kann. Dies impliziert, dass der Datentyp des Datagramms (ausgenommen Header) 512 Bytes nicht überschreiten darf.

##  <a name="setsockopt"></a>CAsyncSocket:: setsockopt

Mit dieser Member-Funktion können Sie eine Socketoption festlegen.

```
BOOL SetSockOpt(
    int nOptionName,
    const void* lpOptionValue,
    int nOptionLen,
    int nLevel = SOL_SOCKET);
```

### <a name="parameters"></a>Parameter

*nOptionName*<br/>
Die Socketoption, für die der Wert festgelegt werden soll.

*lpOptionValue*<br/>
Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option angegeben wird.

*nOptionLen*<br/>
Die Größe des *lpoptionvalue* -Puffers in Bytes.

*nLevel*<br/>
Die Ebene, auf der die Option definiert ist. die einzigen unterstützten Ebenen sind SOL_SOCKET und IPPROTO_TCP.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsaefault *lpoptionvalue* befindet sich nicht in einem gültigen Teil des Prozess Adressraums.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- WSAEINVAL *Nlevel* ist ungültig, oder die Informationen in *lpoptionvalue* sind ungültig.

- Timeout bei der wsaenetreset-Verbindung, wenn SO_KEEPALIVE festgelegt wird.

- Wsakooprodeopt die Option ist unbekannt oder wird nicht unterstützt. SO_BROADCAST wird insbesondere für Sockets vom Typ SOCK_STREAM nicht unterstützt, während SO_DONTLINGER, SO_KEEPALIVE, SO_LINGER und SO_OOBINLINE bei Sockets vom Typ SOCK_DGRAM nicht unterstützt werden.

- Die wsaenotconn-Verbindung wurde zurückgesetzt, wenn SO_KEEPALIVE festgelegt ist.

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

`SetSockOpt`Legt den aktuellen Wert für eine Socketoption fest, die einem Socket eines beliebigen Typs in einem beliebigen Zustand zugeordnet ist. Obwohl Optionen auf mehreren Protokoll Ebenen vorhanden sein können, definiert diese Spezifikation nur Optionen, die auf der obersten Ebene "Socket" vorhanden sind. Optionen wirken sich auf Socketvorgänge aus, z. b. ob beschleunigte Daten im normalen Datenstream empfangen werden, ob Broadcast Nachrichten auf dem Socket gesendet werden können usw.

Es gibt zwei Arten von Socketoptionen: Boolesche Optionen, die ein Feature oder Verhalten aktivieren bzw. deaktivieren, sowie Optionen, die einen ganzzahligen Wert oder eine ganzzahlige Struktur erfordern. Um eine boolesche Option zu aktivieren, verweist *lpoptionvalue* auf eine ganze Zahl ungleich 0 (null). Um die Option zu deaktivieren, verweist *lpoptionvalue* auf eine Ganzzahl, die gleich NULL ist. *noptionlen* sollte `sizeof(BOOL)` für boolesche Optionen gleich sein. Bei anderen Optionen zeigt *lpoptionvalue* auf die ganze Zahl oder Struktur, die den gewünschten Wert für die Option enthält, und *noptionlen* ist die Länge der Ganzzahl oder Struktur.

SO_LINGER steuert die Aktion, die ausgeführt wird, wenn nicht gesendete Daten in einem Socket `Close` in die Warteschlange eingereiht werden und die Funktion zum Schließen des Sockets aufgerufen wird.

Standardmäßig kann ein Socket (siehe [Bind](#bind)) nicht an eine lokale Adresse gebunden werden, die bereits verwendet wird. Gelegentlich kann es jedoch wünschenswert sein, eine Adresse auf diese Weise wiederzuverwenden. Da jede Verbindung durch die Kombination aus lokalen und Remote Adressen eindeutig identifiziert wird, gibt es kein Problem, wenn zwei Sockets an dieselbe lokale Adresse gebunden sind, solange sich die Remote Adressen unterscheiden.

Um die Windows Sockets-Implementierung darüber zu `Bind` informieren, dass ein Rückruf für einen Socket nicht zulässig sein soll, da die gewünschte Adresse bereits von einem anderen Socket verwendet wird, sollte die Anwendung die SO_REUSEADDR-Socketoption für den Socket festlegen, bevor das `Bind` aufgerufen wird. Beachten Sie, dass die Option nur zum Zeitpunkt des `Bind` Aufrufes interpretiert wird: Es ist daher unnötig (aber harmlos), die Option für einen Socket festzulegen, der nicht an eine vorhandene Adresse gebunden werden soll, und die Option festzulegen oder zurückzusetzen, nachdem der `Bind` Aufruf erfolgt ist. keine Auswirkung auf diesen oder einen anderen Socket.

Eine Anwendung kann anfordern, dass die Windows Sockets-Implementierung die Verwendung von Keep-Alive-Paketen für TCP (Transmission Control Protocol)-Verbindungen ermöglicht, indem die SO_KEEPALIVE-Socketoption aktiviert wird. Eine Windows Sockets-Implementierung muss die Verwendung von "Keep-Alives" nicht unterstützen: Wenn dies der Fall ist, ist die genaue Semantik Implementierungs spezifisch, sollte jedoch dem Abschnitt 4.2.3.6 of RFC 1122 entsprechen: "Anforderungen für Internet Hosts – Kommunikations Schichten". Wenn eine Verbindung als Ergebnis von "Keep-Alives" gelöscht wird, wird der Fehlercode wsaenetreset an alle Aufrufe zurückgegeben, die im Socket ausgeführt werden, und alle nachfolgenden Aufrufe schlagen mit wsaenotconn fehl.

Die Option TCP_NODELAY deaktiviert den Nagle-Algorithmus. Der Nagle-Algorithmus wird verwendet, um die Anzahl von kleinen Paketen zu verringern, die von einem Host gesendet werden, indem nicht bestätigte Sendedaten gepuffert werden, bis ein Paket mit vollständiger Größe gesendet werden kann. Bei manchen Anwendungen kann dieser Algorithmus jedoch die Leistung beeinträchtigen, und TCP_NODELAY kann verwendet werden, um ihn zu deaktivieren. Anwendungs Schreiber sollten TCP_NODELAY nur dann festlegen, wenn die Auswirkungen auf diese Weise gut verstanden und erwünscht sind, da das Festlegen von TCP_NODELAY eine erhebliche negative Auswirkung auf die Netzwerkleistung haben kann. TCP_NODELAY ist die einzige unterstützte Socketoption, die Level IPPROTO_TCP verwendet. alle anderen Optionen verwenden Ebene SOL_SOCKET.

Einige Implementierungen von Windows Sockets geben Ausgabe Debuginformationen an, wenn die SO_DEBUG-Option von einer Anwendung festgelegt wird.

Die folgenden Optionen werden für `SetSockOpt`unterstützt. Der Typ identifiziert den Typ der Daten, die von *lpoptionvalue*adressiert werden.

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_BROADCAST|BOOL|Ermöglicht das Übertragen von Broadcast Nachrichten auf dem Socket.|
|SO_DEBUG|BOOL|Zeichnet Debuginformationen auf.|
|SO_DONTLINGER|BOOL|Blockieren `Close` Sie nicht, dass auf nicht gesendete Daten gesendet werden. Das Festlegen dieser Option entspricht der Festlegung von `l_onoff` SO_LINGER, wobei auf NULL festgelegt ist.|
|SO_DONTROUTE|BOOL|Nicht weiterleiten: direkt an Schnittstelle senden.|
|SO_KEEPALIVE|BOOL|Senden Sie Keep-Alives.|
|SO_LINGER|`struct LINGER`|Verweilen, `Close` wenn nicht gesendete Daten vorhanden sind.|
|SO_OOBINLINE|BOOL|Empfangen von Out-of-Band-Daten im normalen Datenstream.|
|SO_RCVBUF|**int**|Geben Sie die Puffergröße für Empfangs Vorgänge an.|
|SO_REUSEADDR|BOOL|Zulassen, dass der Socket an eine Adresse gebunden ist, die bereits verwendet wird. (Siehe [Bind](#bind).)|
|SO_SNDBUF|**int**|Geben Sie die Puffergröße für Sende Vorgänge an.|
|TCP_NODELAY|BOOL|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|

Die Optionen von Berkeley Software Distribution (BSD) werden `SetSockOpt` für nicht unterstützt:

|Wert|Typ|Bedeutung|
|-----------|----------|-------------|
|SO_ACCEPTCONN|BOOL|Socket lauscht|
|SO_ERROR|**int**|Fehlerstatus erhalten und löschen.|
|SO_RCVLOWAT|**int**|Niedrige Wasser Grenze empfangen.|
|SO_RCVTIMEO|**int**|Empfangs Timeout|
|SO_SNDLOWAT|**int**|Niedrige Wasser Grenze senden.|
|SO_SNDTIMEO|**int**|Timeout für Sendevorgang.|
|SO_TYPE|**int**|Der Typ des Sockets.|
|IP_OPTIONS||Legen Sie das Optionsfeld im IP-Header fest.|

##  <a name="shutdown"></a>CAsyncSocket:: Shutdown

Mit dieser Member-Funktion können Sie Sende-, Empfangs-oder beides im Socket deaktivieren.

```
BOOL ShutDown(int nHow = sends);
```

### <a name="parameters"></a>Parameter

*Nhow*<br/>
Ein Flag, das beschreibt, welche Typen von Operation nicht mehr zulässig sind. dabei werden die folgenden Enumerationswerte verwendet:

- **empfängt = 0**

- **sendet = 1**

- **both = 2**

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Funktion erfolgreich ist. Andernfalls kann der Wert 0 und ein bestimmter Fehlercode durch Aufrufen von [GetLastError](#getlasterror)abgerufen werden. Die folgenden Fehler sind für diese Member-Funktion anwendbar:

- Wsanotinitialisierte ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) muss vor der Verwendung dieser API erfolgen.

- Wsaaufetdown die Windows Sockets-Implementierung hat erkannt, dass das Netzwerk Subsystem ausgefallen ist.

- Wsainval *Nhow* ist ungültig.

- WSAEINPROGRESS ein blockierender Windows Sockets-Vorgang wird ausgeführt.

- Wsaumotconn der Socket ist nicht verbunden (nur SOCK_STREAM).

- Wsaenotsock der Deskriptor ist kein Socket.

### <a name="remarks"></a>Hinweise

`ShutDown`wird für alle Socketypen verwendet, um den Empfang, die Übertragung oder beides zu deaktivieren. Wenn *Nhow* den Wert 0 hat, werden nachfolgende Empfangs Vorgänge im Socket nicht zugelassen. Dies hat keine Auswirkung auf die niedrigeren Protokoll Ebenen.

Für das TCP (Transmission Control Protocol) wird das TCP-Fenster nicht geändert, und eingehende Daten werden akzeptiert (aber nicht bestätigt), bis das Fenster erschöpft ist. Für UDP (User Datagram Protocol) werden eingehende Datagramme akzeptiert und in die Warteschlange eingereiht. In keinem Fall wird ein ICMP-Fehler Paket generiert. Wenn *Nhow* 1 ist, sind nachfolgende Sende Vorgänge nicht zulässig. Bei TCP-Sockets wird eine FIN gesendet. Wenn Sie " *Nhow* to 2" festlegen, werden Sende-und Empfangs Vorgänge wie oben beschrieben deaktiviert.

Beachten Sie `ShutDown` , dass den Socket nicht schließt und dass an den Socket angefügte Ressourcen erst freigegeben `Close` werden, wenn aufgerufen wird. Eine Anwendung sollte sich nicht darauf verlassen, dass ein Socket nach dem Herunterfahren wieder verwendet werden kann. Insbesondere ist eine Windows Sockets-Implementierung nicht erforderlich, um die Verwendung von `Connect` auf einem solchen Socket zu unterstützen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CAsyncSocket:: OnReceive](#onreceive).

##  <a name="socket"></a>CAsyncSocket:: Socket

Ordnet ein Sockethandle zu.

```
BOOL Socket(
    int nSocketType = SOCK_STREAM,
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,
    int nProtocolType = 0,
    int nAddressFormat = PF_INET);
```

### <a name="parameters"></a>Parameter

*nSocketType*<br/>
Gibt `SOCK_STREAM` oder`SOCK_DGRAM`an.

*lEvent*<br/>
Eine Bitmaske, die eine Kombination von Netzwerk Ereignissen angibt, an denen die Anwendung interessiert ist.

- `FD_READ`: Sie möchten eine Benachrichtigung über die Bereitschaft zum Lesen erhalten.

- `FD_WRITE`: Sie möchten eine Benachrichtigung über die Bereitschaft zum Schreiben erhalten.

- `FD_OOB`: Sie möchten eine Benachrichtigung über die Ankunft von Out-of-Band-Daten erhalten.

- `FD_ACCEPT`: Sie möchten eine Benachrichtigung über eingehende Verbindungen erhalten.

- `FD_CONNECT`: Sie möchten eine Benachrichtigung über die abgeschlossene Verbindung erhalten.

- `FD_CLOSE`: Sie möchten eine Benachrichtigung über den Socket-Abschluss erhalten.

*nProtocolType*<br/>
Das Protokoll, das mit dem Socket verwendet werden soll, der spezifisch für die angegebene Adressfamilie ist.

*nAddressFormat*<br/>
Spezifikation der Adressfamilie.

### <a name="return-value"></a>Rückgabewert

Gibt `TRUE` bei Erfolg bzw. `FALSE` bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode ordnet ein Sockethandle zu. [CAsyncSocket:: Bind](#bind) wird nicht aufgerufen, um den Socket an eine angegebene Adresse zu binden, sodass Sie später einen `Bind` Rückruf ausführen müssen, um den Socket an eine angegebene Adresse zu binden. Sie können [CAsyncSocket:: setsockopt](#setsockopt) verwenden, um die Socketoption festzulegen, bevor Sie gebunden wird.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CSocket-Klasse](../../mfc/reference/csocket-class.md)<br/>
[CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)
