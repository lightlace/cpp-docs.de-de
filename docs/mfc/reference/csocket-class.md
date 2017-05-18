---
title: CSocket-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- WinSock CSocket class
- CSocket class
- SOCKET handle
- sockets classes
ms.assetid: 7f23c081-d24d-42e3-b511-8053ca53d729
caps.latest.revision: 30
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 451ea100dbf02e365204fe4fdf1c380e855d8231
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csocket-class"></a>CSocket-Klasse
Leitet sich von `CAsyncSocket`, erbt die Kapselung der Windows Sockets-API und stellt eine höhere Abstraktionsebene als ein `CAsyncSocket` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSocket : public CAsyncSocket  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocket::CSocket](#csocket)|Erstellt ein `CSocket`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocket:: Attach](#attach)|Fügt eine **SOCKET** handle für ein `CSocket` Objekt.|  
|[CSocket::CancelBlockingCall](#cancelblockingcall)|Bricht einen blockierenden Aufruf, der gerade ausgeführt wird.|  
|[CSocket::Create](#create)|Ein Socket erstellt.|  
|[CSocket::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CSocket` -Objekt, ein **SOCKET** behandeln.|  
|[CSocket::IsBlocking](#isblocking)|Bestimmt, ob ein blockierender Aufruf ausgeführt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocket::OnMessagePending](#onmessagepending)|Aufgerufen, um ausstehende Nachrichten Prozess beim Warten auf eines blockierenden Aufrufs abgeschlossen.|  
  
## <a name="remarks"></a>Hinweise  
 `CSocket`mit den Klassen `CSocketFile` und `CArchive` das Senden und Empfangen von Daten zu verwalten.  
  
 Ein `CSocket` Objekt sorgt blockieren, ist wichtig, damit die synchrone Ausführung von `CArchive`. Blockieren von Funktionen, wie z. B. `Receive`, `Send`, `ReceiveFrom`, `SendTo`, und `Accept` (alle geerbten aus `CAsyncSocket`), keine Zurückgeben einer `WSAEWOULDBLOCK` Fehler in `CSocket`. Warten stattdessen, diese Funktionen auf, bis der Vorgang abgeschlossen ist. Darüber hinaus wird der ursprüngliche Aufruf mit Fehler beendet `WSAEINTR` Wenn `CancelBlockingCall` aufgerufen wird, während eine dieser Funktionen blockiert wird.  
  
 Verwenden einer `CSocket` Objekt, rufen Sie den Konstruktor rufen dann `Create` zum Erstellen des zugrunde liegenden `SOCKET` behandeln (Typ `SOCKET`). Die Standardparameter des `Create` erstellen einen Streamsocket, aber wenn Sie nicht den Socket mit verwenden ein `CArchive` -Objekt, geben Sie Parameter zum Erstellen Sie stattdessen eines Datagrammsockets sowie zum Binden an einen bestimmten Anschluss einen Serversocket zu erstellen. Verbinden mit einem Client Socket `Connect` auf der Clientseite und `Accept` auf dem Server. Erstellen Sie eine `CSocketFile` Objekt, und ordnen Sie sie an der `CSocket` -Objekt in die `CSocketFile` Konstruktor. Als Nächstes erstellen Sie eine `CArchive` Objekt zum Senden und eine zum Empfangen von Daten (bei Bedarf), ordnen diese dann mit der `CSocketFile` -Objekt in die `CArchive` Konstruktor. Kommunikation abgeschlossen sind, zerstört der `CArchive`, `CSocketFile`, und `CSocket` Objekte. Die `SOCKET` -Datentyp wird in diesem Artikel beschrieben [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md).  
  
 Bei Verwendung `CArchive` mit `CSocketFile` und `CSocket`, treten möglicherweise Situationen, in denen `CSocket::Receive` tritt in eine Schleife (durch `PumpMessages(FD_READ)`) warten, bis die angeforderte Anzahl der Bytes. Dies ist, da die Windows-Sockets nur ein Aufruf von empfangen pro Benachrichtigung FD_READ maskiert, ermöglichen jedoch `CSocketFile` und `CSocket` mehrere Recv-Aufrufe pro FD_READ maskiert zulassen. Wenn Sie eine FD_READ maskiert erhalten, wenn keine Daten lesen, stürzt die Anwendung. Wenn Sie einen anderen FD_READ maskiert nie erhalten, reagiert die Anwendung die Kommunikation über den Socket.  
  
 Sie können dieses Problem folgendermaßen beheben. In der `OnReceive` -Methode Ihrer Socketklasse Aufrufen `CAsyncSocket::IOCtl(FIONREAD, ...)` vor dem Aufrufen der `Serialize` -Methode Ihrer Nachrichtenklasse, wenn die erwarteten Daten in den Socket gelesen werden, die Größe des TCP-Pakets (maximale Übertragungseinheit der Netzwerk-Mittel in der Regel mit der mindestens 1096 Bytes) überschreitet. Wenn die Größe der verfügbaren Daten kleiner als erforderlich ist, warten Sie alle Daten empfangen werden und nur dann lesen.  
  
 Im folgenden Beispiel `m_dwExpected` ist die ungefähre Anzahl von Bytes, die der Benutzer erwartet, empfangen. Es wird vorausgesetzt, dass Sie an anderer Stelle im Code deklariert werden.  
  
 [!code-cpp[NVC_MFCSocketThread&4;](../../mfc/reference/codesnippet/cpp/csocket-class_1.cpp)]  
  
> [!NOTE]
>  Wenn Sie MFC-Sockets in sekundären Threads in einer statisch gebunden mit MFC_Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jedem Thread, die Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. In der Standardeinstellung `AfxSocketInit` wird nur im primären Thread aufgerufen.  
  
 Weitere Informationen finden Sie unter [Windows-Sockets in MFC](../../mfc/windows-sockets-in-mfc.md), [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md), [Windows Sockets: wie Sockets mit Archiven arbeiten](../../mfc/windows-sockets-how-sockets-with-archives-work.md), [Windows Sockets: Operationsabfolge](../../mfc/windows-sockets-sequence-of-operations.md), [Windows Sockets: Beispiel für Sockets mithilfe von Archiven](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CAsyncSocket](../../mfc/reference/casyncsocket-class.md)  
  
 `CSocket`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Datei afxsock.h  
  
##  <a name="attach"></a>CSocket:: Attach  
 Rufen Sie diese Memberfunktion Anfügen der `hSocket` handle für ein `CSocket` Objekt.  
  
```  
BOOL Attach(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parameter  
 `hSocket`  
 Enthält ein Handle für einen Socket.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich null, wenn die Funktion erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Die **SOCKET** Handle wird in des Objekts gespeichert [M_hSocket](../../mfc/reference/casyncsocket-class.md#m_hsocket) -Datenmember.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCSocketThread&#1;](../../mfc/reference/codesnippet/cpp/csocket-class_2.h)]  
  
 [!code-cpp[NVC_MFCSocketThread&#2;](../../mfc/reference/codesnippet/cpp/csocket-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCSocketThread&3;](../../mfc/reference/codesnippet/cpp/csocket-class_4.cpp)]  
  
##  <a name="cancelblockingcall"></a>CSocket::CancelBlockingCall  
 Rufen Sie diese Memberfunktion, um einen blockierenden Aufruf derzeit in Bearbeitung abbrechen.  
  
```  
void CancelBlockingCall();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion bricht alle ausstehenden Blockierungsvorgang für diesen Socket ab. Die ursprüngliche blockierende Aufruf wird so bald wie möglich mit Fehler beendet **WSAEINTR**.  
  
 Im Fall einer Blockierung **verbinden** Operation, die Windows Sockets-Implementierung wird beendet blockierenden Aufruf wie möglich, aber es möglicherweise nicht möglich, dass der Socket Ressourcen freigegeben werden, bis die Verbindung wurde abgeschlossen (und dann zurückgesetzt wurde) oder Zeitlimit überschritten. Dies ist wahrscheinlich nur, wenn die Anwendung sofort versucht wird, um einen neuen Socket (wenn keine Sockets verfügbar sind) zu öffnen oder Verbindung mit demselben Peer bemerkt werden.  
  
 Alle außer Abbruch **annehmen** lassen den Socket in einem unbestimmten Zustand. Wenn eine Anwendung einen blockierenden Vorgang auf einem Socket abgebrochen wird, ist der einzige Vorgang, der die Anwendung verlassen kann, auf dem Socket ausführen, einen Aufruf von **schließen**, obwohl andere Vorgänge auf einige Windows Sockets-Implementierung funktionieren können. Wenn Sie maximale Portabilität für Ihre Anwendung wünschen, müssen Sie darauf achten, dass keine Vorgänge nach einem Abbruch hängen sein.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="create"></a>CSocket::Create  
 Rufen Sie die **erstellen** Member-Funktion nach dem Konstruieren ein Socketobjekt, um den Windows-Socket erstellen und anfügen.  
  
```  
BOOL Create(
    UINT nSocketPort = 0,  
    int nSocketType = SOCK_STREAM,  
    LPCTSTR lpszSocketAddress = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `nSocketPort`  
 Einen bestimmten Port mit der Socket oder 0 verwendet werden soll, wenn Sie MFC ermöglicht, einen Port auswählen möchten.  
  
 `nSocketType`  
 **SOCK_STREAM** oder **SOCK_DGRAM**.  
  
 `lpszSocketAddress`  
 Ein Zeiger auf eine Zeichenfolge, die die Netzwerkadresse des verbundenen Sockets, eine gepunktete Zahl z. B. "128.56.22.8" enthält. Übergeben der **NULL** Zeichenfolge für die dieser Parameter gibt die **CSocket** Instanz Clientaktivität an allen Netzwerkschnittstellen überwachen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ist; andernfalls 0 und einen bestimmten Fehlercode kann abgerufen werden durch Aufrufen von `GetLastError`.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** ruft dann **binden** beim Binden des Sockets an die angegebene Adresse. Die folgenden Sockettypen werden unterstützt:  
  
- **SOCK_STREAM** sequenziert, bietet zuverlässige bidirektionale, verbindungsbasiertes Bytestreams. Verwendet Transmission Control Protocol (TCP) für die Internet-Adressfamilie.  
  
- **SOCK_DGRAM** Datagramme, die verbindungsloses und nicht zuverlässiges Puffer fester (normalerweise klein) maximale Länge unterstützt. Verwendet User Datagram Protocol (UDP) für die Internet-Adressfamilie. Um diese Option verwenden zu können, verwenden Sie nicht den Socket mit einem `CArchive` Objekt.  
  
    > [!NOTE]
    >  Die **annehmen** Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Sie müssen dieses Objekt erstellen, vor dem Aufruf von **annehmen**. Beachten Sie, dass, wenn dieses Socketobjekt des Bereichs an, die Verbindung geschlossen wird. Rufen Sie **erstellen** für dieses neue Socketobjekt.  
  
 Weitere Informationen zu Stream und Datagram Sockets, finden Sie in den Artikeln [Windows Sockets: Hintergrund](../../mfc/windows-sockets-background.md), [Windows Sockets: Ports und Socketadressen](../../mfc/windows-sockets-ports-and-socket-addresses.md), und [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="csocket"></a>CSocket::CSocket  
 Erstellt ein `CSocket`-Objekt.  
  
```  
CSocket();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung, rufen Sie die **erstellen** Member-Funktion.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="fromhandle"></a>CSocket::FromHandle  
 Gibt einen Zeiger auf ein `CSocket` Objekt.  
  
```  
static CSocket* PASCAL FromHandle(SOCKET hSocket);
```  
  
### <a name="parameters"></a>Parameter  
 `hSocket`  
 Enthält ein Handle für einen Socket.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CSocket` -Objekt, oder **NULL** ist keine `CSocket` Objekt angefügt, um `hSocket`.  
  
### <a name="remarks"></a>Hinweise  
 Bei einer **SOCKET** zu behandeln, wenn eine `CSocket` Objekt ist nicht auf das Handle verknüpft, die Memberfunktion gibt **NULL** und ein temporäres Objekt erstellt.  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="isblocking"></a>CSocket::IsBlocking  
 Rufen Sie diese Memberfunktion, um festzustellen, ob ein blockierender Aufruf ausgeführt wird.  
  
```  
BOOL IsBlocking();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Socket blockiert wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
##  <a name="onmessagepending"></a>CSocket::OnMessagePending  
 Überschreiben Sie diese Memberfunktion zum Suchen nach bestimmten Nachrichten von Windows und reagieren darauf in der Socket.  
  
```  
virtual BOOL OnMessagePending();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Meldung verarbeitet wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine erweiterte überschrieben.  
  
 Das Framework ruft `OnMessagePending` während der Socket Windows-Meldungen, um Sie Gelegenheit für den Umgang mit Nachrichten von Interesse für Ihre Anwendung weiterleitet. Beispiele für die Verwendung `OnMessagePending`, finden Sie im Artikel [Windows Sockets: Ableiten von Socketklassen](../../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Weitere Informationen finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket-Klasse](../../mfc/reference/casyncsocket-class.md)   
 [CSocketFile-Klasse](../../mfc/reference/csocketfile-class.md)

