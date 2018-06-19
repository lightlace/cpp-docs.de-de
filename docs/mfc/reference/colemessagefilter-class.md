---
title: COleMessageFilter Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleMessageFilter
- AFXOLE/COleMessageFilter
- AFXOLE/COleMessageFilter::COleMessageFilter
- AFXOLE/COleMessageFilter::BeginBusyState
- AFXOLE/COleMessageFilter::EnableBusyDialog
- AFXOLE/COleMessageFilter::EnableNotRespondingDialog
- AFXOLE/COleMessageFilter::EndBusyState
- AFXOLE/COleMessageFilter::OnMessagePending
- AFXOLE/COleMessageFilter::Register
- AFXOLE/COleMessageFilter::Revoke
- AFXOLE/COleMessageFilter::SetBusyReply
- AFXOLE/COleMessageFilter::SetMessagePendingDelay
- AFXOLE/COleMessageFilter::SetRetryReply
dev_langs:
- C++
helpviewer_keywords:
- COleMessageFilter [MFC], COleMessageFilter
- COleMessageFilter [MFC], BeginBusyState
- COleMessageFilter [MFC], EnableBusyDialog
- COleMessageFilter [MFC], EnableNotRespondingDialog
- COleMessageFilter [MFC], EndBusyState
- COleMessageFilter [MFC], OnMessagePending
- COleMessageFilter [MFC], Register
- COleMessageFilter [MFC], Revoke
- COleMessageFilter [MFC], SetBusyReply
- COleMessageFilter [MFC], SetMessagePendingDelay
- COleMessageFilter [MFC], SetRetryReply
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85161e7f3dd752c6df27afedf6276f8823e7ec6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371363"
---
# <a name="colemessagefilter-class"></a>COleMessageFilter-Klasse
Verwaltet die Parallelität, die für die Interaktion von OLE-Anwendungen benötigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Erstellt ein `COleMessageFilter`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Setzt die Anwendung im Status "ausgelastet".|  
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Aktiviert und deaktiviert das Dialogfeld wird angezeigt, wenn eine aufgerufene Anwendung ausgelastet ist.|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Aktiviert und deaktiviert das Dialogfeld wird angezeigt, wenn eine aufgerufene Anwendung nicht reagiert.|  
|[COleMessageFilter::EndBusyState](#endbusystate)|Beendet die Anwendung ausgelastet.|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Vom Framework zum Verarbeiten von Nachrichten aufgerufen, während ein OLE-Aufruf ausgeführt wird.|  
|[COleMessageFilter::Register](#register)|Den Nachrichtenfilter registriert OLE-System-DLLs.|  
|[COleMessageFilter::Revoke](#revoke)|Hebt die Nachrichtenfilter Registrierung mit OLE-System-DLLs an.|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Bestimmt die ausgelastete Anwendung Antworten zu einem OLE-Aufruf.|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Bestimmt, wie lange die Anwendung auf eine Antwort auf einen OLE-Aufruf wartet.|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|Bestimmt die aufrufende Anwendung Antworten Sie auf eine ausgelastete Anwendung an.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COleMessageFilter` -Klasse eignet sich für Server und-Container Anwendungen für visuelle Bearbeitung sowie Anwendungen von OLE-Automatisierung. Für serveranwendungen, die aufgerufen werden, kann diese Klasse verwendet werden, um die Anwendung "ausgelastet" vornehmen, damit eingehende Aufrufe von anderen containeranwendungen abgebrochen oder später erneut ausgeführt werden. Diese Klasse kann auch verwendet werden, um zu bestimmen, die Aktion, die von einer aufrufenden Anwendung ausgeführt wird, wenn die aufgerufene Anwendung ausgelastet ist.  
  
 Allgemeine Verwendung ist für eine Serveranwendung aufrufen, [BeginBusyState](#beginbusystate) und [EndBusyState](#endbusystate) Wenn ist es wäre gefährlich für ein Dokument oder eine andere OLE-Objekts zugegriffen werden kann, die gelöscht werden. Diese Aufrufe [OnIdle](../../mfc/reference/cwinapp-class.md#onidle) während eines Updates der Benutzeroberfläche.  
  
 Wird standardmäßig ein `COleMessageFilter` Objekt zugewiesen wird, wenn die Anwendung initialisiert wird. Sie können abgerufen werden, mit [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
 Hierbei handelt es sich um eine erweiterte Klasse; Sie müssen nur selten direkt mit der sie arbeiten.  
  
 Weitere Informationen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState  
 Mit dieser Funktion können ausgelasteten Zustand zu starten.  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>Hinweise  
 Funktioniert in Kombination mit [EndBusyState](#endbusystate) ausgelastet Anwendungsstatus zu steuern. Die Funktion [SetBusyReply](#setbusyreply) bestimmt die Anwendung Antworten an aufrufende Anwendungen aus, wenn sie stark ausgelastet ist.  
  
 Die `BeginBusyState` und `EndBusyState` Aufrufe Inkrementieren und Dekrementieren, bzw. einen Leistungsindikator, der bestimmt, ob die Anwendung ausgelastet ist. Beispielsweise die beiden Aufrufe von `BeginBusyState` und ein Aufruf von `EndBusyState` bleibt in einem ausgelasteten Zustand. Ausgelasteten Zustand Abbrechen, es erforderlich ist, rufen Sie `EndBusyState` die gleiche Anzahl von Zeiten `BeginBusyState` aufgerufen wurde.  
  
 Wird standardmäßig das Framework wechselt in den ausgelastet Status während der leerlaufverarbeitung von ausgeführt wird [OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Während die Anwendung verarbeitet **ON_COMMANDUPDATEUI** Benachrichtigungen, eingehende Aufrufe werden später verarbeitet, nachdem leerlaufverarbeitung abgeschlossen ist.  
  
##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter  
 Erstellt ein `COleMessageFilter`-Objekt.  
  
```  
COleMessageFilter();
```  
  
##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog  
 Aktiviert und deaktiviert die ausgelastet Dialogfeld angezeigt wird, wenn die Nachricht ausstehende Verzögerung abläuft (finden Sie unter [SetRetryReply](#setretryreply)) während eines OLE-Aufrufs.  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableBusy*  
 Gibt an, ob das Dialogfeld "ausgelastet" aktiviert oder deaktiviert ist.  
  
##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog  
 Aktiviert und deaktiviert das Dialogfeld "nicht aktiv", der angezeigt wird, wenn eine Nachricht Tastatur- oder Maustastenzustand ausstehend ist bei einer OLE Aufruf und durch das Timeout.  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableNotResponding*  
 Gibt an, ob das Dialogfeld "nicht aktiv" aktiviert oder deaktiviert ist.  
  
##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState  
 Mit dieser Funktion können ausgelasteten Zustand zu beenden.  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>Hinweise  
 Funktioniert in Kombination mit [BeginBusyState](#beginbusystate) ausgelastet Anwendungsstatus zu steuern. Die Funktion [SetBusyReply](#setbusyreply) bestimmt die Anwendung Antworten an aufrufende Anwendungen aus, wenn sie stark ausgelastet ist.  
  
 Die `BeginBusyState` und `EndBusyState` Aufrufe Inkrementieren und Dekrementieren, bzw. einen Leistungsindikator, der bestimmt, ob die Anwendung ausgelastet ist. Beispielsweise die beiden Aufrufe von `BeginBusyState` und ein Aufruf von `EndBusyState` bleibt in einem ausgelasteten Zustand. Ausgelasteten Zustand Abbrechen, es erforderlich ist, rufen Sie `EndBusyState` die gleiche Anzahl von Zeiten `BeginBusyState` aufgerufen wurde.  
  
 Wird standardmäßig das Framework wechselt in den ausgelastet Status während der leerlaufverarbeitung von ausgeführt wird [OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Während die Anwendung verarbeitet `ON_UPDATE_COMMAND_UI` Benachrichtigungen, eingehende Aufrufe werden verarbeitet, nachdem die leerlaufverarbeitung abgeschlossen ist.  
  
##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending  
 Vom Framework zum Verarbeiten von Nachrichten aufgerufen, während ein OLE-Aufruf ausgeführt wird.  
  
```  
virtual BOOL OnMessagePending(const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Ein Zeiger auf die ausstehende Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine aufrufende Anwendung für einen Aufruf abgeschlossen werden, wartet das Framework ruft `OnMessagePending` mit einem Zeiger auf die ausstehende Nachricht. Standardmäßig sendet das Framework `WM_PAINT` Nachrichten verwenden, sodass Fenster Updates während eines Aufrufs auftreten können, die einen längeren Zeitraum benötigt wird.  
  
 Sie müssen Ihre Nachrichtenfilter registrieren, durch einen Aufruf von [registrieren](#register) , bevor es aktiviert werden kann.  
  
##  <a name="register"></a>  COleMessageFilter::Register  
 Den Nachrichtenfilter registriert OLE-System-DLLs.  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Ein Nachrichtenfilter hat keine Auswirkungen, es sei denn, sie mit der System-DLLs registriert ist. Initialisierungscode für Ihre Anwendung wird in der Regel Nachrichtenfilter für die Anwendung registriert. Alle anderen von der Anwendung registriert Nachrichtenfilter aufgehoben werden soll, bevor das Programm beendet, durch den Aufruf von wird [widerrufen](#revoke).  
  
 Das Framework standardmäßig Nachrichtenfilter wird automatisch während der Initialisierung registriert und bei Beendigung aufgehoben.  
  
##  <a name="revoke"></a>  COleMessageFilter::Revoke  
 Hebt eine vorherige Registrierung durchgeführt, die durch einen Aufruf von [registrieren](#register).  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Nachrichtenfilter sollte aufgehoben werden, bevor das Programm beendet wird.  
  
 Der Standardfilter für die Nachricht, die erstellt und automatisch vom Framework registriert, wird außerdem automatisch gesperrt.  
  
##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply  
 Diese Funktion setzt die Anwendung "ausgelastet Reply."  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>Parameter  
 *nBusyReply*  
 Ein Wert aus der `SERVERCALL` -Enumeration, die in der Datei COMPOBJ definiert ist. H. Es kann eine der folgenden Werte aufweisen:  
  
- **SERVERCALL_ISHANDLED** die Anwendung können Aufrufe annehmen, aber möglicherweise ein Fehler bei der Verarbeitung eines bestimmten Aufrufs.  
  
- **SERVERCALL_REJECTED** die Anwendung wahrscheinlich werden nie einen Aufruf verarbeitet.  
  
- **IOleMessageFilter.HandleIncomingCall** die Anwendung ist vorübergehend in einem Zustand in der sie einen Aufruf nicht verarbeiten kann.  
  
### <a name="remarks"></a>Hinweise  
 Die [BeginBusyState](#beginbusystate) und [EndBusyState](#endbusystate) Funktionen steuern die Anwendung ausgelastet.  
  
 Wenn eine Anwendung wurde mit einem Aufruf von ausgelasteten `BeginBusyState`, es reagiert auf Aufrufe von OLE-System-DLLs mit einem Wert, der bestimmt, indem die letzte Einstellung des `SetBusyReply`. Die aufrufende Anwendung verwendet diese Antwort ausgelastet, um zu bestimmen, welche Aktion.  
  
 Wird standardmäßig die ausgelastet Antwort **IOleMessageFilter.HandleIncomingCall**. Diese Antwort führt dazu, dass die aufrufende Anwendung den Aufruf so bald wie möglich erneut zu versuchen.  
  
##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay  
 Bestimmt, wie lange die aufrufende Anwendung auf eine Antwort aus der Anwendung aufgerufen, bevor eine weitere Aktion wartet.  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>Parameter  
 `nTimeout`  
 Anzahl der Millisekunden für die Verzögerung Nachricht aussteht.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion funktioniert in Verbindung mit [SetRetryReply](#setretryreply).  
  
##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply  
 Bestimmt, die aufrufende Anwendung-Aktion beim Empfang einer Antwort ausgelasteten aus einer Anwendung aufgerufen.  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nRetryReply`  
 Anzahl der Millisekunden zwischen den Wiederholungsversuchen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine aufgerufene Anwendung gibt an, dass es ausgelastet ist, kann die aufrufende Anwendung entscheiden, zu warten, bis der Server nicht mehr ausgelastet, um einen Wiederholungsversuch sofort oder nach einem angegebenen Intervall wiederholt werden. Sie haben auch die Möglichkeit, den Aufruf vollständig abzubrechen.  
  
 Der Aufrufer Antwort wird gesteuert, indem die Funktionen `SetRetryReply` und [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply` Bestimmt, wie lange die aufrufende Anwendung zwischen den Wiederholungsversuchen für einen bestimmten Aufruf warten soll. `SetMessagePendingDelay` Bestimmt, wie lange die aufrufende Anwendung auf eine Antwort vom Server wartet, bevor eine weitere Aktion ausgeführt.  
  
 In der Regel werden die Standardwerte sind zulässig und müssen nicht geändert werden. Das Framework versucht, den Aufruf jeder `nRetryReply` Millisekunden, bis der Aufruf durchläuft oder die Nachricht ausstehende Verzögerung ist abgelaufen. Der Wert 0 für `nRetryReply` eine sofortige Wiederholung und -1 gibt an, Abbruch des Aufrufs angibt.  
  
 Wenn die Nachricht ausstehende Verzögerung abgelaufen ist, das OLE "ausgelastet Dialogfeld" (finden Sie unter [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) wird angezeigt, sodass der Benutzer auswählen kann, auf "Abbrechen", oder wiederholen den Aufruf. Rufen Sie [EnableBusyDialog](#enablebusydialog) aktivieren oder deaktivieren das Dialogfeld zu öffnen.  
  
 Wenn eine Nachricht Tastatur- oder Maustastenzustand steht während eines Aufrufs und der Aufruf wurde überschritten (überschritten die Nachricht ausstehende Verzögerung), wird das Dialogfeld "nicht aktiv" angezeigt. Rufen Sie [EnableNotRespondingDialog](#enablenotrespondingdialog) aktivieren oder deaktivieren das Dialogfeld zu öffnen. Dieser Status Informationsquelle gibt normalerweise an, dass etwas schiefgelaufen und ist der Benutzer ungeduldig abrufen.  
  
 Wenn die Dialogfelder deaktiviert sind, werden die aktuelle "erneut versuchen, Antwort" immer für Aufrufe von ausgelasteten Anwendungen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
