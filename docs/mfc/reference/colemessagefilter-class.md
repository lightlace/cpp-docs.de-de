---
title: COleMessageFilter-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 585044a5da8ca3ce8b2650801558b19bf1d5ef59
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427796"
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
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Wird die Anwendung im Status "beschäftigt" an.|
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Aktiviert und deaktiviert das Dialogfeld wird angezeigt, wenn eine aufgerufene Anwendung ausgelastet ist.|
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Aktiviert und deaktiviert das Dialogfeld wird angezeigt, wenn eine aufgerufene Anwendung nicht reagiert.|
|[COleMessageFilter::EndBusyState](#endbusystate)|Beendet den Zustand der Anwendung beschäftigt.|
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Wird vom Framework zum Verarbeiten von Nachrichten aufgerufen, während ein OLE-Aufruf ausgeführt wird.|
|[COleMessageFilter::Register](#register)|Den Nachrichtenfilter registriert die OLE-System-DLLs.|
|[COleMessageFilter::Revoke](#revoke)|Hebt die Registrierung des Nachrichtenfilters die OLE-System-DLLs.|
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Bestimmt, die andere Anwendung die Antwort zu einem OLE-Aufruf.|
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Bestimmt, wie lange die Anwendung auf eine Antwort auf eine OLE-Aufruf wartet.|
|[COleMessageFilter::SetRetryReply](#setretryreply)|Bestimmt, die aufrufende Anwendung die Antwort auf eine ausgelastete Anwendung.|

## <a name="remarks"></a>Hinweise

Die `COleMessageFilter` Klasse eignet sich für Server und-Container Anwendungen für visuelle Bearbeitung als auch Anwendungen von OLE-Automatisierung. Für serveranwendungen, die aufgerufen werden, kann diese Klasse verwendet werden, um die Anwendung "beschäftigt" machen, sodass eingehender Aufrufe von anderen Anwendungen mit Containern abgebrochen oder später erneut ausgeführt werden. Diese Klasse kann auch verwendet werden, um zu bestimmen, die Aktion, die von einer aufrufenden Anwendung ausgeführt werden, wenn die aufgerufene Anwendung ausgelastet ist.

Allgemeine Verwendung ist für eine Serveranwendung aufzurufende [BeginBusyState](#beginbusystate) und [EndBusyState](#endbusystate) Wenn wäre gefährlich für ein Dokument oder ein anderes zugegriffen werden OLE-Objekt zerstört werden soll. Diese Aufrufe [OnIdle](../../mfc/reference/cwinapp-class.md#onidle) während eines Updates der Benutzeroberfläche.

Standardmäßig eine `COleMessageFilter` Objekt zugeordnet ist, wenn die Anwendung initialisiert wird. Es kann abgerufen werden, mit [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

Hierbei handelt es sich um eine erweiterte Klasse; Sie müssen nur selten direkt zu arbeiten.

Weitere Informationen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleMessageFilter`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="beginbusystate"></a>  COleMessageFilter::BeginBusyState

Mit dieser Funktion können ausgelasteten Zustand beginnt.

```
virtual void BeginBusyState();
```

### <a name="remarks"></a>Hinweise

Es funktioniert in Verbindung mit [EndBusyState](#endbusystate) ausgelasteter Zustand der Anwendung steuern. Die Funktion [SetBusyReply](#setbusyreply) bestimmt die Antwort von der Anwendung an aufrufende Anwendungen aus, wenn es ausgelastet ist.

Die `BeginBusyState` und `EndBusyState` Aufrufe Inkrementieren und Dekrementieren, bzw. einen Indikator, der bestimmt, ob die Anwendung ausgelastet ist. Zum Beispiel zwei Aufrufe von `BeginBusyState` und einen Aufruf von `EndBusyState` ausgelasteter Zustand bleibt. Ausgelasteten Zustand Abbrechen, es notwendig ist, `EndBusyState` die gleiche Anzahl an, wie oft `BeginBusyState` aufgerufen wurde.

Standardmäßig gibt das Framework Status "beschäftigt" während der leerlaufverarbeitung, die vom ausgeführt wird [OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Während die Anwendung ON_COMMANDUPDATEUI Benachrichtigungen verarbeitet, werden eingehende Anrufe später behandelt, nachdem leerlaufverarbeitung abgeschlossen ist.

##  <a name="colemessagefilter"></a>  COleMessageFilter::COleMessageFilter

Erstellt ein `COleMessageFilter`-Objekt.

```
COleMessageFilter();
```

##  <a name="enablebusydialog"></a>  COleMessageFilter::EnableBusyDialog

Aktiviert und deaktiviert die ausgelastet das Dialogfeld wird angezeigt, wenn die Verzögerung ausstehende Nachricht abläuft (finden Sie unter [SetRetryReply](#setretryreply)) während einem OLE-Aufruf.

```
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnableBusy*<br/>
Gibt an, ob das Dialogfeld für die "beschäftigt" aktiviert oder deaktiviert ist.

##  <a name="enablenotrespondingdialog"></a>  COleMessageFilter::EnableNotRespondingDialog

Aktiviert und deaktiviert das Dialogfeld "nicht reagiert", die angezeigt wird, wenn eine Nachricht Tastatur oder Maus aussteht während eines OLE-Aufruf und der Aufruf wurde überschritten.

```
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnableNotResponding*<br/>
Gibt an, ob das Dialogfeld "nicht reagiert" aktiviert oder deaktiviert ist.

##  <a name="endbusystate"></a>  COleMessageFilter::EndBusyState

Mit dieser Funktion können ausgelasteten Zustand enden.

```
virtual void EndBusyState();
```

### <a name="remarks"></a>Hinweise

Es funktioniert in Verbindung mit [BeginBusyState](#beginbusystate) ausgelasteter Zustand der Anwendung steuern. Die Funktion [SetBusyReply](#setbusyreply) bestimmt die Antwort von der Anwendung an aufrufende Anwendungen aus, wenn es ausgelastet ist.

Die `BeginBusyState` und `EndBusyState` Aufrufe Inkrementieren und Dekrementieren, bzw. einen Indikator, der bestimmt, ob die Anwendung ausgelastet ist. Zum Beispiel zwei Aufrufe von `BeginBusyState` und einen Aufruf von `EndBusyState` ausgelasteter Zustand bleibt. Ausgelasteten Zustand Abbrechen, es notwendig ist, `EndBusyState` die gleiche Anzahl an, wie oft `BeginBusyState` aufgerufen wurde.

Standardmäßig gibt das Framework Status "beschäftigt" während der leerlaufverarbeitung, die vom ausgeführt wird [OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Während die Anwendung ON_UPDATE_COMMAND_UI Benachrichtigungen verarbeitet, werden eingehende Anrufe behandelt, nachdem leerlaufverarbeitung abgeschlossen ist.

##  <a name="onmessagepending"></a>  COleMessageFilter::OnMessagePending

Wird vom Framework zum Verarbeiten von Nachrichten aufgerufen, während ein OLE-Aufruf ausgeführt wird.

```
virtual BOOL OnMessagePending(const MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Zeiger auf die ausstehende Nachricht.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Wenn eine aufrufende Anwendung für einen Aufruf abgeschlossen werden, wartet, das Framework ruft `OnMessagePending` mit einem Zeiger auf die ausstehende Nachricht. Standardmäßig sendet das Framework WM_PAINT-Meldungen an, sodass aktualisiert während eines Aufrufs auftreten können, die sehr lange dauert.

Sie müssen Ihre Nachrichtenfilter registrieren, durch einen Aufruf von [registrieren](#register) bevor es aktiv werden kann.

##  <a name="register"></a>  COleMessageFilter::Register

Den Nachrichtenfilter registriert die OLE-System-DLLs.

```
BOOL Register();
```

### <a name="return-value"></a>Rückgabewert

Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Ein Nachrichtenfilter hat keine Auswirkungen, es sei denn, sie für die System-DLLs registriert wurde. In der Regel wird Code für die Initialisierung von Ihrer Anwendung Nachrichtenfilter der Anwendung registriert. Alle anderen von der Anwendung registriert Nachrichtenfilter aufgehoben werden soll, bevor das Programm beendet, durch einen Aufruf von wird [widerrufen](#revoke).

Die Framework Standard-Nachrichtenfilter wird automatisch während der Initialisierung registriert und bei Beendigung des aufgehoben.

##  <a name="revoke"></a>  COleMessageFilter::Revoke

Widerruft eine vorherige Registrierung durchgeführt, die durch einen Aufruf von [registrieren](#register).

```
void Revoke();
```

### <a name="remarks"></a>Hinweise

Ein Nachrichtenfilter muss aufgehoben werden, bevor das Programm beendet wird.

Der Standardfilter für die Nachricht, die erstellt und automatisch vom Framework registriert, wird außerdem automatisch gesperrt.

##  <a name="setbusyreply"></a>  COleMessageFilter::SetBusyReply

Diese Funktion legt fest, der Anwendung "ausgelastet Antworten."

```
void SetBusyReply(SERVERCALL nBusyReply);
```

### <a name="parameters"></a>Parameter

*nBusyReply*<br/>
Ein Wert aus der `SERVERCALL` -Enumeration, die in der Datei COMPOBJ definiert ist. H. Sie können eine der folgenden Werte haben:

- SERVERCALL_ISHANDLED die Anwendung kann Aufrufe akzeptieren, aber es kann Fehler verursachen, bei der Verarbeitung eines bestimmten Aufrufs.

- SERVERCALL_REJECTED die Anwendung werden wahrscheinlich nie einen Aufruf verarbeitet.

- IOleMessageFilter.HandleIncomingCall der Anwendung ist vorübergehend in einem Zustand, in dem einen Aufruf nicht verarbeitet werden kann.

### <a name="remarks"></a>Hinweise

Die [BeginBusyState](#beginbusystate) und [EndBusyState](#endbusystate) Funktionen steuern den Zustand der Anwendung beschäftigt.

Wenn eine Anwendung durchgeführt wurde mit einem Aufruf von `BeginBusyState`, sie reagiert auf Aufrufe von der OLE-System-DLLs mit einem Wert, der bestimmt, indem die letzte Einstellung des `SetBusyReply`. Die aufrufende Anwendung verwendet diese Antwort ausgelastet, um zu bestimmen, welche Aktionen durchzuführen sind.

Standardmäßig ist die Antwort ausgelastet IOleMessageFilter.HandleIncomingCall. Diese Antwort führt dazu, dass die aufrufende Anwendung den Aufruf so bald wie möglich zu wiederholen.

##  <a name="setmessagependingdelay"></a>  COleMessageFilter::SetMessagePendingDelay

Bestimmt, wie lange die aufrufende Anwendung auf eine Antwort von der aufgerufenen Anwendung, bevor weitere Aktionen wartet.

```
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```

### <a name="parameters"></a>Parameter

*%ntimeout*<br/>
Anzahl der Millisekunden, für die Nachricht ausstehende Verzögerung.

### <a name="remarks"></a>Hinweise

Diese Funktion kann zusammen mit [SetRetryReply](#setretryreply).

##  <a name="setretryreply"></a>  COleMessageFilter::SetRetryReply

Bestimmt, die aufrufende Anwendung Aktion beim Empfang einer Antwort ausgelasteten aus einer Anwendung aufgerufen.

```
void SetRetryReply(DWORD nRetryReply = 0);
```

### <a name="parameters"></a>Parameter

*nRetryReply*<br/>
Anzahl der Millisekunden zwischen den Wiederholungen.

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung namens gibt an, dass sie beschäftigt ist, kann die aufrufende Anwendung entscheiden, warten, bis der Server nicht mehr ausgelastet, um sofort zu wiederholen oder nach einem angegebenen Intervall wiederholt wird. Sie haben auch die Möglichkeit, den Aufruf abgebrochen.

Des Aufrufers Antwort wird gesteuert, von den Funktionen `SetRetryReply` und [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply` Bestimmt, wie lange die aufrufende Anwendung zwischen den Wiederholungsversuchen für einen bestimmten Aufruf warten soll. `SetMessagePendingDelay` Bestimmt, wie lange die aufrufende Anwendung auf eine Antwort vom Server wartet, bevor Sie weitere Aktionen durchführen.

In der Regel werden die Standardwerte zulässig sind und müssen nicht geändert werden. Das Framework wiederholt den Aufruf alle *nRetryReply* Millisekunden, bis der Aufruf durchläuft oder die Nachricht ausstehende Verzögerung ist abgelaufen. Der Wert 0 für *nRetryReply* gibt an, eine sofortige Wiederholung und -1 gibt an, die Abbruch des Aufrufs.

Wenn die Verzögerung ausstehende Nachricht abgelaufen ist, das OLE "ausgelastet Dialogfeld" (finden Sie unter [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) wird angezeigt, damit der Benutzer auswählen kann, Abbrechen oder wiederholen den Aufruf. Rufen Sie [EnableBusyDialog](#enablebusydialog) aktivieren oder deaktivieren das Dialogfeld zu öffnen.

Wenn eine Nachricht Tastatur oder Maus steht bei einem Aufruf und der Aufruf wurde überschritten (überschritten die Nachricht ausstehende Verzögerung), wird das Dialogfeld "nicht aktiv" angezeigt. Rufen Sie [EnableNotRespondingDialog](#enablenotrespondingdialog) aktivieren oder deaktivieren das Dialogfeld zu öffnen. Dieser Vergleich zwischen Status gibt normalerweise an, dass etwas falsch gelaufen ist und der Benutzer ungeduldig erhält.

Wenn die Dialogfelder deaktiviert sind, werden die aktuelle "erneut versuchen Antwort" immer für Aufrufe von ausgelasteten Anwendungen verwendet.

## <a name="see-also"></a>Siehe auch

[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
