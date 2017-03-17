---
title: Klasse COleMessageFilter | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- COleMessageFilter class
- OLE [C++], managing concurrency
- message filters [C++]
- OLE applications [C++], managing interactions
- OLE messages
- applications [OLE], managing interactions
- messages [C++], OLE
ms.assetid: b1fd1639-fac4-4fd0-bf17-15172deba13c
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d91ed300bb6cade5d804fe4a74dfe6cc2e4384fe
ms.lasthandoff: 02/24/2017

---
# <a name="colemessagefilter-class"></a>COleMessageFilter-Klasse
Verwaltet die Parallelität, die für die Interaktion von OLE-Anwendungen benötigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleMessageFilter : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleMessageFilter::COleMessageFilter](#colemessagefilter)|Erstellt ein `COleMessageFilter`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleMessageFilter::BeginBusyState](#beginbusystate)|Wird die Anwendung im Status "beschäftigt".|  
|[COleMessageFilter::EnableBusyDialog](#enablebusydialog)|Aktiviert und deaktiviert das Dialogfeld, das angezeigt wird, wenn eine aufgerufene Anwendung ausgelastet ist.|  
|[COleMessageFilter::EnableNotRespondingDialog](#enablenotrespondingdialog)|Aktiviert und deaktiviert das Dialogfeld wird angezeigt, wenn eine aufgerufene Anwendung nicht reagiert.|  
|[COleMessageFilter::EndBusyState](#endbusystate)|Beendet den Zustand der Anwendung ausgelastet.|  
|[COleMessageFilter::OnMessagePending](#onmessagepending)|Vom Framework zum Verarbeiten von Nachrichten aufgerufen, während ein OLE-Aufruf ausgeführt wird.|  
|[COleMessageFilter::Register](#register)|Den Nachrichtenfilter registriert die OLE-System-DLLs.|  
|[COleMessageFilter::Revoke](#revoke)|Hebt die Registrierung des Nachrichtenfilters die OLE-System-DLLs.|  
|[COleMessageFilter::SetBusyReply](#setbusyreply)|Bestimmt, die andere Anwendung Antwort auf einen OLE-Aufruf.|  
|[COleMessageFilter::SetMessagePendingDelay](#setmessagependingdelay)|Bestimmt, wie lange die Anwendung auf eine Antwort auf einen OLE-Aufruf wartet.|  
|[COleMessageFilter::SetRetryReply](#setretryreply)|Bestimmt die aufrufende Anwendung Antwort auf eine andere Anwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COleMessageFilter` -Klasse ist hilfreich, Server und-Container Anwendungen für visuelle Bearbeitung sowie OLE Automation-Programme. Für serveranwendungen, die aufgerufen werden, kann diese Klasse verwendet werden, um die Anwendung "ausgelastet", damit eingehende Anrufe von anderen Programmen Container abgebrochen oder später wiederholt werden. Diese Klasse kann auch verwendet werden, bestimmt die Aktion, die von einer aufrufenden Anwendung ausgeführt werden, wenn die aufgerufene Anwendung ausgelastet ist.  
  
 Meist wird für eine Server-Anwendung aufrufen, [BeginBusyState](#beginbusystate) und [EndBusyState](#endbusystate) Wenn wäre es gefährlich für ein Dokument oder ein anderes zugänglich OLE-Objekt zerstört werden. Diese Aufrufe [OnIdle](../../mfc/reference/cwinapp-class.md#onidle) während der Aktualisierung der Benutzeroberfläche.  
  
 In der Standardeinstellung ein `COleMessageFilter` Objekt beim Initialisieren der Anwendung zugewiesen wird. Es kann abgerufen werden, mit [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
 Dies ist eine erweiterte Klasse. Sie müssen nur selten direkt mit der sie arbeiten.  
  
 Weitere Informationen finden Sie im Artikel [Server: Implementieren eines Servers](../../mfc/servers-implementing-a-server.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleMessageFilter`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="beginbusystate"></a>COleMessageFilter::BeginBusyState  
 Rufen Sie diese Funktion, um den Status "beschäftigt" beginnen.  
  
```  
virtual void BeginBusyState();
```  
  
### <a name="remarks"></a>Hinweise  
 Funktioniert in Kombination mit [EndBusyState](#endbusystate) zum Steuern der Anwendung ausgelastet. Die Funktion [SetBusyReply](#setbusyreply) Applikationen aufrufen, wird die Anwendung Antworten bestimmt.  
  
 Die `BeginBusyState` und `EndBusyState` Aufrufe Inkrementieren und Dekrementieren, jeweils einen Zähler, der bestimmt, ob die Anwendung ausgelastet ist. Zum Beispiel zwei Aufrufe von `BeginBusyState` und durch einen Aufruf von `EndBusyState` dennoch in einem ausgelasteten Zustand. Ausgelasteten Status Abbrechen erforderlich ist, aufzurufen `EndBusyState` die gleiche Anzahl `BeginBusyState` aufgerufen wurde.  
  
 Standardmäßig trägt das Framework Status "beschäftigt" während der Verarbeitung im Leerlauf: durch erfolgt [OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Während die Anwendung verarbeitet **ON_COMMANDUPDATEUI** Benachrichtigungen, eingehende Anrufe werden nach Abschluss der Verarbeitung im Leerlauf später behandelt.  
  
##  <a name="colemessagefilter"></a>COleMessageFilter::COleMessageFilter  
 Erstellt ein `COleMessageFilter`-Objekt.  
  
```  
COleMessageFilter();
```  
  
##  <a name="enablebusydialog"></a>COleMessageFilter::EnableBusyDialog  
 Aktiviert und deaktiviert die ausgelastet Dialogfeld angezeigt wird, wenn die Verzögerung ausstehende Nachricht läuft ab (siehe [SetRetryReply](#setretryreply)) während eines Aufrufs OLE.  
  
```  
void EnableBusyDialog(BOOL bEnableBusy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableBusy*  
 Gibt an, ob das Dialogfeld "ausgelastet" aktiviert oder deaktiviert ist.  
  
##  <a name="enablenotrespondingdialog"></a>COleMessageFilter::EnableNotRespondingDialog  
 Aktiviert und deaktiviert das Dialogfeld "nicht reagiert", der angezeigt wird, wenn eine Tastatur oder Maus Meldung ausstehend ist bei einer OLE-Aufruf und der Aufruf wurde überschritten.  
  
```  
void EnableNotRespondingDialog(BOOL bEnableNotResponding = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bEnableNotResponding*  
 Gibt an, ob das Dialogfeld "nicht reagiert" aktiviert oder deaktiviert ist.  
  
##  <a name="endbusystate"></a>COleMessageFilter::EndBusyState  
 Rufen Sie diese Funktion, um den Status "beschäftigt" enden.  
  
```  
virtual void EndBusyState();
```  
  
### <a name="remarks"></a>Hinweise  
 Funktioniert in Kombination mit [BeginBusyState](#beginbusystate) zum Steuern der Anwendung ausgelastet. Die Funktion [SetBusyReply](#setbusyreply) Applikationen aufrufen, wird die Anwendung Antworten bestimmt.  
  
 Die `BeginBusyState` und `EndBusyState` Aufrufe Inkrementieren und Dekrementieren, jeweils einen Zähler, der bestimmt, ob die Anwendung ausgelastet ist. Zum Beispiel zwei Aufrufe von `BeginBusyState` und durch einen Aufruf von `EndBusyState` dennoch in einem ausgelasteten Zustand. Ausgelasteten Status Abbrechen erforderlich ist, aufzurufen `EndBusyState` die gleiche Anzahl `BeginBusyState` aufgerufen wurde.  
  
 Standardmäßig trägt das Framework Status "beschäftigt" während der Verarbeitung im Leerlauf: durch erfolgt [OnIdle](../../mfc/reference/cwinapp-class.md#onidle). Während die Anwendung verarbeitet `ON_UPDATE_COMMAND_UI` Benachrichtigungen, eingehende Anrufe werden nach Abschluss der Verarbeitung im Leerlauf behandelt.  
  
##  <a name="onmessagepending"></a>COleMessageFilter::OnMessagePending  
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
 Bei einem Aufruf abgeschlossen werden, während eine aufrufende Anwendung gewartet wird, ruft das Framework `OnMessagePending` mit einem Zeiger auf die ausstehende Nachricht. Standardmäßig sendet das Framework `WM_PAINT` Nachrichten, sodass aktualisiert während eines Aufrufs auftreten können, die einen längeren Zeitraum benötigt wird.  
  
 Registrieren Sie Ihre Nachrichtenfilter durch einen Aufruf von [registrieren](#register) , bevor es aktiviert werden kann.  
  
##  <a name="register"></a>COleMessageFilter::Register  
 Den Nachrichtenfilter registriert die OLE-System-DLLs.  
  
```  
BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Ein Meldungsfilter hat keine Auswirkung, es sei denn, sie für die System-DLLs registriert wurde. Initialisierungscode für Ihre Anwendung wird in der Regel Nachrichtenfilter für die Anwendung registriert. Alle anderen von der Anwendung registriert Nachrichtenfilter aufgehoben werden soll, bevor das Programm beendet, durch einen Aufruf von wird [Sperren](#revoke).  
  
 Das Framework Standardfilter Nachricht wird automatisch während der Initialisierung registriert und bei Beendigung gesperrt.  
  
##  <a name="revoke"></a>COleMessageFilter::Revoke  
 Widerruft eine vorherige Registrierung ausgeführt wird, durch einen Aufruf von [registrieren](#register).  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Meldungsfilter sollte aufgehoben werden, bevor das Programm beendet wird.  
  
 Der Standardfilter für die Nachricht, die erstellt und automatisch vom Framework registriert, wird ebenfalls automatisch gesperrt.  
  
##  <a name="setbusyreply"></a>COleMessageFilter::SetBusyReply  
 Diese Funktion legt die Anwendung "ausgelastet Antwort."  
  
```  
void SetBusyReply(SERVERCALL nBusyReply);
```  
  
### <a name="parameters"></a>Parameter  
 *nBusyReply*  
 Ein Wert aus der `SERVERCALL` -Enumeration, die in der Datei COMPOBJ definiert ist. H. Einer der folgenden Werte sind möglich:  
  
- **SERVERCALL_ISHANDLED** die Anwendung können Anrufe annehmen, aber bei der Verarbeitung eines bestimmten Aufrufs fehlschlagen.  
  
- **SERVERCALL_REJECTED** die Anwendung wahrscheinlich werden nie einen Aufruf zu verarbeiten.  
  
- **IOleMessageFilter.HandleIncomingCall** die Anwendung ist vorübergehend in einem Zustand in der sie einen Aufruf verarbeiten kann.  
  
### <a name="remarks"></a>Hinweise  
 Die [BeginBusyState](#beginbusystate) und [EndBusyState](#endbusystate) Funktionen steuern den Zustand der Anwendung ausgelastet.  
  
 Wenn eine Anwendung wurde mit einem Aufruf von ausgelasteten `BeginBusyState`, es reagiert auf Aufrufe von OLE-System-DLLs mit einem Wert, der durch die letzte Einstellung der `SetBusyReply`. Die aufrufende Anwendung verwendet diese ausgelastet Antwort, um welche Aktion zu bestimmen.  
  
 Die Antwort ausgelastet ist standardmäßig **IOleMessageFilter.HandleIncomingCall**. Diese Antwort führt dazu, dass die aufrufende Anwendung den Aufruf so bald wie möglich zu wiederholen.  
  
##  <a name="setmessagependingdelay"></a>COleMessageFilter::SetMessagePendingDelay  
 Bestimmt, wie lange die aufrufende Anwendung auf eine Antwort von der Anwendung aufgerufen, bevor eine weitere Aktion wartet.  
  
```  
void SetMessagePendingDelay(DWORD nTimeout = 5000);
```  
  
### <a name="parameters"></a>Parameter  
 `nTimeout`  
 Anzahl der Millisekunden für die Verzögerung Nachricht steht.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion arbeitet gemeinsam mit [SetRetryReply](#setretryreply).  
  
##  <a name="setretryreply"></a>COleMessageFilter::SetRetryReply  
 Bestimmt, die aufrufende Anwendung Aktion beim Empfang einer Antwort ausgelasteten aus einer Anwendung aufgerufen.  
  
```  
void SetRetryReply(DWORD nRetryReply = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nRetryReply`  
 Anzahl der Millisekunden zwischen den Wiederholungsversuchen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine sogenannte anwendungsbasierte gibt an, dass sie beschäftigt ist, kann die aufrufende Anwendung entscheiden, warten, bis der Server nicht mehr ausgelastet, um sofort zu wiederholen oder nach einem angegebenen Intervall wiederholt wird. Sie können auch den Aufruf abgebrochen.  
  
 Der Aufrufer Antwort wird gesteuert, indem die Funktionen `SetRetryReply` und [SetMessagePendingDelay](#setmessagependingdelay). `SetRetryReply`Bestimmt, wie lange die aufrufende Anwendung zwischen den Wiederholungsversuchen für einen bestimmten Aufruf warten soll. `SetMessagePendingDelay`Bestimmt, wie lange die aufrufende Anwendung auf eine Antwort vom Server wartet, bevor eine weitere Aktion ausgeführt.  
  
 In der Regel die Standardwerte sind zulässig und müssen nicht geändert werden. Das Framework versucht, den Aufruf alle `nRetryReply` Millisekunden, bis der Aufruf über erfolgt oder die Nachricht ausstehende Verzögerung ist abgelaufen. Der Wert 0 für `nRetryReply` gibt eine sofortige Wiederholung und – 1 gibt Abbruch des Anrufs.  
  
 Wenn die Nachricht ausstehende Verzögerung abgelaufen ist, das OLE "ausgelastet Dialogfeld" (finden Sie unter [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)) wird angezeigt, damit der Benutzer den Vorgang abbrechen oder wiederholen den Aufruf auswählen kann. Rufen Sie [EnableBusyDialog](#enablebusydialog) aktivieren oder deaktivieren das Dialogfeld zu öffnen.  
  
 Wenn eine Tastatur oder Maus Nachricht steht während eines Aufrufs und der Aufruf wurde überschritten (überschritten die Nachricht ausstehende Verzögerung), wird das Dialogfeld "nicht aktiv" angezeigt. Rufen Sie [EnableNotRespondingDialog](#enablenotrespondingdialog) aktivieren oder deaktivieren das Dialogfeld zu öffnen. Dieser Status Informationsquelle gibt normalerweise an, dass etwas schiefgelaufen ist der Benutzer ungeduldig abrufen.  
  
 Wenn die Dialogfelder deaktiviert sind, werden die aktuellen "erneut versuchen Antwort" immer für Aufrufe von ausgelasteten Applications verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)

