---
title: CSocket-Klasse | Microsoft Docs
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
ms.openlocfilehash: 8c423f1423c874dbf110cfd6951b3510fe0506af
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121876"
---
# <a name="csocket-class"></a>CSocket-Klasse
Leitet sich von `CAsyncSocket`, erbt die Kapselung von der Windows Sockets-API und stellt ein höheres Maß an Abstraktion als die von einem `CAsyncSocket` Objekt.  
  
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
|[CSocket::Create](#create)|Ein Socket erstellt.|  
|[CSocket::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CSocket` -Objekt, ein Sockethandle.|  
|[CSocket::IsBlocking](#isblocking)|Bestimmt, ob ein sperraufruf ausgeführt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|Aufgerufen wird, um ausstehende Nachrichten Prozess beim Warten auf eines blockierenden Aufrufs abgeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 `CSocket` kann mit Klassen `CSocketFile` und `CArchive` das Senden und Empfangen von Daten zu verwalten.  
  
 Ein `CSocket` Objekt zudem blockieren, ist wichtig, damit die synchrone Ausführung von `CArchive`. Blockieren von Funktionen, wie z. B. `Receive`, `Send`, `ReceiveFrom`, `SendTo`, und `Accept` (alle geerbten aus `CAsyncSocket`), keine Zurückgeben einer `WSAEWOULDBLOCK` Fehler in `CSocket`. Warten Sie stattdessen diese Funktionen auf, bis der Vorgang abgeschlossen ist. Darüber hinaus wird der ursprüngliche Aufruf mit dem Fehler WSAEINTR beendet, wenn `CancelBlockingCall` aufgerufen wird, während eine dieser Funktionen blockiert wird.  
  
 Verwenden einer `CSocket` Objekt, rufen Sie den Konstruktor rufen Sie anschließend `Create` der zugrunde liegenden SOCKET-Handle (Typ SOCKET) zu erstellen. Die Standardparameter eines `Create` ein Streamsocket erstellt, aber wenn Sie nicht den Socket mit verwenden eine `CArchive` -Objekt können Sie einen Parameter, um einen Datagrammsocket stattdessen erstellen oder zu einem bestimmten Port binden, zum Erstellen eines Serversockets angeben. Herstellen einer Verbindung mit einem Client Socket mithilfe `Connect` auf der Clientseite und `Accept` auf der Serverseite. Erstellen Sie dann eine `CSocketFile` Objekt, und ordnen sie auf der `CSocket` Objekt in der `CSocketFile` Konstruktor. Als Nächstes erstellen Sie eine `CArchive` -Objekt zum Senden und eine zum Empfangen von Daten (wie erforderlich), weisen diese dann mit der `CSocketFile` Objekt in der `CArchive` Konstruktor. Wenn Kommunikation abgeschlossen sind, Zerstören der `CArchive`, `CSocketFile`, und `CSocket` Objekte. Der Datentyp SOCKET ist im Artikel beschriebenen [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).  
  
 Bei Verwendung von `CArchive` mit `CSocketFile` und `CSocket`, treten möglicherweise eine Situation, in denen `CSocket::Receive` geht in einer Schleife (durch `PumpMessages(FD_READ)`) warten auf die angeforderte Anzahl der Bytes. Dies ist, da die Windows-Sockets nur ein Aufruf von Recv pro FD_READ maskiert Benachrichtigung, können aber `CSocketFile` und `CSocket` können mehrere Recv Aufrufe pro FD_READ maskiert. Wenn Sie eine FD_READ maskiert erhalten, wenn keine Daten lesen, stürzt die Anwendung. Wenn Sie einen anderen FD_READ maskiert nie erhalten, reagiert die Anwendung die Kommunikation über den Socket.  
  
 Sie können dieses Problem wie folgt beheben. In der `OnReceive` Methode der Socket-Klasse, Aufruf `CAsyncSocket::IOCtl(FIONREAD, ...)` vor dem Aufrufen der `Serialize` -Methode einer Nachrichtenklasse überschritten, die Größe des TCP-Pakets (maximum Transmission Unit des Mediums Netzwerk die erwarteten Daten aus den Socket gelesen werden in der Regel mit der mindestens 1096 Bytes). Wenn die Größe der verfügbaren Daten kleiner als erforderlich ist, warten Sie alle Daten empfangen werden und nur den Lesevorgang starten.  
  
 Im folgenden Beispiel `m_dwExpected` die ungefähre Anzahl von Bytes, die vom Benutzer erwarteten empfangen wird. Es wird vorausgesetzt, dass Sie an anderer Stelle im Code deklariert werden.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC_Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jedem Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. Standardmäßig `AfxSocketInit` nur im primären Thread aufgerufen wird.  
  
 Weitere Informationen finden Sie unter [Windows-Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets: wie Sockets mit Archiven arbeiten](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets: Reihenfolge der Operationen](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets: Beispiel für Sockets mit Archiven](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Datei afxsock.h  
  
##  <a name="attach"></a>  CSocket:: Attach  
 Rufen Sie diese Memberfunktion für die Verbindung der `hSocket` handle für ein `CSocket` Objekt.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parameter  
 *hSocket*  
 Enthält ein Handle für ein Socket.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich null, wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 SOCKET-Handle wird gespeichert, in des Objekts [M_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) -Datenmember.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSocketThread#1](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread#2](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread#3](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>  CSocket::CancelBlockingCall  
 Rufen Sie diese Memberfunktion, um einen blockierenden Aufruf gleichzeitig in Verarbeitung befindlichen "Abbrechen".  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bricht alle ausstehenden Blockierungsvorgang für diese Socket ab. Der ursprüngliche blockierende Aufruf wird so bald wie möglich mit dem Fehler WSAEINTR beendet.  
  
 Im Fall von blockieren einer empfangenen `Connect` Vorgang, der Windows Sockets-Implementierung wird abgebrochen blockierenden Aufruf als möglich, aber es möglicherweise nicht möglich, dass der Socket Ressourcen freigegeben werden, bis die Verbindung wurde abgeschlossen (und dann zurückgesetzt wurde) oder Timeout. Dies ist wahrscheinlich nur, wenn die Anwendung sofort versucht wird, um einen neuen Socket (wenn keine Sockets verfügbar sind) zu öffnen oder zur Verbindung mit demselben Peers bemerkbar.  
  
 Jeder Vorgang nicht Abbrechen `Accept` lassen den Socket in einem unbestimmten Zustand. Wenn eine Anwendung einen Blockierungsvorgang Socket abgebrochen wird, die nur Operation, die die Anwendung auf wird auf der Ebene ausführen kann aufgerufen wird, `Close`, obwohl andere Vorgänge auf einigen Windows-Sockets-Implementierungen funktionieren können. Wenn Sie maximale Portabilität für Ihre Anwendung verwendet werden soll, müssen Sie darauf achten, keine richten sich nach Ausführen von Vorgängen nach einem "Abbrechen" sein.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="create"></a>  CSocket::Create  
 Rufen Sie die **erstellen** Memberfunktion nach dem Erstellen einer Socketobjekt, um die Windows Socket erstellt und angefügt.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *nSocketPort*  
 Ein bestimmter Port mit der Socket oder 0 verwendet werden soll, wenn Sie MFC ermöglicht, einen Port auswählen möchten.  
  
 *nSocketType*  
 SOCK_STREAM oder SOCK_DGRAM.  
  
 *lpszSocketAddress*  
 Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets, einer gepunkteten Zahl wie "128.56.22.8" enthält. Übergeben das NULL-Zeichen Zeichenfolge, für die dieser Parameter gibt an die `CSocket` Instanz für die Clientaktivität an allen Netzwerkschnittstellen überwacht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode abgerufen werden durch Aufrufen von `GetLastError`.  
  
### <a name="remarks"></a>Hinweise  
 `Create` Ruft dann `Bind` der Socket an die angegebene Adresse binden. Die folgenden Sockettypen werden unterstützt:  
  
- SOCK_STREAM sequenziert, bietet zuverlässige, bidirektionale, Verbindungsbasiert Bytestreams. Transmission Control Protocol (TCP) verwendet für die Internetadressenfamilie.  
  
- Datagramme SOCK_DGRAM unterstützt, die Verbindungs- und unzuverlässige Puffer mit einer festen (normalerweise klein) maximale Länge sind. Verwendet (UDP = User Datagram Protocol) für die Internetadressenfamilie an. Um diese Option verwenden zu können, müssen Sie nicht den Socket mit verwenden eine `CArchive` Objekt.  
  
    > [!NOTE]
    >  Die `Accept` Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Sie müssen dieses Objekt erstellen, vor dem Aufruf `Accept`. Beachten Sie, dass wenn dieser Socketobjekt des Bereichs, die Verbindung geschlossen wird. Rufen Sie nicht `Create` für dieses neue Socketobjekt.  
  
 Weitere Informationen zu Stream als auch datagrammnachrichten Sockets, finden Sie in den Artikeln [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md), [Windows Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md), und [Windows Sockets: verwenden Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="csocket"></a>  CSocket::CSocket  
 Erstellt ein `CSocket`-Objekt.  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung, rufen Sie die `Create` Memberfunktion.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="fromhandle"></a>  CSocket::FromHandle  
 Gibt einen Zeiger auf eine `CSocket` Objekt.  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parameter  
 *hSocket*  
 Enthält ein Handle für ein Socket.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CSocket` -Objekt oder NULL, wenn es ist keine `CSocket` Objekt angefügt, um *hSocket*.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein SOCKET-Handle, wenn ein `CSocket` Objekt nicht an das Handle angefügt ist, die Member-Funktion gibt NULL zurück, und kein temporäres Objekt erstellt.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isblocking"></a>  CSocket::IsBlocking  
 Rufen Sie diese Memberfunktion, um festzustellen, ob ein sperraufruf ausgeführt wird.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Socket blockiert wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="onmessagepending"></a>  CSocket::OnMessagePending  
 Überschreiben Sie diese Memberfunktion, um bestimmte Nachrichten von Windows suchen und reagieren Sie darauf in Ihrer Socket.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Meldung verarbeitet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte überschrieben.  
  
 Das Framework ruft `OnMessagePending` während der Socket wird Windows-Meldungen, um Sie für den Umgang mit Nachrichten für Ihre Anwendung ermöglichen, Pumping fortgesetzt werden. Beispiele für die Verwendung `OnMessagePending`, finden Sie im Artikel [Windows Sockets: Ableiten von Socket-Classen](../../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)
