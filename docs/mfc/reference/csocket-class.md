---
title: CSocket-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSocket
- AFXSOCK/CSocket
- AFXSOCK/CSocket::CSocket
- AFXSOCK/CSocket::Attach
- AFXSOCK/CSocket::CancelBlockingCall
- AFXSOCK/CSocket::Create
- AFXSOCK/CSocket::FromHandle
- AFXSOCK/CSocket::IsBlocking
- AFXSOCK/CSocket::OnMessagePending
dev_langs:
- C++
helpviewer_keywords:
- CSocket [MFC], CSocket
- CSocket [MFC], Attach
- CSocket [MFC], CancelBlockingCall
- CSocket [MFC], Create
- CSocket [MFC], FromHandle
- CSocket [MFC], IsBlocking
- CSocket [MFC], OnMessagePending
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 170acf3fb9d8cc1e63177a372517cccc8e21b94c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445125"
---
# <a name="csocket-class"></a>CSocket-Klasse

Leitet sich von `CAsyncSocket`, erbt die Kapselung der Windows Sockets-API und stellt eine höhere Abstraktionsebene als bei einem `CAsyncSocket` Objekt.

## <a name="syntax"></a>Syntax

```
class CSocket : public CAsyncSocket
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSocket::CSocket](#csocket)|Erstellt ein `CSocket`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSocket:: Attach](#attach)|Fügt ein Sockethandle für ein `CSocket` Objekt.|
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Bricht einen blockierenden Aufruf, der gerade ausgeführt wird.|
|[CSocket::Create](#create)|Erstellt einen Socket.|
|[CSocket::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CSocket` -Objekt, ein SOCKET-Handle.|
|[CSocket::IsBlocking](#isblocking)|Bestimmt, ob ein blockierender Aufruf ausgeführt wird.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSocket::OnMessagePending](#onmessagepending)|Aufgerufen wird, um den Prozess ausstehender Nachrichten beim Warten auf eines blockierenden Aufrufs abgeschlossen.|

## <a name="remarks"></a>Hinweise

`CSocket` mit den Klassen `CSocketFile` und `CArchive` das Senden und Empfangen von Daten zu verwalten.

Ein `CSocket` Objekt hauptstartseite blockiert wird, ist wichtig, damit die synchronen Vorgang `CArchive`. Blockieren Sie die Funktionen, z. B. `Receive`, `Send`, `ReceiveFrom`, `SendTo`, und `Accept` (alle geerbten aus `CAsyncSocket`), keine Zurückgeben einer `WSAEWOULDBLOCK` Fehler in `CSocket`. Warten stattdessen diese Funktionen auf, bis der Vorgang abgeschlossen ist. Darüber hinaus wird der ursprüngliche Aufruf mit dem Fehler WSAEINTR beendet, wenn `CancelBlockingCall` wird aufgerufen, während eine dieser Funktionen blockiert wird.

Verwenden einer `CSocket` Objekt, rufen Sie den Konstruktor, rufen Sie anschließend `Create` zum Erstellen der zugrunde liegenden SOCKET-Handle (SOCKET-Typ). Die Standardparameter des `Create` Erstellen eines Streamsockets, aber wenn Sie nicht den Socket mit verwenden eine `CArchive` -Objekt können Sie einen Parameter, um stattdessen einen Datagrammsocket zu erstellen oder zu einem bestimmten Port binden, erstellen Sie einen Serversocket angeben. Verbinden mit einer Client-Socket verwenden `Connect` auf der Clientseite und `Accept` auf dem Server. Erstellen Sie dann eine `CSocketFile` Objekt aus, und ordnen Sie ihn der `CSocket` -Objekt in der `CSocketFile` Konstruktor. Als Nächstes erstellen Sie eine `CArchive` -Objekt zum Senden und eine zum Empfangen von Daten (bei Bedarf), ordnen Sie sie mit der `CSocketFile` -Objekt in der `CArchive` Konstruktor. Bei der Kommunikation abgeschlossen wurden, zerstört die `CArchive`, `CSocketFile`, und `CSocket` Objekte. Der Datentyp SOCKET wird in diesem Artikel beschrieben [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).

Bei Verwendung von `CArchive` mit `CSocketFile` und `CSocket`, treten möglicherweise eine Situation, in denen `CSocket::Receive` tritt in eine Schleife (von `PumpMessages(FD_READ)`) warten auf die angeforderte Anzahl der Bytes. Dies ist, da Windows Sockets nur ein empfangener Aufruf pro FD_READ maskiert-Benachrichtigung, ermöglichen aber `CSocketFile` und `CSocket` mehrere empfangener Anrufe pro FD_READ maskiert zulassen. Wenn Sie eine FD_READ maskiert erhalten, wenn keine Daten lesen, hängt die Anwendung. Wenn Sie einen anderen FD_READ maskiert nie erhalten haben, reagiert die Anwendung die Kommunikation über den Socket.

Sie können dieses Problem wie folgt beheben. In der `OnReceive` -Methode der Socket-Klasse, Aufruf `CAsyncSocket::IOCtl(FIONREAD, ...)` vor dem Aufruf der `Serialize` Methode Ihrer Message-Klasse, wenn die erwarteten Daten vom Socket gelesen werden, die Größe des TCP-Pakets (maximale Übertragungseinheit des Mediums Netzwerk überschreitet in der Regel mit der mindestens 1096 Bytes). Wenn die Größe der verfügbaren Daten kleiner als erforderlich ist, warten Sie alle Daten empfangen werden und erst dann damit den Lesevorgang beginnt.

Im folgenden Beispiel `m_dwExpected` wird die ungefähre Anzahl von Bytes, die der Benutzer zu empfangen erwartet. Es wird vorausgesetzt, dass Sie sie an anderer Stelle in Ihrem Code deklarieren.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]

> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC-Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jeder Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. In der Standardeinstellung `AfxSocketInit` nur im primären Thread aufgerufen wird.

Weitere Informationen finden Sie unter [Windows-Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets: wie Sockets mit Archiven arbeiten](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets: Reihenfolge der Operationen](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets: Beispiel für Sockets mithilfe der Archive](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CAsyncSocket](../../mfc/reference/casyncsocket-class.md)

`CSocket`

## <a name="requirements"></a>Anforderungen

**Header:** Datei afxsock.h

##  <a name="attach"></a>  CSocket:: Attach

Rufen Sie diese Memberfunktion zum Anfügen der `hSocket` handle für ein `CSocket` Objekt.

```
BOOL Attach(SOCKET hSocket);
```

### <a name="parameters"></a>Parameter

*hSocket*<br/>
Enthält ein Handle für einen Socket.

### <a name="return-value"></a>Rückgabewert

Ungleich null, wenn die Funktion erfolgreich ist.

### <a name="remarks"></a>Hinweise

Der SOCKET-Handle befindet sich in den Objekteigenschaften [M_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) -Datenmember.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]

[!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]

[!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]

##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall

Rufen Sie diese Memberfunktion, um einen blockierenden Aufruf gerade abzubrechen.

```
void CancelBlockingCall();
```

### <a name="remarks"></a>Hinweise

Diese Funktion bricht alle ausstehenden blockierender Vorgang für diesen Socket ab. Der ursprüngliche blockierende Aufruf wird mit dem Fehler WSAEINTR so bald wie möglich beendet werden.

Im Fall von blockieren einer `Connect` -Operation, die Windows Sockets-Implementierung wird beendet den blockierenden Aufruf, sobald wie möglich, aber es möglicherweise nicht möglich, dass der socketressourcen freigegeben werden, bis die Verbindung wurde abgeschlossen (und dann zurückgesetzt wurde) oder Timeout. Dies ist wahrscheinlich nur dann, wenn die Anwendung sofort versucht wird, um einen neuen Socket (wenn keine Sockets verfügbar sind) zu öffnen oder Verbindung mit demselben Peer bemerkt werden.

Jeder Vorgang nicht Abbrechen `Accept` können den Socket in einem unbestimmten Zustand belassen. Wenn eine Anwendung für einen Socket einen blockierenden Vorgang abbricht, ist der einzige Vorgang, der die Anwendung verlassen kann, auf dem Socket durchführen können, einen Aufruf von `Close`, obwohl einige Windows Sockets-Implementierungen anderen Vorgängen bearbeitet werden können. Wenn Sie die maximale Portabilität für Ihre Anwendung wünschen, müssen Sie darauf achten, nicht abhängig sind, zum Durchführen von Vorgängen nach dem ein Abbruch sein.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="create"></a>  CSocket::Create

