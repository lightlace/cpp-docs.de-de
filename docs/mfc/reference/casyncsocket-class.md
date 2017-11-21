---
title: CAsyncSocket-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1043273a7a0c8d34428289664b651ccb158a8e9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="casyncsocket-class"></a>CAsyncSocket-Klasse
Stellt eine Windows Socket dar – ein Endpunkt der Netzwerkkommunikation.  
  
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
|[CAsyncSocket::Accept](#accept)|Akzeptiert eine Verbindung auf den Socket.|  
|[CAsyncSocket::AsyncSelect](#asyncselect)|Anforderungen-ereignisbenachrichtigung für den Socket.|  
|[CAsyncSocket::Attach](#attach)|Fügt ein Sockethandle für ein `CAsyncSocket` Objekt.|  
|[CAsyncSocket::Bind](#bind)|Ordnet eine lokale Adresse den Socket.|  
|[CAsyncSocket::Close](#close)|Schließt den Socket.|  
|[CAsyncSocket:: Connect](#connect)|Herstellen einer Verbindung mit einem Peer-Socket.|  
|[CAsyncSocket::Create](#create)|Ein Socket erstellt.|  
|[CAsyncSocket::Detach](#detach)|Trennt ein Sockethandle aus einem `CAsyncSocket` Objekt.|  
|[CAsyncSocket::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CAsyncSocket` -Objekt, ein Sockethandle.|  
|[CAsyncSocket::GetLastError](#getlasterror)|Ruft den Fehlerstatus für den letzten Vorgang, die nicht an.|  
|[CAsyncSocket::GetPeerName](#getpeername)|Ruft die Adresse des Sockets Peer mit dem der Socket verbunden ist.|  
|[CAsyncSocket::GetPeerNameEx](#getpeernameex)|Ruft die Adresse des Sockets Peer, der der Socket verbunden ist (Handles IPv6-Adressen) ist.|  
|[CAsyncSocket::GetSockName](#getsockname)|Ruft den lokalen Namen eines Sockets ab.|  
|[CAsyncSocket::GetSockNameEx](#getsocknameex)|Ruft den lokalen Namen eines Sockets (Handles IPv6-Adressen).|  
|[CAsyncSocket::GetSockOpt](#getsockopt)|Ruft ein Socket-Option ab.|  
|[CAsyncSocket::IOCtl](#ioctl)|Steuert den Modus des Sockets.|  
|[CAsyncSocket:: Listen](#listen)|Stellt ein Socket zum Abhören von eingehenden verbindungsanforderungen her.|  
|[CAsyncSocket::Receive](#receive)|Empfängt Daten von den Socket.|  
|[CAsyncSocket::ReceiveFrom](#receivefrom)|Empfängt ein Datagramm und speichert die Quelladresse.|  
|[CAsyncSocket::ReceiveFromEx](#receivefromex)|Empfängt ein Datagramm und speichert die Quelladresse (Handles IPv6-Adressen).|  
|[CAsyncSocket::Send](#send)|Sendet Daten an einen verbundenen Socket.|  
|[Einsatz](#sendto)|Sendet Daten an ein bestimmtes Ziel.|  
|[CAsyncSocket::SendToEx](#sendtoex)|Sendet Daten an ein bestimmtes Ziel (Handles IPv6-Adressen).|  
|[CAsyncSocket::SetSockOpt](#setsockopt)|Wird eine Socketoption festgelegt.|  
|[CAsyncSocket::ShutDown](#shutdown)|Deaktiviert die **senden** und/oder **Receive** Ruft für den Socket.|  
|[CASyncSocket::Socket](#socket)|Reserviert ein Sockethandle.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::OnAccept](#onaccept)|Benachrichtigt ein empfangsbereiten Sockets, die er ausstehenden verbindungsanforderungen, durch den Aufruf annehmen kann **Accept**.|  
|[CAsyncSocket::OnClose](#onclose)|Benachrichtigt, dass ein Socket, die mit der Socket geschlossen ist.|  
|[CAsyncSocket::OnConnect](#onconnect)|Benachrichtigt einem verbundenen Socket, dass der Verbindungsversuch abgeschlossen ist, gibt an, ob erfolgreich oder fehlerhaft ist.|  
|[CAsyncSocket::OnOutOfBandData](#onoutofbanddata)|Benachrichtigt einem empfangenden Socket, ergibt sich Out-of-Band-Daten auf den Socket, in der Regel eine dringende Nachricht gelesen werden.|  
|[CAsyncSocket::OnReceive](#onreceive)|Benachrichtigt einem empfangsbereiten Sockets, dass Daten durch den Aufruf abgerufen werden sollen **Receive**.|  
|[CAsyncSocket::OnSend](#onsend)|Benachrichtigt einem Socket, dass er Daten, durch den Aufruf senden kann **senden**.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::operator =](#operator_eq)|Weist einen neuen Wert zu einem `CAsyncSocket` Objekt.|  
|[CAsyncSocket::operator SOCKET](#operator_socket)|Verwenden Sie diesen Operator zum Abrufen der **SOCKET** Handles aus dem `CAsyncSocket` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAsyncSocket::m_hSocket](#m_hsocket)|Gibt an, die **SOCKET** Handle angefügte `CAsyncSocket` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Klasse `CAsyncSocket` kapselt das Windows Socket Funktionen-API bietet eine Abstraktion eines objektorientierten für Programmierer, die Windows-Sockets in Verbindung mit MFC verwendet werden soll.  
  
 Diese Klasse wird davon ausgegangen, dass Sie wissen, dass die Netzwerkkommunikation. Sie sind verantwortlich für die Behandlung von Blockierungen Bytereihenfolge Unterschiede, und legen Sie Konvertierungen zwischen Unicode- und multibyte-Zeichensätze (MBCS)-Zeichenfolgen. Soll eine besser geeignete Benutzeroberfläche, die diese Probleme für Sie verwaltet wird, finden Sie in der Klasse [CSocket](../../mfc/reference/csocket-class.md).  
  
 Verwenden einer `CAsyncSocket` Objekt, dessen Konstruktor aufrufen rufen Sie anschließend die [erstellen](#create) Funktion zum Erstellen der zugrunde liegenden Socket-Handle (Typ `SOCKET`), außer für akzeptierte Sockets. Für einen Server-Socket-Aufruf die [Lauschen](#listen) Memberfunktion ist, und für einen Client-Socket-Aufruf die [verbinden](#connect) Memberfunktion. Die Serversocket aufrufen sollte die [Accept](#accept) Funktion nach dem Empfang einer verbindungsanforderung. Verwenden Sie die verbleibenden `CAsyncSocket` Funktionen, um die Kommunikation zwischen Sockets durchzuführen. Nach Abschluss des Vorgangs Zerstören der `CAsyncSocket` Objekt, wenn es auf dem Heap erstellt wurde, ruft der Destruktor automatisch die [schließen](#close) Funktion. Die `SOCKET` -Datentyp ist im Artikel beschriebenen [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).  
  
> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC_Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jedem Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. Standardmäßig `AfxSocketInit` nur im primären Thread aufgerufen wird.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von CAsyncSocket-Klasse](../../mfc/windows-sockets-using-class-casyncsocket.md) und verwandten Artikeln., sowie [Windows Sockets-2-API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Ein Verweis, identifizieren einen neuen Socket, der für die Verbindung verfügbar ist.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) socket-Struktur, die die Adresse des verbindenden empfängt, als im Netzwerk bezeichnet. Das genaue Format des der `lpSockAddr` Argument richtet sich nach der Adressfamilie hergestellt, wenn der Socket erstellt wurde. Wenn `lpSockAddr` und/oder `lpSockAddrLen` gleich **NULL**, und klicken Sie dann keine Informationen über die remote-Adresse eines angenommenen Sockets zurückgegeben wird.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Adresse in `lpSockAddr` in Bytes. Die `lpSockAddrLen` ist ein Wert als Ergebnis Parameter: Es sollte die Menge des Speicherplatzes verweist anfänglich enthalten `lpSockAddr`; bei der Rückgabe die tatsächliche Länge (in Bytes) der Adresse zurückgegeben enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist zu klein (kleiner als die Größe von einem [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **"WSAEINPROGRESS" zurück** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAEINVAL** `Listen` konnte nicht vor accept aufgerufen.  
  
- **WSAEMFILE** der Warteschlange beim Eintritt akzeptieren leer ist, und es sind keine Dateideskriptoren verfügbar.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP** referenzierte Socket ist kein Typ, die einem verbindungsorientierten Dienst unterstützt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und es sind keine Verbindungen vorhanden, um akzeptiert zu werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Routine extrahiert die erste Verbindung in die Warteschlange für ausstehende Verbindungen, wird einen neuen Socket mit denselben Eigenschaften wie diesem Socket erstellt und fügt es `rConnectedSocket`. Wenn keine ausstehenden Verbindungen in der Warteschlange vorhanden sind **Accept** gibt NULL zurück und `GetLastError` gibt einen Fehler zurück. Die angenommenen Sockets ( *rConnectedSocket)* kann nicht verwendet werden, um weitere Verbindungen akzeptiert. Der ursprüngliche Socket bleibt geöffnet, und überwacht.  
  
 Das Argument `lpSockAddr` ist ein Ergebnisparameter, der mit der Adresse des verbundenen Sockets ausgefüllt wird, wie die Kommunikation Ebene bekannt. **Akzeptieren Sie** wird verwendet, mit verbindungsorientierten Sockettypen wie z. B. **SOCK_STREAM**.  
  
##  <a name="asyncselect"></a>CAsyncSocket::AsyncSelect  
 Rufen Sie diese Memberfunktion zum Anfordern der ereignisbenachrichtigung für ein Socket.  
  
```  
BOOL AsyncSelect(long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- **FD_READ maskiert** Bereitschaft zum Lesen eine Benachrichtigung erhalten möchten.  
  
- **FD_WRITE** möchten Sie die Benachrichtigung erhalten, wenn Daten gelesen werden kann.  
  
- **FD_OOB** Benachrichtigung über den Eingang von Out-of-Band-Daten empfangen soll.  
  
- **FD_ACCEPT** Benachrichtigungen zu eingehenden Verbindungen werden soll.  
  
- **FD_CONNECT** Verbindung bewirkt eine Benachrichtigung erhalten möchten.  
  
- **FD_CLOSE** möchten Sie die Benachrichtigung erhalten, wenn ein Socket von einem Peer geschlossen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEINVAL** gibt an, dass einer der angegebenen Parameter ungültig war.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um anzugeben, welche MFC Benachrichtigung Rückruffunktionen für den Socket aufgerufen werden. `AsyncSelect`legt automatisch diesem Socket nicht blockierenden Modus fest. Weitere Informationen finden Sie im Artikel [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="attach"></a>CAsyncSocket::Attach  
 Rufen Sie diese Memberfunktion für die Verbindung der `hSocket` handle für ein `CAsyncSocket` Objekt.  
  
```  
BOOL Attach(
    SOCKET hSocket, long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE);
```  
  
### <a name="parameters"></a>Parameter  
 `hSocket`  
 Enthält ein Handle für ein Socket.  
  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- **FD_READ maskiert** Bereitschaft zum Lesen eine Benachrichtigung erhalten möchten.  
  
- **FD_WRITE** möchten Sie die Benachrichtigung erhalten, wenn Daten gelesen werden kann.  
  
- **FD_OOB** Benachrichtigung über den Eingang von Out-of-Band-Daten empfangen soll.  
  
- **FD_ACCEPT** Benachrichtigungen zu eingehenden Verbindungen werden soll.  
  
- **FD_CONNECT** Verbindung bewirkt eine Benachrichtigung erhalten möchten.  
  
- **FD_CLOSE** möchten Sie die Benachrichtigung erhalten, wenn ein Socket von einem Peer geschlossen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich null, wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Die **SOCKET** Handle wird gespeichert, in des Objekts [M_hSocket](#m_hsocket) -Datenmember.  
  
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
 Der Port, die Socket-Anwendung identifizieren.  
  
 `lpszSocketAddress`  
 Die Netzwerkadresse einer gepunkteten Zahl wie "128.56.22.8". Übergeben der **NULL** Zeichenfolge für diesen Parameter gibt an, die **CAsyncSocket** Instanz für die Clientaktivität an allen Netzwerkschnittstellen überwacht werden soll.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur, die die Adresse dieser Socket zuzuweisende enthält.  
  
 `nSockAddrLen`  
 Die Länge der Adresse in `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEADDRINUSE** die angegebene Adresse wird bereits verwendet. (Siehe die **SO_REUSEADDR** socket-Option "unter" [SetSockOpt](#setsockopt).)  
  
- **WSAEFAULT** der `nSockAddrLen` Argument ist zu klein (kleiner als die Größe von einem [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **"WSAEINPROGRESS" zurück** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **** Der angegebenen Adressfamilie wird von dieser Port nicht unterstützt.  
  
- **WSAEINVAL** der Socket ist bereits an eine Adresse gebunden.  
  
- `WSAENOBUFS`Nicht genügend Puffer verfügbar ist, zu viele Verbindungen.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Diese Routine dient auf einem unverbundenen Datagramm oder einem Streamsocket, vor dem nachfolgenden **verbinden** oder `Listen` aufrufen. Bevor er verbindungsanforderungen annehmen kann, einem Abhörsocket Server muss auswählen eine Portnummer und bekannte für Windows Sockets durch Aufrufen von **binden**. **Binden Sie** richtet die lokale Zuordnung (Host-Adresse/Port-Nummer) des Sockets durch einen unbenannten Socket einen lokalen Namen zuweisen.  
  
##  <a name="casyncsocket"></a>CAsyncSocket::CAsyncSocket  
 Erstellt einen leeren Socketobjekt.  
  
```  
CAsyncSocket();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie die **erstellen** Memberfunktion zum Erstellen der **SOCKET** Daten strukturieren und seine Adresse binden. (Beim Erstellen der Abhörsocket ein Socket für die Verwendung in einer Windows-Sockets Kommunikation auf dem Server die **Accept** Aufruf, rufen Sie nicht **erstellen** für diese Socket.)  
  
##  <a name="close"></a>CAsyncSocket::Close  
 Schließt den Socket.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt die Socket-Deskriptor frei, sodass Weitere Verweise darauf mit dem Fehler fehl **WSAENOTSOCK**. Ist dies der letzte Verweis auf den zugrunde liegenden Socket, werden die zugehörigen Namensinformationen und die Daten in der Warteschlange verworfen. Das Socketobjekt Destruktoraufrufe **schließen** für Sie.  
  
 Für `CAsyncSocket`, jedoch nicht für `CSocket`, die Semantik der **schließen** sind von den Socketoptionen betroffen **SO_LINGER** und **SO_DONTLINGER**. Weitere Informationen finden Sie unter Memberfunktion `GetSockOpt`.  
  
##  <a name="connect"></a>CAsyncSocket:: Connect  
 Rufen Sie diese Memberfunktion zum Herstellen einer Verbindung mit einem unverbundenen Stream oder einen Datagrammsocket.  
  
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
 Die Netzwerkadresse des Sockets mit dem dieses Objekt verbunden ist: einen Computernamen ein, z. B. "ftp.microsoft.com" oder einer gepunkteten Zahl wie "128.56.22.8".  
  
 `nHostPort`  
 Der Port, die Socket-Anwendung identifizieren.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur, die die Adresse des verbundenen Sockets enthält.  
  
 `nSockAddrLen`  
 Die Länge der Adresse in `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Wenn dies ein Fehlercode gibt an **WSAEWOULDBLOCK**, und der Anwendung die überschreibbare Rückrufe verwendet wird, empfängt die Anwendung eine `OnConnect` Meldung, wenn Sie der Verbindungsvorgang abgeschlossen ist. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEADDRINUSE** die angegebene Adresse wird bereits verwendet.  
  
- **"WSAEINPROGRESS" zurück** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.  
  
- **STARK** Verbindungsversuch wurde zurückgewiesen.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAEFAULT** der `nSockAddrLen` Argument ist falsch.  
  
- **WSAEINVAL** ungültige Host-Adresse.  
  
- **WSAEISCONN** der Socket ist bereits verbunden.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- **WSAENETUNREACH** im Netzwerk kann nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar. Der Socket kann nicht verbunden werden.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAETIMEDOUT** Versuch der verbindungsherstellung Zeitlimit ohne eine Verbindung herzustellen.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und die Verbindung nicht sofort abgeschlossen werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Socket ungebundenen, eindeutige Werte der lokalen Zuordnung vom System zugewiesen sind, und der Socket als markiert ist gebunden. Beachten Sie, wenn das Feld für die Adresse der Namensstruktur wird alle Nullen (0) **verbinden** 0 (null) zurück. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die `GetLastError` Memberfunktion.  
  
 Für Streamsockets (Typ **SOCK_STREAM**), wird eine aktive Verbindung mit dem Fremdschlüssel Host initiiert. Nach erfolgreichem der Socket-Aufruf Abschluss ist der Socket zum Senden/Empfangen von Daten bereit.  
  
 Für einen Datagrammsocket (Typ **SOCK_DGRAM**), ein Standardziel festgelegt ist, wird in nachfolgenden verwendet werden **senden** und **Receive** aufrufen.  
  
##  <a name="create"></a>CAsyncSocket::Create  
 Rufen Sie die **erstellen** Memberfunktion nach dem Erstellen einer Socketobjekt, um die Windows Socket erstellt und angefügt.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    long lEvent = FD_READ | FD_WRITE | FD_OOB | FD_ACCEPT | FD_CONNECT | FD_CLOSE,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nSocketPort`  
 Ein bekannter Port mit der Socket oder 0 verwendet werden soll, wenn Sie Windows-Sockets auf einen Port auswählen möchten.  
  
 `nSocketType`  
 **SOCK_STREAM** oder **SOCK_DGRAM**.  
  
 `lEvent`  
 Eine Bitmaske, die eine Kombination von Netzwerkereignisse gibt an, in dem die Anwendung interessiert ist.  
  
- **FD_READ maskiert** Bereitschaft zum Lesen eine Benachrichtigung erhalten möchten.  
  
- **FD_WRITE** Bereitschaft zum Schreiben eine Benachrichtigung erhalten möchten.  
  
- **FD_OOB** Benachrichtigung über den Eingang von Out-of-Band-Daten empfangen soll.  
  
- **FD_ACCEPT** Benachrichtigungen zu eingehenden Verbindungen werden soll.  
  
- **FD_CONNECT** abgeschlossene Verbindung eine Benachrichtigung erhalten möchten.  
  
- **FD_CLOSE** der Socket Schließvorgänge Benachrichtigung erhalten möchten.  
  
 *lpszSockAddress*  
 Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets, einer gepunkteten Zahl wie "128.56.22.8" enthält. Übergeben der **NULL** Zeichenfolge für diesen Parameter gibt an, die **CAsyncSocket** Instanz für die Clientaktivität an allen Netzwerkschnittstellen überwacht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **** Der angegebenen Adressfamilie wird nicht unterstützt.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar. Der Socket kann nicht erstellt werden.  
  
- **WSAEPROTONOSUPPORT** der angegebene Port wird nicht unterstützt.  
  
- **WSAEPROTOTYPE** der angegebene Port hat den falschen Typ für diesen Socket.  
  
- **WSAESOCKTNOSUPPORT** der angegebenen Sockettyp wird in dieser Adressfamilie nicht unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** Aufrufe [Socket](#socket) und bei Erfolg, ruft [binden](#bind) der Socket an die angegebene Adresse binden. Die folgenden Sockettypen werden unterstützt:  
  
- **SOCK_STREAM** sequenziert, bietet zuverlässige Vollduplex, Verbindungsbasiert Bytestreams. Das Protokoll TCP (Transmission Control) verwendet für die Internetadressenfamilie.  
  
- **SOCK_DGRAM** Datagramme, die Verbindungs- und unzuverlässige Pakete, die eine feste (normalerweise klein), maximale Länge werden unterstützt. Verwendet das User Datagram Protocol (UDP) für die Internetadressenfamilie an.  
  
    > [!NOTE]
    >  Die **Accept** Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Sie müssen dieses Objekt erstellen, vor dem Aufruf **Accept**. Beachten Sie, dass wenn dieser Socketobjekt des Bereichs, die Verbindung geschlossen wird. Rufen Sie nicht **erstellen** für dieses neue Socketobjekt.  
  
> [!IMPORTANT]
> **Erstellen Sie** ist **nicht** threadsicher.  Beim Aufrufen es in einer Multithread-Umgebung, in denen konnten sie gleichzeitig von verschiedenen Threads aufgerufen werden, müssen Sie jeden Aufruf mit einem Mutex oder andere Synchronisierungssperre zu schützen.  
  
 Weitere Informationen zu Stream als auch datagrammnachrichten Sockets, finden Sie in den Artikeln [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md) und [Windows Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md) und [APIvonWindowsSockets2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="detach"></a>CAsyncSocket::Detach  
 Rufen Sie diese Memberfunktion zum Trennen der **SOCKET** in behandelt die `m_hSocket` Datenmember aus der `CAsyncSocket` Objekt, und `m_hSocket` auf **NULL**.  
  
```  
SOCKET Detach();
```  
  
##  <a name="fromhandle"></a>CAsyncSocket::FromHandle  
 Gibt einen Zeiger auf eine `CAsyncSocket` Objekt.  
  
```  
static CAsyncSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parameter  
 `hSocket`  
 Enthält ein Handle für ein Socket.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CAsyncSocket` -Objekt, oder **NULL** liegt keine `CAsyncSocket` Objekt angefügt, um `hSocket`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine **SOCKET** zu behandeln, wenn eine `CAsyncSocket` Objekt nicht an das Handle angefügt ist, die Memberfunktion gibt **NULL**.  
  
##  <a name="getlasterror"></a>CAsyncSocket::GetLastError  
 Rufen Sie diese Memberfunktion um den Fehlerstatus für den letzten Vorgang zu erhalten, die nicht an.  
  
```  
static int PASCAL GetLastError();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert gibt an, der Fehlercode für die letzten Windows Sockets-API-Routine, die von diesem Thread ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine bestimmten Member-Funktion gibt an, dass ein Fehler aufgetreten ist, `GetLastError` aufgerufen werden, um den entsprechenden Fehlercode abzurufen. Finden Sie Beschreibungen der einzelne Member-Funktion eine Liste der entsprechenden Fehlercodes.  
  
 Weitere Informationen zu den Fehlercodes finden Sie unter [Windows Sockets-2-API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
##  <a name="getpeername"></a>CAsyncSocket::GetPeerName  
 Rufen Sie diese Memberfunktion erhalten die Adresse des Sockets Peer, mit dem dieser Socket verbunden ist.  
  
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
 Ein Verweis auf eine **"uint"** , speichert einen Port.  
  
 `lpSockAddr`  
 Ein Zeiger auf die [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die den Namen des Peer-Socket empfängt.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Adresse in `lpSockAddr` in Bytes. Bei der Rückgabe der `lpSockAddrLen` -Argument enthält die tatsächliche Größe der `lpSockAddr` in Bytes zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **"WSAEINPROGRESS" zurück** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::GetPeerNameEx](#getpeernameex).  
  
##  <a name="getpeernameex"></a>CAsyncSocket::GetPeerNameEx  
 Rufen Sie diese Memberfunktion erhalten, die Adresse des Sockets Peer, der diesem Socket verbunden ist (Handles IPv6-Adressen) ist.  
  
```  
BOOL GetPeerNameEx(
    CString& rPeerAddress,  
    UINT& rPeerPort);
```  
  
### <a name="parameters"></a>Parameter  
 `rPeerAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rPeerPort`  
 Ein Verweis auf eine **"uint"** , speichert einen Port.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **"WSAEINPROGRESS" zurück** ein blockierender Aufruf der Windows-Sockets ist in Bearbeitung.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist identisch mit [CAsyncSocket::GetPeerName](#getpeername) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen auch als ältere Protokolle.  
  
##  <a name="getsockname"></a>CAsyncSocket::GetSockName  
 Rufen Sie diese Memberfunktion um den lokalen Namen eines Sockets zu erhalten.  
  
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
 Ein Verweis auf eine **"uint"** , speichert einen Port.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die die Adresse des Sockets empfängt.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Adresse in `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde, eine Adresse mit **binden**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf ist besonders nützlich, wenn eine **verbinden** aufgerufen wurde ohne dabei eine **binden** zuerst dieses Aufrufs stellt die einzige Möglichkeit, die durch den lokale Zuordnung, die festgelegt wurde, indem bestimmt werden kann die System.  
  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::GetSockNameEx](#getsocknameex)  
  
##  <a name="getsocknameex"></a>CAsyncSocket::GetSockNameEx  
 Rufen Sie diese Memberfunktion um den lokalen Namen eines Sockets (Handles IPv6-Adressen) zu erhalten.  
  
```  
BOOL GetSockNameEx(
    CString& rSocketAddress,  
    UINT& rSocketPort);
```  
  
### <a name="parameters"></a>Parameter  
 `rSocketAddress`  
 Ein Verweis auf ein `CString` Objekt, das eine Zahl IP-Adresse empfängt.  
  
 `rSocketPort`  
 Ein Verweis auf eine **"uint"** , speichert einen Port.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist nicht groß genug.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde, eine Adresse mit **binden**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf ist identisch mit [CAsyncSocket::GetSockName](#getsockname) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen auch als ältere Protokolle.  
  
 Dieser Aufruf ist besonders nützlich, wenn eine **verbinden** aufgerufen wurde ohne dabei eine **binden** zuerst dieses Aufrufs stellt die einzige Möglichkeit, die durch den lokale Zuordnung, die festgelegt wurde, indem bestimmt werden kann die System.  
  
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
 Die Socketoption für die ist der Wert abgerufen werden sollen.  
  
 `lpOptionValue`  
 Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option ist, zurückgegeben werden. Die ausgewählte Option zugeordnete Wert wird im Puffer zurückgegeben `lpOptionValue`. Die Ganzzahl verweist `lpOptionLen` sollte die Größe dieses Puffers in Byte; ursprünglich enthalten und bei der Rückgabe wird es auf die Größe des zurückgegebenen Werts festgelegt werden. Für **SO_LINGER**, dies ist die Größe des wird eine `LINGER` Struktur; für alle anderen Optionen werden die Größe des eine **BOOL** oder ein `int`, je nachdem, welche Option. Finden Sie in der Liste der Optionen und deren Größen im Abschnitt "Hinweise".  
  
 `lpOptionLen`  
 Ein Zeiger auf die Größe der `lpOptionValue` Puffers in Bytes.  
  
 `nLevel`  
 Die Ebene, auf der die Option definiert ist; Die einzigen unterstützte Stufen sind **SOL_SOCKET** und **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Wenn eine Option nie mit festgelegter `SetSockOpt`, klicken Sie dann `GetSockOpt` gibt den Standardwert für die Option zurück. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpOptionLen` Argument war ungültig.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAENOPROTOOPT** die Option ist unbekannt oder wird nicht unterstützt. Insbesondere **SO_BROADCAST** wird nicht unterstützt für Sockets vom Typ **SOCK_STREAM**, während **SO_ACCEPTCONN**, **SO_DONTLINGER**,  **SO_KEEPALIVE**, **SO_LINGER**, und **SO_OOBINLINE** werden nicht unterstützt für Sockets vom Typ **SOCK_DGRAM**.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 `GetSockOpt`Ruft den aktuellen Wert für eine Socketoption zugeordneten ein Socket eines beliebigen Typs, in einem beliebigen Zustand, und speichert das Ergebnis in `lpOptionValue`. Die Optionen beeinflussen Socketvorgänge, z. B. das routing der Pakete, die Out-of-Band-Datenübertragung und So weiter.  
  
 Die folgenden Optionen sind für unterstützt `GetSockOpt`. Den Typ identifiziert den Typ der Daten, die vom adressiert `lpOptionValue`. Die **TCP_NODELAY** Option verwendet Ebene **IPPROTO_TCP**; alle anderen Optionen verwenden Ebene **SOL_SOCKET**.  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Socket überwacht.|  
|**SO_BROADCAST**|**BOOL**|Socket ist für die Übertragung von Broadcastmeldungen konfiguriert.|  
|**SO_DEBUG**|**BOOL**|Debuggen ist aktiviert.|  
|**SO_DONTLINGER**|**BOOL**|Bei "true", die **SO_LINGER** Option ist deaktiviert.|  
|**SO_DONTROUTE**|**BOOL**|Routing ist deaktiviert.|  
|**SO_ERROR**|`int`|Rufen Sie der Fehlerstatus ab, und deaktivieren.|  
|**SO_KEEPALIVE**|**BOOL**|Keep-Alives werden gesendet.|  
|**SO_LINGER**|**LINGER-Struktur**|Die aktuelle Linger-Optionen zurückgegeben.|  
|**SO_OOBINLINE**|**BOOL**|Out-of-Band-Daten werden im normalen Datenstream empfangen wird.|  
|**SO_RCVBUF**|`int`|Die Größe des Puffers für empfängt.|  
|**SO_REUSEADDR**|**BOOL**|Der Socket kann an eine Adresse gebunden werden, der bereits verwendet wird.|  
|**SO_SNDBUF**|`int`|Die Größe des Puffers für sendet.|  
|**SO_TYPE**|`int`|Der Typ des Sockets (z. B. **SOCK_STREAM**).|  
|**TCP_NODELAY**|**BOOL**|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|  
  
 Nicht unterstützten Optionen der Berkeley Software Distribution (BSD) `GetSockOpt` sind:  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_RCVLOWAT**|`int`|Untere Grenze zu empfangen.|  
|**SO_RCVTIMEO**|`int`|Empfangstimeout.|  
|**SO_SNDLOWAT**|`int`|Senden Sie die untere Grenze.|  
|**SO_SNDTIMEO**|`int`|Timeout des Sendevorgangs.|  
|**IP_OPTIONS**||Abrufen von Optionen im IP-Header.|  
|**TCP_MAXSEG**|`int`|Abgerufen Sie maximale Segmentgröße TCP werden.|  
  
 Aufrufen von `GetSockOpt` mit einer nicht unterstützten Option führt zu einem Fehlercode von **WSAENOPROTOOPT** zurückgegeben werden aus der `GetLastError`.  
  
##  <a name="ioctl"></a>CAsyncSocket::IOCtl  
 Rufen Sie diese Memberfunktion um den Modus eines Sockets zu steuern.  
  
```  
BOOL IOCtl(
    long lCommand,  
    DWORD* lpArgument);
```  
  
### <a name="parameters"></a>Parameter  
 `lCommand`  
 Der Befehl zum Ausführen auf den Socket.  
  
 `lpArgument`  
 Ein Zeiger auf einen Parameter für `lCommand`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEINVAL** `lCommand` ist kein gültiger Befehl, oder `lpArgument` ist kein akzeptabler Parameter für `lCommand`, oder der Befehl gilt nicht für den Typ des Sockets angegeben.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 Diese Routine kann auf jeder Ebene in einem beliebigen Zustand verwendet werden. Es dient zum Abrufen oder Abrufen von Betriebsparameter den Socket, unabhängig von der das Protokoll und die Kommunikation Subsystem zugeordnet. Die folgenden Befehle werden unterstützt:  
  
- **FIONBIO** aktivieren oder deaktivieren Sie nicht blockierenden Modus auf den Socket. Die `lpArgument` Parameter verweist auf eine `DWORD`ist ungleich NULL, wenn nicht blockierenden Modus aktiviert werden, und NULL, wenn es deaktiviert ist. Wenn `AsyncSelect` ausgegeben wurde für ein Socket wird jeder Versuch, verwenden Sie **IOCtl** für den Socket wieder Blockierungsmodus festzulegen, schlagen mit **WSAEINVAL**. Setzen Sie den Socket auf Blockierungsmodus zurück und zu verhindern, dass die **WSAEINVAL** Fehler, eine Anwendung muss zuerst deaktivieren `AsyncSelect` durch Aufrufen `AsyncSelect` mit der `lEvent` Parameter gleich 0 ist, rufen Sie anschließend **IOCtl** .  
  
- **FIONREAD** bestimmt die maximale Anzahl von Bytes, die mit einem gelesen werden können **Receive** aus diesem Socket aufrufen. Die `lpArgument` Parameter verweist auf eine `DWORD` in der **IOCtl** speichert das Ergebnis. Wenn diesem Socket vom Typ **SOCK_STREAM**, **FIONREAD** gibt die Gesamtmenge der Daten, die gelesen werden können, in einer einzelnen **Receive**; Dies ist normalerweise identisch mit der Gesamtmenge des Daten in der Warteschlange für den Socket. Wenn diesem Socket vom Typ **SOCK_DGRAM**, **FIONREAD** gibt die Größe des ersten Datagramms in der Warteschlange auf den Socket.  
  
- **SIOCATMARK** zu bestimmen, ob alle Out-of-Band-Daten gelesen wurden. Dies gilt nur für ein Socket vom Typ **SOCK_STREAM** die für den Inline-Empfang von Out-of-Band-Daten konfiguriert wurde ( **SO_OOBINLINE**). Wenn keine Out-of-Band-Daten gelesen werden wartet, gibt der Vorgang ungleich NULL zurück. Andernfalls wird 0 und das nächste zurückgegeben **Receive** oder `ReceiveFrom` ausgeführt wird, auf der Socket wird abgerufen, einige oder alle Daten vor der "Markierung" werden die Anwendung die zu verwendende der **SIOCATMARK** Vorgang Bestimmen Sie, ob irgendwelche Daten verbleiben. Wenn die "dringenden" (Out-of-Band) Daten vor normalen Daten vorhanden sind, wird er in der Reihenfolge empfangen werden. (Beachten Sie, dass eine **Receive** oder `ReceiveFrom` Out-of-Band- und "normale" Daten im selben Aufruf wird niemals mischen.) Die `lpArgument` Parameter verweist auf eine `DWORD` in der **IOCtl** speichert das Ergebnis.  
  
 Diese Funktion ist eine Teilmenge der **ioctl()** in Berkeley-Sockets verwendet. Insbesondere, es gibt keinen Befehl entspricht **FIOASYNC**, während **SIOCATMARK** ist nur Socketebene-Befehl das unterstützt wird.  
  
##  <a name="listen"></a>CAsyncSocket:: Listen  
 Rufen Sie diese Memberfunktion zum Abhören von eingehenden verbindungsanforderungen.  
  
```  
BOOL Listen(int nConnectionBacklog = 5);
```  
  
### <a name="parameters"></a>Parameter  
 *nConnectionBacklog*  
 Die maximale Länge, die auf die die Warteschlange für ausstehende Verbindungen anwachsen kann. Gültige Bereich liegt zwischen 1 und 5.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEADDRINUSE** wurde versucht, das Lauschen an eine Adresse verwendet.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden** oder ist bereits verbunden.  
  
- **WSAEISCONN** der Socket ist bereits verbunden.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP** referenzierte Socket ist nicht vom ein Typ, unterstützt die `Listen` Vorgang.  
  
### <a name="remarks"></a>Hinweise  
 Um Verbindungen zu akzeptieren, wird der Socket zuerst mit erstellt **erstellen**, ein Backlog für eingehende Verbindungen mit angegeben wird `Listen`, und klicken Sie dann die Verbindungen akzeptiert werden **Accept**. `Listen`gilt nur für Sockets, die Verbindungen, d. h. unterstützen die eines Typs **SOCK_STREAM**. Diesem Socket ist, wobei eingehende Verbindungen bestätigt und in der Warteschlange ausstehender Annahme durch den Prozess "passive" Modus versetzen.  
  
 Diese Funktion wird meist von Servern (oder jede Anwendung, die Verbindungen akzeptieren möchte) verwendet, die möglicherweise mehr als eine verbindungsanforderung zu einem Zeitpunkt: Wenn eine verbindungsanforderung mit der vollständigen Warteschlange eingeht, der Client wird eine Fehlermeldung mit Angabe der  **STARK**.  
  
 `Listen`versucht, die weiterhin Rational funktionsfähig, wenn es keine verfügbaren Ports (Deskriptoren sind). Es werden Verbindungen akzeptieren, bis die Warteschlange geleert wird. Wenn Ports verfügbar eines späteren Aufrufs von `Listen` oder **Accept** möglichst Auffüllen von der Warteschlange des aktuellen oder letzten "Backlog,", und für eingehende Verbindungen Überwachung fort.  
  
##  <a name="m_hsocket"></a>CAsyncSocket::m_hSocket  
 Enthält die **SOCKET** -handle für den Socket gekapselt, die von diesem `CAsyncSocket` Objekt.  
  
```  
SOCKET m_hSocket;  
```  
  
##  <a name="onaccept"></a>CAsyncSocket::OnAccept  
 Wird aufgerufen, durch das Framework auf einem Abhörsocket zu informieren, die er ausstehenden verbindungsanforderungen, durch Aufrufen annehmen kann der [Accept](#accept) Memberfunktion.  
  
```  
virtual void OnAccept(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Das neueste Fehlerprotokoll für ein Socket. Die folgenden Fehlercodes gilt für die `OnAccept` Memberfunktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onclose"></a>CAsyncSocket::OnClose  
 Wird aufgerufen, durch das Framework um diesem Socket zu benachrichtigen, dass die verbundene Socket von einem Prozess geschlossen wird.  
  
```  
virtual void OnClose(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Das neueste Fehlerprotokoll für ein Socket. Die folgenden Fehlercodes gelten für die `OnClose` Memberfunktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAECONNRESET** die Verbindung wurde von der Remoteseite zurückgesetzt.  
  
- **WSAECONNABORTED** die Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onconnect"></a>CAsyncSocket::OnConnect  
 Vom Framework aufgerufen wird, diese Verbindung Socket mitzuteilen, dass der Verbindungsversuch, ob erfolgreich oder Fehler abgeschlossen ist.  
  
```  
virtual void OnConnect(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Das neueste Fehlerprotokoll für ein Socket. Die folgenden Fehlercodes gelten für die `OnConnect` Memberfunktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAEADDRINUSE** die angegebene Adresse wird bereits verwendet.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.  
  
- **STARK** Verbindungsversuch abgelehnten erzwungen.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument ist falsch.  
  
- **WSAEINVAL** der Socket ist bereits an eine Adresse gebunden.  
  
- **WSAEISCONN** der Socket ist bereits verbunden.  
  
- **WSAEMFILE** keine weiteren Dateideskriptoren verfügbar sind.  
  
- **WSAENETUNREACH** im Netzwerk kann nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
- `WSAENOBUFS`Es ist kein Pufferplatz verfügbar. Der Socket kann nicht verbunden werden.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist.  
  
- **WSAENOTSOCK** Deskriptors ist eine Datei, die nicht von einem Socket.  
  
- **WSAETIMEDOUT** Verbindungsversuch Timeout, ohne eine Verbindung herzustellen.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  In [CSocket](../../mfc/reference/csocket-class.md)die `OnConnect` Benachrichtigungsfunktion wird nie aufgerufen. Für Verbindungen, rufen Sie einfach **verbinden**, die dann zurück, wenn die Verbindung (erfolgreich oder fehlerhaft) abgeschlossen ist. Behandlung von Verbindung Benachrichtigungen ist ein Implementierungsdetail MFC.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAsyncSocket#1](../../mfc/reference/codesnippet/cpp/casyncsocket-class_1.cpp)]  
  
##  <a name="onoutofbanddata"></a>CAsyncSocket::OnOutOfBandData  
 Wird aufgerufen, durch das Framework auf den empfangenden Socket zu informieren, den der sendende Socket Out-of-Band-Daten, die gesendet wurde.  
  
```  
virtual void OnOutOfBandData(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Das neueste Fehlerprotokoll für ein Socket. Die folgenden Fehlercodes gelten für die `OnOutOfBandData` Memberfunktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Out-of-Band-Daten ist ein logisch unabhängig Kanal, der für jedes Paar von verbundenen Sockets vom Typ zugeordnet ist **SOCK_STREAM**. Der Kanal wird normalerweise verwendet, um dringende Daten zu senden.  
  
 MFC unterstützt die Out-of-Band-Daten, aber der Benutzer der Klasse `CAsyncSocket` werden aus ihrer Verwendung abgeraten. Einfacher besteht darin, einen zweiten Socket für die Übergabe von Daten zu erstellen. Weitere Informationen über Out-of-Band-Daten finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
##  <a name="onreceive"></a>CAsyncSocket::OnReceive  
 Wird aufgerufen, durch das Framework um diesem Socket zu benachrichtigen, dass Daten in den Puffer, die durch den Aufruf abgerufen werden kann die **Receive** Memberfunktion.  
  
```  
virtual void OnReceive(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Das neueste Fehlerprotokoll für ein Socket. Die folgenden Fehlercodes gelten für die `OnReceive` Memberfunktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAsyncSocket#2](../../mfc/reference/codesnippet/cpp/casyncsocket-class_2.cpp)]  
  
##  <a name="onsend"></a>CAsyncSocket::OnSend  
 Wird aufgerufen, durch das Framework dem Socket zu benachrichtigen, dass sie Daten durch den Aufruf jetzt senden kann die **senden** Memberfunktion.  
  
```  
virtual void OnSend(int nErrorCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nErrorCode`  
 Das neueste Fehlerprotokoll für ein Socket. Die folgenden Fehlercodes gelten für die `OnSend` Memberfunktion:  
  
- **0** die Funktion erfolgreich ausgeführt wurde.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Socketbenachrichtigungen](../../mfc/windows-sockets-socket-notifications.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAsyncSocket#3](../../mfc/reference/codesnippet/cpp/casyncsocket-class_3.cpp)]  
  
##  <a name="operator_eq"></a>CAsyncSocket::operator =  
 Weist einen neuen Wert zu einem `CAsyncSocket` Objekt.  
  
```  
void operator=(const CAsyncSocket& rSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `rSrc`  
 Ein Verweis auf ein vorhandenes `CAsyncSocket` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen vorhandenen kopieren `CAsyncSocket` Objekt zu einem anderen `CAsyncSocket` Objekt.  
  
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
 Rufen Sie diese Memberfunktion zum Empfangen von Daten aus einem Socket.  
  
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
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion durch die Socketoptionen festgelegt werden und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_PEEK** die eingehenden Daten einsehen. Die Daten in den Puffer kopiert werden jedoch nicht aus der Eingabewarteschlange entfernt.  
  
- **MSG_OOB** Out-of-Band-Daten zu verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, **Receive** gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch den Aufruf [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket heruntergefahren; es ist nicht möglich, rufen Sie **Receive** für ein Socket nach `ShutDown` wurde aufgerufen, mit `nHow` auf 0 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und die **Receive** Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist für verbundene Stream oder Datagrammsockets verwendet und wird verwendet, um eingehende Daten gelesen.  
  
 Für Sockets vom Typ **SOCK_STREAM**, wie viele Informationen als aktuell verfügbaren bis zur Größe des Puffers angegeben ist, zurückgegeben wird. Wenn der Socket für Inline-Empfang der Out-of-Band-Daten konfiguriert wurde (Socketoption **SO_OOBINLINE**) und Out-of-Band-Daten als ungelesen ist, werden nur Out-of-Band-Daten zurückgegeben. Die Anwendung können die **IOCtlSIOCATMARK** Option oder [OnOutOfBandData](#onoutofbanddata) zu bestimmen, ob irgendwelche mehr Out-of-Band-Daten verbleiben gelesen werden.  
  
 Für Datagrammsockets werden Daten aus der erste Datagramm bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der bereitgestellte Puffer ist, der Puffer voll ist, mit dem ersten Teil des Datagramms, überschüssigen Daten in die geht verloren, und **Receive** gibt einen Wert von **SOCKET_ERROR** mit dem Fehlercode festgelegt **WSAEMSGSIZE**. Wenn keine eingehenden Daten verfügbar, auf den Socket, einen Wert von sind **SOCKET_ERROR** wird zurückgegeben, mit dem Fehlercode **WSAEWOULDBLOCK**. Die [OnReceive](#onreceive) Callback-Funktion kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.  
  
 Wenn der Typ der Socket ist **SOCK_STREAM** und die Remoteseite hat die Verbindung ordnungsgemäß heruntergefahren, eine **Receive** sofort abgeschlossen wird, mit 0 empfangenen Bytes. Wenn die Verbindung zurückgesetzt wurde, eine **Receive** schlägt fehl mit Fehler **WSAECONNRESET**.  
  
 **Empfangen von** sollte nur einmal für jedes Mal aufgerufen werden [CAsyncSocket::OnReceive](#onreceive) aufgerufen wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CAsyncSocket::OnReceive](#onreceive).  
  
##  <a name="receivefrom"></a>CAsyncSocket::ReceiveFrom  
 Rufen Sie diese Memberfunktion zum Empfangen eines Datagramms und speichern die Quelladresse in die [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur oder im `rSocketAddress`.  
  
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
 Ein Verweis auf eine **"uint"** , speichert einen Port.  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) -Struktur, die die Quelladresse bei der Rückgabe enthält.  
  
 `lpSockAddrLen`  
 Ein Zeiger auf die Länge der Quelladresse in `lpSockAddr` in Bytes.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion durch die Socketoptionen festgelegt werden und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_PEEK** die eingehenden Daten einsehen. Die Daten in den Puffer kopiert werden jedoch nicht aus der Eingabewarteschlange entfernt.  
  
- **MSG_OOB** Out-of-Band-Daten zu verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `ReceiveFrom` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch den Aufruf `GetLastError`. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument war ungültig: die `lpSockAddr` Formatnamenpuffer war zu klein, um die Peer-Adresse zu berücksichtigen.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket heruntergefahren; es ist nicht möglich, rufen Sie `ReceiveFrom` für ein Socket nach `ShutDown` wurde aufgerufen, mit `nHow` auf 0 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und die `ReceiveFrom` Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um eingehende Daten auf einen (möglicherweise verbundenen) Socket lesen und erfassen die Adresse, von der die Daten gesendet wurde.  
  
 Verwenden Sie zum Behandeln von IPv6-Adressen [CAsyncSocket::ReceiveFromEx](#receivefromex).  
  
 Für Sockets vom Typ **SOCK_STREAM**, wie viele Informationen als aktuell verfügbaren bis zur Größe des Puffers angegeben ist, zurückgegeben wird. Wenn der Socket für Inline-Empfang der Out-of-Band-Daten konfiguriert wurde (Socketoption **SO_OOBINLINE**) und Out-of-Band-Daten als ungelesen ist, werden nur Out-of-Band-Daten zurückgegeben. Die Anwendung können die **IOCtlSIOCATMARK** Option oder `OnOutOfBandData` zu bestimmen, ob irgendwelche mehr Out-of-Band-Daten verbleiben gelesen werden. Die `lpSockAddr` und `lpSockAddrLen` Parameter werden ignoriert, für **SOCK_STREAM** Sockets.  
  
 Für Datagrammsockets werden Daten aus der erste Datagramm bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der bereitgestellte Puffer ist, der Puffer voll ist, mit dem ersten Teil der Nachricht, die überzähligen Daten geht verloren, und `ReceiveFrom` gibt einen Wert von **SOCKET_ERROR** mit dem Fehlercode festgelegt  **WSAEMSGSIZE**.  
  
 Wenn `lpSockAddr` ungleich NULL ist und der Socket ist vom Typ **SOCK_DGRAM**, die Netzwerkadresse des Sockets, die die Daten gesendet wird kopiert, auf den entsprechenden [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur. Der Wert verweist `lpSockAddrLen` auf die Größe dieser Struktur initialisiert wird und bei der Rückgabe an, dass die tatsächliche Größe der Adresse, die dort gespeicherten geändert wird. Wenn keine eingehenden Daten verfügbar, auf den Socket sind der `ReceiveFrom` Aufruf wartet auf Daten auf das eingehen, es sei denn, der Socket ist nicht blockierend. In diesem Fall wird ein Wert von **SOCKET_ERROR** wird zurückgegeben, mit dem Fehlercode **WSAEWOULDBLOCK**. Die `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.  
  
 Wenn der Typ der Socket ist **SOCK_STREAM** und die Remoteseite hat die Verbindung ordnungsgemäß heruntergefahren, eine `ReceiveFrom` sofort abgeschlossen wird, mit 0 empfangenen Bytes.  
  
##  <a name="receivefromex"></a>CAsyncSocket::ReceiveFromEx  
 Rufen Sie diese Memberfunktion zum Empfangen eines Datagramms und speichern die Quelladresse in die [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur oder im `rSocketAddress` (handles IPv6-Adressen).  
  
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
 Ein Verweis auf eine **"uint"** , speichert einen Port.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion durch die Socketoptionen festgelegt werden und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_PEEK** die eingehenden Daten einsehen. Die Daten in den Puffer kopiert werden jedoch nicht aus der Eingabewarteschlange entfernt.  
  
- **MSG_OOB** Out-of-Band-Daten zu verarbeiten.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `ReceiveFromEx` gibt die Anzahl der empfangenen Bytes. Wenn die Verbindung geschlossen wurde, wird 0 zurückgegeben. Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch den Aufruf `GetLastError`. Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** der `lpSockAddrLen` Argument war ungültig: die `lpSockAddr` Formatnamenpuffer war zu klein, um die Peer-Adresse zu berücksichtigen.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket heruntergefahren; es ist nicht möglich, rufen Sie `ReceiveFromEx` für ein Socket nach `ShutDown` wurde aufgerufen, mit `nHow` auf 0 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und die `ReceiveFromEx` Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** Datagramm war zu groß für den angegebenen Puffer und wurde abgeschnitten.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um eingehende Daten auf einen (möglicherweise verbundenen) Socket lesen und erfassen die Adresse, von der die Daten gesendet wurde.  
  
 Diese Funktion ist identisch mit [CAsyncSocket::ReceiveFrom](#receivefrom) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen auch als ältere Protokolle.  
  
 Für Sockets vom Typ **SOCK_STREAM**, wie viele Informationen als aktuell verfügbaren bis zur Größe des Puffers angegeben ist, zurückgegeben wird. Wenn der Socket für Inline-Empfang der Out-of-Band-Daten konfiguriert wurde (Socketoption **SO_OOBINLINE**) und Out-of-Band-Daten als ungelesen ist, werden nur Out-of-Band-Daten zurückgegeben. Die Anwendung können die **IOCtlSIOCATMARK** Option oder `OnOutOfBandData` zu bestimmen, ob irgendwelche mehr Out-of-Band-Daten verbleiben gelesen werden. Die `lpSockAddr` und `lpSockAddrLen` Parameter werden ignoriert, für **SOCK_STREAM** Sockets.  
  
 Für Datagrammsockets werden Daten aus der erste Datagramm bis zur Größe des Puffers angegeben extrahiert. Wenn das Datagramm größer als der bereitgestellte Puffer ist, der Puffer voll ist, mit dem ersten Teil der Nachricht, die überzähligen Daten geht verloren, und `ReceiveFromEx` gibt einen Wert von **SOCKET_ERROR** mit dem Fehlercode festgelegt  **WSAEMSGSIZE**.  
  
 Wenn `lpSockAddr` ungleich NULL ist und der Socket ist vom Typ **SOCK_DGRAM**, die Netzwerkadresse des Sockets, die die Daten gesendet wird kopiert, auf den entsprechenden [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur. Der Wert verweist `lpSockAddrLen` auf die Größe dieser Struktur initialisiert wird und bei der Rückgabe an, dass die tatsächliche Größe der Adresse, die dort gespeicherten geändert wird. Wenn keine eingehenden Daten verfügbar, auf den Socket sind der `ReceiveFromEx` Aufruf wartet auf Daten auf das eingehen, es sei denn, der Socket ist nicht blockierend. In diesem Fall wird ein Wert von **SOCKET_ERROR** wird zurückgegeben, mit dem Fehlercode **WSAEWOULDBLOCK**. Die `OnReceive` Rückruf kann verwendet werden, um zu bestimmen, wenn weitere Daten empfangen werden.  
  
 Wenn der Typ der Socket ist **SOCK_STREAM** und die Remoteseite hat die Verbindung ordnungsgemäß heruntergefahren, eine `ReceiveFromEx` sofort abgeschlossen wird, mit 0 empfangenen Bytes.  
  
##  <a name="send"></a>CAsyncSocket::Send  
 Rufen Sie diese Memberfunktion zum Senden von Daten für einen verbundenen Socket.  
  
```  
virtual int Send(
    const void* lpBuf,  
    int nBufLen,  
    int nFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Ein Puffer mit den zu sendenden Daten.  
  
 `nBufLen`  
 Die Länge der Daten in `lpBuf` in Bytes.  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion durch die Socketoptionen festgelegt werden und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_DONTROUTE** gibt an, die die Daten nicht unterliegen routing sein sollen. Ein Windows-Sockets Lieferant können ignorieren dieses Flag.  
  
- **MSG_OOB** Out-of-Band-Daten senden ( **SOCK_STREAM** nur).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, **senden** gibt die Gesamtzahl der Zeichen gesendet. (Beachten Sie, dass dies kann kleiner als die Anzahl erkennbar sein `nBufLen`.) Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch den Aufruf [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEACCES** die angeforderte Adresse ist eine Broadcastadresse, aber das entsprechende Flag nicht festgelegt wurde.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEFAULT** der `lpBuf` Argument ist nicht in einem gültigen Teil des benutzeradressraums.  
  
- **WSAENETRESET** die Verbindung muss zurückgesetzt werden, da der Windows Sockets-Implementierung, die sie gelöscht.  
  
- `WSAENOBUFS`Windows Sockets-Implementierung eine Puffer-Deadlocks gemeldet.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket heruntergefahren; es ist nicht möglich, rufen Sie **senden** für ein Socket nach `ShutDown` wurde aufgerufen, mit `nHow` auf 1 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und der angeforderte Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** der Socket ist vom Typ **SOCK_DGRAM**, und das Datagramm ist größer als die maximal von der Windows Sockets-Implementierung unterstützt.  
  
- **WSAEINVAL** der Socket nicht gebunden wurde mit **binden**.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
### <a name="remarks"></a>Hinweise  
 **Senden von** zum Schreiben der ausgehender Daten auf verbundenen-Stream oder das Datagramm-Sockets verwendet wird. Für Datagrammsockets, muss darauf geachtet werden, nicht zu überschreiten, die maximale Größe der IP-Paket der zugrunde liegenden Subnetze, das durch vorgegeben der **iMaxUdpDg** Element in der [WSADATA](../../mfc/reference/wsadata-structure.md) zurückgegebene Struktur `AfxSocketInit`. Wenn die Daten für die zugrunde liegenden Protokoll, den Fehler atomar durchlaufen zu lang ist **WSAEMSGSIZE** wird zurückgegeben, über `GetLastError`, und keine Daten übertragen.  
  
 Beachten Sie, die für ein Datagramm vom erfolgreichen Abschluss der socket eine **senden** nicht, dass die Daten erfolgreich übermittelt wurde.  
  
 Auf `CAsyncSocket` Objekte des Typs **SOCK_STREAM**, die Anzahl der geschriebenen Bytes kann zwischen 1 und die angeforderte Länge, abhängig von der Puffer-Konfiguration auf den lokalen und fremden Hosts sein.  
  
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
 Ein Puffer mit den zu sendenden Daten.  
  
 `nBufLen`  
 Die Länge der Daten in `lpBuf` in Bytes.  
  
 `nHostPort`  
 Der Port, die Socket-Anwendung identifizieren.  
  
 `lpszHostAddress`  
 Die Netzwerkadresse des Sockets mit dem dieses Objekt verbunden ist: einen Computernamen ein, z. B. "ftp.microsoft.com" oder einer gepunkteten Zahl wie "128.56.22.8".  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion durch die Socketoptionen festgelegt werden und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_DONTROUTE** gibt an, die die Daten nicht unterliegen routing sein sollen. Ein Windows-Sockets Lieferant können ignorieren dieses Flag.  
  
- **MSG_OOB** Out-of-Band-Daten senden ( **SOCK_STREAM** nur).  
  
 `lpSockAddr`  
 Ein Zeiger auf eine [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur, die die Adresse des Sockets Ziel enthält.  
  
 `nSockAddrLen`  
 Die Länge der Adresse in `lpSockAddr` in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `SendTo` gibt die Gesamtzahl der Zeichen gesendet. (Beachten Sie, dass dies kann kleiner als die Anzahl erkennbar sein `nBufLen`.) Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch den Aufruf [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEACCES** die angeforderte Adresse ist eine Broadcastadresse, aber das entsprechende Flag nicht festgelegt wurde.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEFAULT** der `lpBuf` oder `lpSockAddr` Parameter sind nicht Teil des benutzeradressraums oder `lpSockAddr` Argument ist zu klein (kleiner als die Größe von einer [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **WSAEINVAL** der Hostname ist ungültig.  
  
- **WSAENETRESET** die Verbindung muss zurückgesetzt werden, da der Windows Sockets-Implementierung, die sie gelöscht.  
  
- `WSAENOBUFS`Windows Sockets-Implementierung eine Puffer-Deadlocks gemeldet.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket heruntergefahren; es ist nicht möglich, rufen Sie `SendTo` für ein Socket nach `ShutDown` wurde aufgerufen, mit `nHow` auf 1 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und der angeforderte Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** der Socket ist vom Typ **SOCK_DGRAM**, und das Datagramm ist größer als die maximal von der Windows Sockets-Implementierung unterstützt.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAENETUNREACH** im Netzwerk kann nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
### <a name="remarks"></a>Hinweise  
 `SendTo`auf Datagramm oder den Stream-Sockets verwendet wird, und zum Schreiben der ausgehender Daten auf einem Socket verwendet wird. Für Datagrammsockets, muss darauf geachtet werden, nicht zu überschreiten, die maximale Größe der IP-Paket der zugrunde liegenden Subnetze, das durch vorgegeben der **iMaxUdpDg** Element in der [WSADATA](../../mfc/reference/wsadata-structure.md) Struktur ausgefüllt [ AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Wenn die Daten für die zugrunde liegenden Protokoll, den Fehler atomar durchlaufen zu lang ist **WSAEMSGSIZE** zurückgegeben wird, und keine Daten übertragen.  
  
 Beachten Sie, dass beim erfolgreichen Abschluss einer `SendTo` nicht, dass die Daten erfolgreich übermittelt wurde.  
  
 `SendTo`wird nur verwendet werden, auf eine **SOCK_DGRAM** Socket zum Senden von ein Datagramm an einen bestimmten Socket identifizierte der `lpSockAddr` Parameter.  
  
 Eine Übertragung senden (auf einer **SOCK_DGRAM** nur), die Adresse in der `lpSockAddr` Parameter sollten erstellt werden, die spezielle IP-Adresse **INADDR_BROADCAST** (definiert in der Windows Sockets-Header WINSOCK-Datei. H) zusammen mit der gewünschten Portnummer. Oder, wenn die `lpszHostAddress` Parameter ist **NULL**, für die Übertragung der Socket konfiguriert ist. Es ist im Allgemeinen empfiehlt für ein broadcast Datagramm die Ordnergröße überschritten, in denen Fragmentierung auftreten kann, was bedeutet, dass der Datenanteil das Datagramm (mit Ausnahme von Headern) 512 Bytes nicht überschreiten darf.  
  
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
 Ein Puffer mit den zu sendenden Daten.  
  
 `nBufLen`  
 Die Länge der Daten in `lpBuf` in Bytes.  
  
 `nHostPort`  
 Der Port, die Socket-Anwendung identifizieren.  
  
 `lpszHostAddress`  
 Die Netzwerkadresse des Sockets mit dem dieses Objekt verbunden ist: einen Computernamen ein, z. B. "ftp.microsoft.com" oder einer gepunkteten Zahl wie "128.56.22.8".  
  
 `nFlags`  
 Gibt an, wie in der der Aufruf ausgeführt wird. Die Semantik dieser Funktion durch die Socketoptionen festgelegt werden und die `nFlags` Parameter. Letzteres wird erstellt, durch die Kombination der folgenden Werte mit dem C++- `OR` Operator:  
  
- **MSG_DONTROUTE** gibt an, die die Daten nicht unterliegen routing sein sollen. Ein Windows-Sockets Lieferant können ignorieren dieses Flag.  
  
- **MSG_OOB** Out-of-Band-Daten senden ( **SOCK_STREAM** nur).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn kein Fehler auftritt, `SendToEx` gibt die Gesamtzahl der Zeichen gesendet. (Beachten Sie, dass dies kann kleiner als die Anzahl erkennbar sein `nBufLen`.) Andernfalls der Wert **SOCKET_ERROR** zurückgegeben wird, und ein bestimmten Fehlercode abgerufen werden kann, durch den Aufruf [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEACCES** die angeforderte Adresse ist eine Broadcastadresse, aber das entsprechende Flag nicht festgelegt wurde.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEFAULT** der `lpBuf` oder `lpSockAddr` Parameter sind nicht Teil des benutzeradressraums oder `lpSockAddr` Argument ist zu klein (kleiner als die Größe von einer [SOCKADDR](../../mfc/reference/sockaddr-structure.md) Struktur).  
  
- **WSAEINVAL** der Hostname ist ungültig.  
  
- **WSAENETRESET** die Verbindung muss zurückgesetzt werden, da der Windows Sockets-Implementierung, die sie gelöscht.  
  
- `WSAENOBUFS`Windows Sockets-Implementierung eine Puffer-Deadlocks gemeldet.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
- **WSAEOPNOTSUPP MSG_OOB** wurde angegeben, aber der Socket ist nicht vom Typ **SOCK_STREAM**.  
  
- **WSAESHUTDOWN** der Socket heruntergefahren; es ist nicht möglich, rufen Sie `SendToEx` für ein Socket nach `ShutDown` wurde aufgerufen, mit `nHow` auf 1 oder 2 festgelegt.  
  
- **WSAEWOULDBLOCK** der Socket gekennzeichnet ist als nicht blockierend und der angeforderte Vorgang würde blockieren.  
  
- **WSAEMSGSIZE** der Socket ist vom Typ **SOCK_DGRAM**, und das Datagramm ist größer als die maximal von der Windows Sockets-Implementierung unterstützt.  
  
- **WSAECONNABORTED** die virtuelle Verbindung wurde aufgrund eines Timeout- oder anderer Fehler abgebrochen.  
  
- **WSAECONNRESET** die virtuelle Verbindung wurde von der Remoteseite zurückgesetzt.  
  
- **WSAEADDRNOTAVAIL** die angegebene Adresse ist nicht auf dem lokalen Computer verfügbar.  
  
- **** Adressen in der angegebenen Adressfamilie können nicht mit diesem Socket verwendet werden.  
  
- **WSAEDESTADDRREQ** eine Zieladresse ist erforderlich.  
  
- **WSAENETUNREACH** im Netzwerk kann nicht zu diesem Zeitpunkt nicht von diesem Host erreicht werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist identisch mit [Einsatz](#sendto) mit dem Unterschied, dass sie behandelt, dass IPv6-Adressen auch als ältere Protokolle.  
  
 `SendToEx`auf Datagramm oder den Stream-Sockets verwendet wird, und zum Schreiben der ausgehender Daten auf einem Socket verwendet wird. Für Datagrammsockets, muss darauf geachtet werden, nicht zu überschreiten, die maximale Größe der IP-Paket der zugrunde liegenden Subnetze, das durch vorgegeben der **iMaxUdpDg** Element in der [WSADATA](../../mfc/reference/wsadata-structure.md) Struktur ausgefüllt [ AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit). Wenn die Daten für die zugrunde liegenden Protokoll, den Fehler atomar durchlaufen zu lang ist **WSAEMSGSIZE** zurückgegeben wird, und keine Daten übertragen.  
  
 Beachten Sie, dass beim erfolgreichen Abschluss einer `SendToEx` nicht, dass die Daten erfolgreich übermittelt wurde.  
  
 `SendToEx`wird nur verwendet werden, auf eine **SOCK_DGRAM** Socket zum Senden von ein Datagramm an einen bestimmten Socket identifizierte der `lpSockAddr` Parameter.  
  
 Eine Übertragung senden (auf einer **SOCK_DGRAM** nur), die Adresse in der `lpSockAddr` Parameter sollten erstellt werden, die spezielle IP-Adresse **INADDR_BROADCAST** (definiert in der Windows Sockets-Header WINSOCK-Datei. H) zusammen mit der gewünschten Portnummer. Oder, wenn die `lpszHostAddress` Parameter ist **NULL**, für die Übertragung der Socket konfiguriert ist. Es ist im Allgemeinen empfiehlt für ein broadcast Datagramm die Ordnergröße überschritten, in denen Fragmentierung auftreten kann, was bedeutet, dass der Datenanteil das Datagramm (mit Ausnahme von Headern) 512 Bytes nicht überschreiten darf.  
  
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
 Die Socketoption für die ist der Wert festgelegt werden.  
  
 `lpOptionValue`  
 Ein Zeiger auf den Puffer, in dem der Wert für die angeforderte Option bereitgestellt wird.  
  
 `nOptionLen`  
 Die Größe der `lpOptionValue` Puffers in Bytes.  
  
 `nLevel`  
 Die Ebene, auf der die Option definiert ist; Die einzigen unterstützte Stufen sind **SOL_SOCKET** und **IPPROTO_TCP**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEFAULT** `lpOptionValue` befindet sich nicht in einem gültigen Teil des Adressraums.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAEINVAL** `nLevel` ist ungültig, oder die Informationen in `lpOptionValue` ist ungültig.  
  
- **WSAENETRESET** Verbindung wurde abgebrochen, wenn **SO_KEEPALIVE** festgelegt ist.  
  
- **WSAENOPROTOOPT** die Option ist unbekannt oder wird nicht unterstützt. Insbesondere **SO_BROADCAST** wird nicht unterstützt für Sockets vom Typ **SOCK_STREAM**, während **SO_DONTLINGER**, **SO_KEEPALIVE**,  **SO_LINGER**, und **SO_OOBINLINE** werden nicht unterstützt für Sockets vom Typ **SOCK_DGRAM**.  
  
- **WSAENOTCONN** Verbindung wurde zurückgesetzt, wenn **SO_KEEPALIVE** festgelegt ist.  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 `SetSockOpt`Legt den aktuellen Wert für eine Socketoption ein Socket eines beliebigen Typs, in einem beliebigen Zustand zugeordnet. Obwohl Optionen auf mehreren Protokoll Ebenen vorhanden sein können, definiert dieser Spezifikation nur Optionen, die auf der obersten "Socket" Ebene vorhanden sind. Die Optionen beeinflussen die Socketvorgänge, z. B., ob beschleunigte Daten im normalen Datenstream empfangen werden, ob Broadcastmeldungen für den Socket gesendet werden können und so weiter.  
  
 Es gibt zwei Arten von Socketoptionen: Boolean die aktivieren oder Deaktivieren einer Funktion oder das Verhalten und die Optionen die ein Integer-Wert oder eine Struktur erfordern. So aktivieren Sie eine booleschen Option `lpOptionValue` verweist auf eine ganze Zahl ungleich NULL. So deaktivieren Sie die Option `lpOptionValue` verweist auf eine ganze Zahl ungleich 0 (null). `nOptionLen`sollte gleich sein **sizeof(BOOL)** für boolesche Optionen. Weitere Optionen `lpOptionValue` verweist auf die ganze Zahl oder eine Struktur, die den gewünschten Wert für die Option enthält und `nOptionLen` ist die Länge der ganze Zahl oder Struktur.  
  
 **SO_LINGER** Steuerelemente, die die Aktion ausgeführt wird, wenn nicht gesendete Daten werden in die Warteschlange für ein Socket und **schließen** Funktion wird aufgerufen, um den Socket schließen.  
  
 Standardmäßig kann ein Socket kann nicht gebunden werden (finden Sie unter [binden](#bind)) auf eine lokale Adresse der bereits verwendet wird. In manchen Fällen kann jedoch es wünschenswert sein, "eine Adresse auf diese Weise wiederverwenden" sein. Da jede Verbindung durch die Kombination von lokalen und remoten Adressen eindeutig identifiziert wird, besteht kein Problem mit mit zwei Sockets, die in die gleiche lokale Adresse gebunden werden, solange die Remoteadressen unterschiedlich sind.  
  
 Windows Sockets-Implementierung zu informieren, die eine **binden** Aufruf für ein Socket sollte nicht ausgeschlossen, da die gewünschte Adresse bereits von einem anderen Socket verwendet wird, sollte die Anwendung Festlegen der **SO_REUSEADDR**socket-Option für den Socket vor dem Ausstellen der **binden** aufrufen. Beachten Sie, dass die Option nur zum Zeitpunkt der interpretiert wird die **binden** aufrufen: Es ist daher auf die Option für ein Socket festgelegt, ist nicht an eine vorhandene Adresse gebunden werden, unnötige (aber ungefährlich) und festlegen oder die Option nach dem Zurücksetzen der **Binden** Aufruf hat keine Auswirkung darauf oder einen anderen Socket.  
  
 Eine Anwendung kann anfordern, die Windows Sockets-Implementierung die Verwendung von "Keep-alive" Pakete Transmission Control Protocol (TCP) Verbindungen aktivieren, indem das Einschalten der **SO_KEEPALIVE** socket-Option. Windows Sockets-Implementierung muss nicht die Verwendung von Keep-Alives unterstützen: Wenn dies der Fall ist, die genaue Semantik implementierungsspezifische sind jedoch sollte dem Abschnitt 4.2.3.6 von RFC 1122: "Anforderungen für Internethosts – Kommunikationsschichten." Wenn eine Verbindung, als Ergebnis "Keep-Alive" Fehlercode getrennt wird: **WSAENETRESET** keine Aufrufe in Bearbeitung auf den Socket zurückgegeben wird und alle nachfolgenden Aufrufe schlagen mit **WSAENOTCONN**.  
  
 Die **TCP_NODELAY** Option deaktiviert den Nagle-Algorithmus. Der Nagle-Algorithmus dient zum Verringern der Anzahl der kleine Pakete, die von einem Host per, unbestätigten senden Daten gepuffert werden, bis ein Paket in voller Größe gesendet werden kann. Jedoch für einige Anwendungen dieser Algorithmus kann die Leistung durch beeinträchtigt, und **TCP_NODELAY** können verwendet werden, um es zu deaktivieren. Anwendungsentwickler sollten nicht festgelegt. **TCP_NODELAY** , wenn die Auswirkungen auf diese Weise gut verständlich und gewünschte, seit der Einstellung ist **TCP_NODELAY** erhebliche negative Auswirkungen auf die netzwerkleistung lassen. . **TCP_NODELAY** ist die einzige unterstützte Socketoption der Ebene verwendet **IPPROTO_TCP**; alle anderen Optionen verwenden Ebene **SOL_SOCKET**.  
  
 Einige Implementierungen von Windows Sockets-Netzteils Debuginformationen ausgeben, wenn die **SO_DEBUG** Option von einer Anwendung festgelegt ist.  
  
 Die folgenden Optionen sind für unterstützt `SetSockOpt`. Den Typ identifiziert den Typ der Daten, die vom adressiert `lpOptionValue`.  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_BROADCAST**|**BOOL**|Ermöglicht die Übertragung von Broadcastmeldungen für den Socket.|  
|**SO_DEBUG**|**BOOL**|Zeichnet Debuginformationen auf.|  
|**SO_DONTLINGER**|**BOOL**|Nicht blockieren **schließen** warten, nicht gesendeten Daten gesendet werden. Festlegen dieser Option entspricht dem Festlegen **SO_LINGER** mit **L_onoff** auf 0 (null) festgelegt.|  
|**SO_DONTROUTE**|**BOOL**|Nicht weiterleiten: direkt an der Schnittstelle senden.|  
|**SO_KEEPALIVE**|**BOOL**|Senden von Keep-Alives.|  
|**SO_LINGER**|**LINGER-Struktur**|Wird verzögert, **schließen** Wenn nicht gesendete Daten vorhanden ist.|  
|**SO_OOBINLINE**|**BOOL**|Empfangen von Out-of-Band-Daten im normalen Datenstream.|  
|**SO_RCVBUF**|`int`|Geben Sie für die Größe des Puffers empfängt.|  
|**SO_REUSEADDR**|**BOOL**|Zulassen des Sockets an eine Adresse gebunden werden, der bereits verwendet wird. (Siehe [binden](#bind).)|  
|**SO_SNDBUF**|`int`|Geben Sie die Puffergröße für Sendevorgänge.|  
|**TCP_NODELAY**|**BOOL**|Deaktiviert den Nagle-Algorithmus für Sammelsendungen.|  
  
 Nicht unterstützten Optionen der Berkeley Software Distribution (BSD) `SetSockOpt` sind:  
  
|Wert|Typ|Bedeutung|  
|-----------|----------|-------------|  
|**SO_ACCEPTCONN**|**BOOL**|Socket überwacht|  
|**SO_ERROR**|`int`|Fehlerstatus abrufen und löschen.|  
|**SO_RCVLOWAT**|`int`|Untere Grenze zu empfangen.|  
|**SO_RCVTIMEO**|`int`|Empfangstimeout|  
|**SO_SNDLOWAT**|`int`|Senden Sie die untere Grenze.|  
|**SO_SNDTIMEO**|`int`|Timeout des Sendevorgangs.|  
|**SO_TYPE**|`int`|Der Typ des Sockets.|  
|**IP_OPTIONS**||SET-Optionen-Feld im IP-Header.|  
  
##  <a name="shutdown"></a>CAsyncSocket::ShutDown  
 Anruf sendet diese Memberfunktion zu deaktivieren, oder beides für den Socket.  
  
```  
BOOL ShutDown(int nHow = sends);
```  
  
### <a name="parameters"></a>Parameter  
 `nHow`  
 Ein Flag, das beschreibt, welche Arten des Vorgangs wird nicht mehr zulässig, verwenden die folgenden Enumerationswerte:  
  
- **empfängt = 0**  
  
- **sendet = 1**  
  
- **sowohl = 2**  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von [GetLastError](#getlasterror). Diese Memberfunktion gelten die folgenden Fehler:  
  
- **WSANOTINITIALISED** ein erfolgreiches [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit) vorkommen muss, bevor diese API verwenden.  
  
- **WSAENETDOWN** der Windows Sockets-Implementierung erkannt, dass das Netzwerksubsystem fehlgeschlagen ist.  
  
- **WSAEINVAL** `nHow` ist ungültig.  
  
- **"WSAEINPROGRESS" zurück** ein Blockierungsvorgang Windows Sockets wird ausgeführt.  
  
- **WSAENOTCONN** der Socket nicht verbunden ist ( **SOCK_STREAM** nur).  
  
- **WSAENOTSOCK** Deskriptor ist kein Socket.  
  
### <a name="remarks"></a>Hinweise  
 `ShutDown`wird auf allen Arten von Sockets verwendet, um den Empfang oder Übertragung zu deaktivieren. Wenn `nHow` gleich 0 ist, auf die nachfolgenden erhält der Socket wird nicht zugelassen. Dies wirkt sich nicht auf den unteren Protokollebenen aus.  
  
 Transmission Control Protocol (TCP) das TCP-Fenster wird nicht geändert und eingehende Daten werden (jedoch nicht bestätigten) akzeptiert werden, bis das Fenster angezeigt wird. User Datagram Protocol (UDP) werden eingehende Datagramme akzeptiert und in die Warteschlange eingereiht. In keinem Fall wird ein ICMP-Fehler Paket generiert werden. Wenn `nHow` beträgt 1, nachfolgende sendet sind nicht zulässig. Für TCP-Sockets wird eine FIN gesendet werden. Festlegen von `nHow` 2 deaktiviert sowohl sendet und empfängt, wie oben beschrieben.  
  
 Beachten Sie, dass `ShutDown` ist nicht schließen den Socket und Ressourcen, die an den Socket angefügt wird reserviert, bis **schließen** aufgerufen wird. Eine Anwendung sollte nicht abhängig wird einen Socket, nachdem es heruntergefahren wurde, wiederverwenden können. Windows Sockets-Implementierung ist insbesondere nicht erforderlich, für die Unterstützung von **verbinden** für solche ein Socket.  
  
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
  
- `FD_OOB`: Der Ankunft von Daten mit Out-of-Band-Benachrichtigung erhalten möchten.  
  
- `FD_ACCEPT`: Der eingehenden Verbindungen Benachrichtigung erhalten möchten.  
  
- `FD_CONNECT`: Der abgeschlossenen Verbindung Benachrichtigung erhalten möchten.  
  
- `FD_CLOSE`: Der Socket Schließvorgänge Benachrichtigung erhalten möchten.  
  
 `nProtocolType`  
 Protokoll mit den Socket verwendet werden soll, die für die angegebenen Adressfamilie spezifisch ist.  
  
 `nAddressFormat`  
 Familie Spezifikation zu beheben.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` bei Erfolg bzw. `FALSE` bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode weist ein Sockethandle. Wird nicht aufgerufen [CAsyncSocket::Bind](#bind) den Socket an eine bestimmte Adresse binden, damit Sie aufrufen müssen `Bind` später auf den Socket an eine bestimmte Adresse binden. Sie können [CAsyncSocket::SetSockOpt](#setsockopt) die Socketoption fest, bevor es gebunden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSocket-Klasse](../../mfc/reference/csocket-class.md)   
 [CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)