Rufen Sie die **erstellen** Memberfunktion nach dem Erstellen der ein Socketobjekt, um den Windows-Socket zu erstellen und anzufügen.

```
BOOL Create(
    UINT nSocketPort = 0,
    int nSocketType = SOCK_STREAM,
    LPCTSTR lpszSocketAddress = NULL);
```

### <a name="parameters"></a>Parameter

*nSocketPort*<br/>
Ein bestimmter Port mit der Socket, oder 0 verwendet werden, wenn Sie MFC ermöglicht, einen Port auswählen möchten.

*nSocketType*<br/>
SOCK_STREAM oder SOCK_DGRAM.

*lpszSocketAddress*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets, ein durch Punkte getrennte Zahl wie z. B. "128.56.22.8" enthält. Übergeben das NULL-Zeichen Zeichenfolge, für die dieser Parameter gibt an, die `CSocket` Instanz Clientaktivität an allen Netzwerkschnittstellen überwachen soll.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0, und einen bestimmten Fehlercode abrufen können, indem Aufrufen `GetLastError`.

### <a name="remarks"></a>Hinweise

`Create` Ruft dann `Bind` der Socket mit der angegebenen Adresse binden. Die folgenden Sockettypen werden unterstützt:

- SOCK_STREAM sequenziert, bietet zuverlässige, bidirektionale, verbindungsbasierte Bytestreams. Wird Sie für die Internetadressenfamilie Transmission Control Protocol (TCP) verwendet.

- SOCK_DGRAM unterstützt Datagramme, die verbindungslose, unzuverlässige Puffer mit einer festen (i. d. r. kleinen) maximalen Länge sind. Verwendet User Datagram Protocol (UDP), für die Internetadressenfamilie. Um diese Option verwenden zu können, verwenden Sie nicht den Socket mit einem `CArchive` Objekt.

    > [!NOTE]
    >  Die `Accept` Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Müssen Sie dieses Objekt erstellen, vor dem Aufruf `Accept`. Beachten Sie, dass wenn dieser Socketobjekt des Bereichs, die Verbindung geschlossen wird. Rufen Sie keine `Create` für dieses neuen Socketobjekt.

Weitere Informationen zu Stream und Datagramm-Sockets, finden Sie in den Artikeln [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md), [Windows Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md), und [Windows Sockets: verwenden Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="csocket"></a>  CSocket::CSocket

Erstellt ein `CSocket`-Objekt.

```
CSocket();
```

### <a name="remarks"></a>Hinweise

Nach der Erstellung, müssen Sie den Aufrufen der `Create` Member-Funktion.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="fromhandle"></a>  CSocket::FromHandle

Gibt einen Zeiger auf eine `CSocket` Objekt.

```
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```

### <a name="parameters"></a>Parameter

*hSocket*<br/>
Enthält ein Handle für einen Socket.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CSocket` Objekt oder NULL, wenn es gibt keine `CSocket` Objekt angefügt, um *hSocket*.

### <a name="remarks"></a>Hinweise

Wenn ein SOCKET-Handle, wenn eine `CSocket` Objekt ist nicht auf das Handle angefügt, die Memberfunktion gibt NULL zurück, und ein temporäres Objekt wird nicht erstellt werden.

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="isblocking"></a>  CSocket::IsBlocking

Rufen Sie diese Memberfunktion, um festzustellen, ob ein blockierender Aufruf ausgeführt wird.

```
BOOL IsBlocking();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Socket blockiert wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

##  <a name="onmessagepending"></a>  CSocket::OnMessagePending

Überschreiben Sie diese Memberfunktion zum Suchen Sie nach bestimmten Nachrichten von Windows und in Ihre Socket beantwortet.

```
virtual BOOL OnMessagePending();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Meldung behandelt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Dies ist ein fortschrittlicher überschreibbar.

Das Framework ruft `OnMessagePending` während der Socket Windows-Meldungen, um Sie Gelegenheit für den Umgang mit Nachrichten für Ihre Anwendung weiterleitet. Beispiele für die Verwendung `OnMessagePending`, finden Sie im Artikel [Windows Sockets: Ableiten von Socket-Classen](../../mfc/windows-sockets-deriving-from-socket-classes.md).

Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).

## <a name="see-also"></a>Siehe auch

[CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)
