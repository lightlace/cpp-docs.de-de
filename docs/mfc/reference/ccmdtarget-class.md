---
title: CCmdTarget-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCmdTarget
- AFXWIN/CCmdTarget
- AFXWIN/CCmdTarget::CCmdTarget
- AFXWIN/CCmdTarget::BeginWaitCursor
- AFXWIN/CCmdTarget::DoOleVerb
- AFXWIN/CCmdTarget::EnableAutomation
- AFXWIN/CCmdTarget::EnableConnections
- AFXWIN/CCmdTarget::EnableTypeLib
- AFXWIN/CCmdTarget::EndWaitCursor
- AFXWIN/CCmdTarget::EnumOleVerbs
- AFXWIN/CCmdTarget::FromIDispatch
- AFXWIN/CCmdTarget::GetDispatchIID
- AFXWIN/CCmdTarget::GetIDispatch
- AFXWIN/CCmdTarget::GetTypeInfoCount
- AFXWIN/CCmdTarget::GetTypeInfoOfGuid
- AFXWIN/CCmdTarget::GetTypeLib
- AFXWIN/CCmdTarget::GetTypeLibCache
- AFXWIN/CCmdTarget::IsInvokeAllowed
- AFXWIN/CCmdTarget::IsResultExpected
- AFXWIN/CCmdTarget::OnCmdMsg
- AFXWIN/CCmdTarget::OnFinalRelease
- AFXWIN/CCmdTarget::RestoreWaitCursor
helpviewer_keywords:
- CCmdTarget [MFC], CCmdTarget
- CCmdTarget [MFC], BeginWaitCursor
- CCmdTarget [MFC], DoOleVerb
- CCmdTarget [MFC], EnableAutomation
- CCmdTarget [MFC], EnableConnections
- CCmdTarget [MFC], EnableTypeLib
- CCmdTarget [MFC], EndWaitCursor
- CCmdTarget [MFC], EnumOleVerbs
- CCmdTarget [MFC], FromIDispatch
- CCmdTarget [MFC], GetDispatchIID
- CCmdTarget [MFC], GetIDispatch
- CCmdTarget [MFC], GetTypeInfoCount
- CCmdTarget [MFC], GetTypeInfoOfGuid
- CCmdTarget [MFC], GetTypeLib
- CCmdTarget [MFC], GetTypeLibCache
- CCmdTarget [MFC], IsInvokeAllowed
- CCmdTarget [MFC], IsResultExpected
- CCmdTarget [MFC], OnCmdMsg
- CCmdTarget [MFC], OnFinalRelease
- CCmdTarget [MFC], RestoreWaitCursor
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
ms.openlocfilehash: 4d69b0b262ec53460d655a19cd421051f7177636
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498854"
---
# <a name="ccmdtarget-class"></a>CCmdTarget-Klasse

Die Basisklasse für die meldungszuordnungsarchitektur der Microsoft Foundation Class-Bibliothek.

## <a name="syntax"></a>Syntax

```
class CCmdTarget : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCmdTarget::CCmdTarget](#ccmdtarget)|Erstellt ein `CCmdTarget`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|Zeigt den Cursor als ein Sanduhrcursor.|
|[CCmdTarget::DoOleVerb](#dooleverb)|Bewirkt, dass eine Aktion angegeben, die von einem OLE-Verb ausgeführt werden.|
|[CCmdTarget::EnableAutomation](#enableautomation)|Ermöglicht das OLE-Automatisierung für die `CCmdTarget` Objekt.|
|[CCmdTarget::EnableConnections](#enableconnections)|Ermöglicht das Auslösen von Ereignissen über die Verbindungspunkte an.|
|[CCmdTarget::EnableTypeLib](#enabletypelib)|Ermöglicht die Typbibliothek des Objekts.|
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|Gibt zurück, auf den vorherigen Cursor.|
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|Listet die auf ein Objekt des OLE-Verben.|
|[CCmdTarget::FromIDispatch](#fromidispatch)|Gibt einen Zeiger auf die `CCmdTarget` zugeordnete Objekt der `IDispatch` Zeiger.|
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|Ruft die primäre Dispatch-Schnittstellen-ID.|
|[CCmdTarget::GetIDispatch](#getidispatch)|Gibt einen Zeiger auf die `IDispatch` zugeordnete Objekt der `CCmdTarget` Objekt.|
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|Ruft die Anzahl der Schnittstellen mit Typinformationen, die ein Objekt bereitstellt.|
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|Ruft die Beschreibung, die der angegebenen GUID entspricht.|
|[CCmdTarget::GetTypeLib](#gettypelib)|Ruft einen Zeiger auf eine Typbibliothek.|
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|Ruft den Typ-Bibliothek-Cache ab.|
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|Ermöglicht die Automatisierung-Methodenaufruf.|
|[CCmdTarget::IsResultExpected](#isresultexpected)|Gibt zurück, die ungleich NULL, wenn ein Automatisierungsfunktion sollte es sich um einen Wert zurückgeben.|
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|Leitet und Command-Meldungen sendet.|
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|Löscht nach der Veröffentlichung des letzten OLE-Verweis.|
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|Stellt die Sanduhrcursor.|

## <a name="remarks"></a>Hinweise

Eine meldungszuordnung leitet Befehle oder Nachrichten, die Memberfunktionen, die Sie schreiben, um sie zu behandeln. (Ein Befehl ist eine Nachricht aus der ein Menüelement, die Schaltfläche "Befehl" oder die Zugriffstaste.)

Wichtige Framework-Klassen abgeleitet `CCmdTarget` enthalten [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), und [ CFrameWnd](../../mfc/reference/cframewnd-class.md). Wenn Sie beabsichtigen eine neue Klasse, um Nachrichten zu verarbeiten, leiten Sie die Klasse von einer der folgenden `CCmdTarget`-abgeleiteten Klassen. Sie werden nur selten leiten eine Klasse von `CCmdTarget` direkt.

Eine Übersicht über Befehlsziele und `OnCmdMsg` routing finden Sie [Befehlsziele](../../mfc/command-targets.md), [Befehlsrouting](../../mfc/command-routing.md), und [Zuordnen von Meldungen](../../mfc/mapping-messages.md).

`CCmdTarget` enthält die Member-Funktionen, die die Anzeige von ein Sanduhrcursor behandelt. Sanduhrcursor angezeigt, wenn Sie erwarten, dass einen Befehl eine merkliche Zeitintervall ausgeführt wird.

Dispatchzuordnungen, meldungszuordnungen ähnelt, werden verwendet, um OLE-Automatisierung verfügbar zu machen `IDispatch` Funktionalität. Von dieser Schnittstelle verfügbar macht, können andere Anwendungen (z. B. Visual Basic) in Ihrer Anwendung aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CCmdTarget`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="beginwaitcursor"></a>  CCmdTarget::BeginWaitCursor

Rufen Sie diese Funktion, um den Cursor als Sanduhr angezeigt, wenn Sie erwarten, dass einen Befehl eine merkliche Zeitintervall ausgeführt wird.

```
void BeginWaitCursor();
```

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Funktion, um dem Benutzer angezeigt, dass sie beschäftigt ist, z. B. wenn ist eine `CDocument` Objekt lädt oder speichert selbst in einer Datei.

Die Aktionen der `BeginWaitCursor` sind nicht immer effektiv außerhalb eines einzelnen meldungshandlers wie andere Aktionen, z. B. `OnSetCursor` behandeln, können Sie den Cursor ändern.

Rufen Sie `EndWaitCursor` zum Wiederherstellen des vorherigen Cursors.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="ccmdtarget"></a>  CCmdTarget::CCmdTarget

Erstellt ein `CCmdTarget`-Objekt.

```
CCmdTarget();
```

##  <a name="dooleverb"></a>  CCmdTarget::DoOleVerb

Bewirkt, dass eine Aktion angegeben, die von einem OLE-Verb ausgeführt werden.

```
BOOL DoOleVerb(
    LONG iVerb,
    LPMSG lpMsg,
    HWND hWndParent,
    LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*iVerb*<br/>
Numerischer Bezeichner des Verbs.

*lpMsg*<br/>
Zeiger auf die [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958) Struktur, die Beschreibung des Ereignisses (z. B. einem Doppelklick), die das Verb aufgerufen hat.

*hWndParent*<br/>
Das Handle des Dokumentfensters, das das Objekt enthält.

*lpRect*<br/>
Zeiger auf die [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur mit den Koordinaten, in Pixel, die ein Objekt definieren, die das Begrenzungsrechteck in *HwndParent*.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist im Grunde eine Implementierung von [IOleObject](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-doverb). Die möglichen Aktionen werden durch den aufgezählt [CCmdTarget::EnumOleVerbs](#enumoleverbs).

##  <a name="enableautomation"></a>  CCmdTarget::EnableAutomation

Rufen Sie diese Funktion zum Aktivieren der OLE-Automatisierung für ein Objekt.

```
void EnableAutomation();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird in der Regel aus dem Konstruktor des Objekts aufgerufen und sollte nur aufgerufen werden, wenn eine Dispatchzuordnung für die Klasse deklariert wurde. Weitere Informationen zur Automatisierung finden Sie in den Artikeln [Automatisierungsclients](../../mfc/automation-clients.md) und [Automatisierungsserver](../../mfc/automation-servers.md).

##  <a name="enableconnections"></a>  CCmdTarget::EnableConnections

Ermöglicht das Auslösen von Ereignissen über die Verbindungspunkte an.

```
void EnableConnections();
```

### <a name="remarks"></a>Hinweise

Um Verbindungspunkte zu aktivieren, rufen Sie diese Memberfunktion im Konstruktor einer abgeleiteten Klasse ein.

##  <a name="enabletypelib"></a>  CCmdTarget::EnableTypeLib

Ermöglicht die Typbibliothek des Objekts.

```
void EnableTypeLib();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion im Konstruktor der Ihre `CCmdTarget`-abgeleitetes Objekt aus, wenn diese Typinformationen bereitstellt.

##  <a name="endwaitcursor"></a>  CCmdTarget::EndWaitCursor

Nachdem Sie aufgerufen haben, rufen Sie diese Funktion die `BeginWaitCursor` Memberfunktion versucht, aus der Sanduhrcursor an den vorherigen Cursor zurückgegeben.

```
void EndWaitCursor();
```

### <a name="remarks"></a>Hinweise

Das Framework ruft auch diese Memberfunktion auf, nachdem Sanduhrcursor aufgerufen wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

##  <a name="enumoleverbs"></a>  CCmdTarget::EnumOleVerbs

Listet die auf ein Objekt des OLE-Verben.

```
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```

### <a name="parameters"></a>Parameter

*ppenumOleVerb*<br/>
Ein Zeiger auf einen Zeiger auf ein [IEnumOLEVERB](/windows/desktop/api/oleidl/nn-oleidl-ienumoleverb) Schnittstelle.

### <a name="return-value"></a>Rückgabewert

True, wenn das Objekt mindestens ein OLE-Verb unterstützt (in diesem Fall \* *PpenumOleVerb* verweist auf eine `IEnumOLEVERB` Enumerator-Schnittstelle), andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Memberfunktion ist im Grunde eine Implementierung von [IOleObject:: EnumVerbs](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-enumverbs).

##  <a name="fromidispatch"></a>  CCmdTarget::FromIDispatch

Mit dieser Funktion wird zum Zuordnen einer `IDispatch` -Zeiger ist, Empfangen von Automation-Memberfunktionen einer Klasse, in der `CCmdTarget` Objekt, das die Schnittstellen implementiert die `IDispatch` Objekt.

```
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```

### <a name="parameters"></a>Parameter

*lpDispatch*<br/>
Ein Zeiger auf ein `IDispatch` -Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `CCmdTarget` zugeordnete Objekt *LpDispatch*. Diese Funktion gibt NULL zurück, wenn die `IDispatch` Objekt wurde nicht erkannt, als eine Microsoft Foundation Class `IDispatch` Objekt.

### <a name="remarks"></a>Hinweise

Das Ergebnis dieser Funktion ist die Umkehrung von einen Aufruf der Memberfunktion `GetIDispatch`.

##  <a name="getdispatchiid"></a>  CCmdTarget::GetDispatchIID

Ruft die primäre Dispatch-Schnittstellen-ID.

```
virtual BOOL GetDispatchIID(IID* pIID);
```

### <a name="parameters"></a>Parameter

*pIID*<br/>
Ein Zeiger auf eine Schnittstellen-ID (eine [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931)).

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls "false". Im Erfolgsfall \* *pIID* festgelegt ist, um die primäre Dispatch-Schnittstellen-ID.

### <a name="remarks"></a>Hinweise

Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht überschrieben, `GetDispatchIID` gibt FALSE zurück). Finden Sie unter [COleControl](../../mfc/reference/colecontrol-class.md).

##  <a name="getidispatch"></a>  CCmdTarget::GetIDispatch

Rufen Sie diese Memberfunktion zum Abrufen der `IDispatch` Zeiger ein Automatisierungsmethode zurückgibt, dass entweder ein `IDispatch` Zeiger oder übernimmt eine `IDispatch` Zeiger als Verweis.

```
LPDISPATCH GetIDispatch(BOOL bAddRef);
```

### <a name="parameters"></a>Parameter

*bAddRef*<br/>
Gibt an, ob für das Objekt der Verweiszähler inkrementiert werden soll.

### <a name="return-value"></a>Rückgabewert

Die `IDispatch` Zeiger, die dem Objekt zugeordnet.

### <a name="remarks"></a>Hinweise

Um Objekte für diesen Aufruf `EnableAutomation` in ihren Konstruktoren, stellt sie Automation aktiviert ist, gibt diese Funktion einen Zeiger der Foundation Class-Implementierung von `IDispatch` , wird von Clients verwendet, die für die Kommunikation über die `IDispatch` Schnittstelle. Ein Verweis auf den Zeiger, durch das Aufrufen dieser Funktion wird automatisch hinzugefügt werden, daher es nicht notwendig ist, einen Aufruf an [IUnknown:: AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref).

##  <a name="gettypeinfocount"></a>  CCmdTarget::GetTypeInfoCount

Ruft die Anzahl der Schnittstellen mit Typinformationen, die ein Objekt bereitstellt.

```
virtual UINT GetTypeInfoCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Schnittstellen mit Typinformationen.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion im Grunde implementiert [IDispatch:: GetTypeInfoCount](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-gettypeinfocount).

Abgeleitete Klassen überschreiben, sollte dieser Funktion können Sie die Anzahl von Schnittstellen mit Typinformationen bereitgestellt (0 oder 1) zurückgegeben. Wenn Sie nicht überschrieben, `GetTypeInfoCount` gibt 0 zurück. Um zu überschreiben, verwenden die [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) Makro, das implementiert auch `GetTypeLib` und `GetTypeLibCache`.

##  <a name="gettypeinfoofguid"></a>  CCmdTarget::GetTypeInfoOfGuid

Ruft die Beschreibung, die der angegebenen GUID entspricht.

```
HRESULT GetTypeInfoOfGuid(
    LCID lcid,
    const GUID& guid,
    LPTYPEINFO* ppTypeInfo);
```

### <a name="parameters"></a>Parameter

*lcid*<br/>
Ein Gebietsschemabezeichner ( `LCID`).

*GUID*<br/>
Die [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) der typenbeschreibung.

*ppTypeInfo*<br/>
Zeiger auf einen Zeiger auf die `ITypeInfo` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT, der angibt, den Erfolg oder Fehler des Aufrufs. Im Erfolgsfall \* *PpTypeInfo* verweist auf die Schnittstelle des Typs Informationen.

##  <a name="gettypelib"></a>  CCmdTarget::GetTypeLib

Ruft einen Zeiger auf eine Typbibliothek.

```
virtual HRESULT GetTypeLib(
    LCID lcid,
    LPTYPELIB* ppTypeLib);
```

### <a name="parameters"></a>Parameter

*lcid*<br/>
Ein Gebietsschemabezeichner (LCID).

*ppTypeLib*<br/>
Ein Zeiger auf einen Zeiger auf die `ITypeLib` Schnittstelle.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT, der angibt, den Erfolg oder Fehler des Aufrufs. Im Erfolgsfall \* *PpTypeLib* verweist auf die Typ-Library-Schnittstelle.

### <a name="remarks"></a>Hinweise

Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht überschrieben, `GetTypeLib` TYPE_E_CANTLOADLIBRARY zurückgibt). Verwenden der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) Makro, das implementiert auch `GetTypeInfoCount` und `GetTypeLibCache`.

##  <a name="gettypelibcache"></a>  CCmdTarget::GetTypeLibCache

Ruft den Typ-Bibliothek-Cache ab.

```
virtual CTypeLibCache* GetTypeLibCache();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CTypeLibCache` -Objekt.

### <a name="remarks"></a>Hinweise

Abgeleitete Klassen müssen diese Memberfunktion überschreiben (wenn nicht überschrieben, `GetTypeLibCache` gibt NULL zurück). Verwenden der [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) Makro, das implementiert auch `GetTypeInfoCount` und `GetTypeLib`.

##  <a name="isinvokeallowed"></a>  CCmdTarget::IsInvokeAllowed

Diese Funktion wird aufgerufen, durch die Implementierung von MFC `IDispatch::Invoke` bestimmen, ob eine angegebene Automatisierungsmethode (identifizierte *Dispid*) aufgerufen werden kann.

```
virtual BOOL IsInvokeAllowed(DISPID dispid);
```

### <a name="parameters"></a>Parameter

*DISPID*<br/>
Ein Verteiler-ID.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode aufgerufen, andernfalls "false" sein kann.

### <a name="remarks"></a>Hinweise

Wenn `IsInvokeAllowed` gibt TRUE zurück, `Invoke` geht zum Aufrufen der Methode; andernfalls `Invoke` fehl und gibt die E_UNEXPECTED zurück.

Abgeleitete Klassen können Überschreiben dieser Funktion können Sie die entsprechenden Werte zurück (wenn nicht überschrieben, `IsInvokeAllowed` gibt "true"). Sehen Sie sich vor allem [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed).

##  <a name="isresultexpected"></a>  CCmdTarget::IsResultExpected

Verwendung `IsResultExpected` zu ermitteln, ob ein Client einen Rückgabewert von seinem Aufruf an eine Automatisierungsfunktion erwartet.

```
BOOL IsResultExpected();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn eine Automatisierungsfunktion einen Wert zurückgeben sollte; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die OLE-Schnittstelle stellt Informationen zu MFC gibt an, ob der Client ist verwenden oder ignorieren das Ergebnis eines Funktionsaufrufs bereit und MFC verwendet diese Informationen wiederum das Ergebnis eines Aufrufs von bestimmen `IsResultExpected`. Produktion eines Rückgabewerts ist Time - oder ressourcenintensiv, können Sie die Effizienz erhöhen, durch Aufrufen dieser Funktion vor dem Berechnen des zurückgegeben Wert.

Diese Funktion gibt 0 zurück, nur einmal, damit Sie gültige Rückgabe von Werten aus anderen Automatisierungsfunktionen erhalten werden, wenn Sie sie aus der Automatisierungsfunktion Aufrufen des Clients aufgerufen hat.

`IsResultExpected` Gibt einen Wert ungleich NULL zurück, wenn aufgerufen, wenn ein Automation-Funktionsaufruf nicht ausgeführt wird.

##  <a name="oncmdmsg"></a>  CCmdTarget::OnCmdMsg

Wird aufgerufen, durch das Framework um befehlsmeldungen weiterzuleiten und zu und zum Behandeln der Aktualisierung der Benutzeroberfläche von Befehlsobjekten.

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
Enthält Befehls-ID.

*nCode*<br/>
Identifiziert den Befehlscode-Benachrichtigung an. Finden Sie unter **"Hinweise"** für Weitere Informationen zu den Werten für *nCode*.

*pExtra*<br/>
Nach dem Wert des verwendet *nCode*. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *pExtra*.

*pHandlerInfo*<br/>
Falls ungleich NULL, `OnCmdMsg` füllt die *pTarget* und *Pmf* Mitglied der *pHandlerInfo* Struktur anstatt den Befehl zu verteilen. In der Regel sollte dieser Parameter NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Nachricht behandelt wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Dies ist die Haupt-Implementierung-Routine, die Architektur der Framework-Befehl.

Zur Laufzeit `OnCmdMsg` sendet einen Befehl für andere Objekte oder den Befehl selbst-handles durch Aufrufen der Stammklasse `CCmdTarget::OnCmdMsg`, führt die tatsächlichen meldungszuordnung-Suche. Eine vollständige Beschreibung der Standard-Befehlsrouting, finden Sie unter [Nachrichtenbehandlung und Zuordnen von Themen](../../mfc/message-handling-and-mapping.md).

In seltenen Fällen sollten Sie diese Memberfunktion zum Erweitern des Frameworks zu überschreiben standardbefehlsroutings. Finden Sie unter [technischen Hinweis 21](../../mfc/tn021-command-and-message-routing.md) für erweiterte Details der Befehlsrouting Architektur.

Wenn Sie außer Kraft setzen `OnCmdMsg`, müssen Sie angeben, den richtigen Wert für *nCode*, den Befehlscode Benachrichtigung und *pExtra*, das hängt vom Wert der *nCode* . In der folgende Tabelle sind die entsprechenden Werte aufgeführt:

|*nCode* Wert|*pExtra* Wert|
|-------------------|--------------------|
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)\*|
|CN_EVENT|AFX_EVENT\*|
|AUFGERUFEN|CCmdUI\*|
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)\*|
|CN_OLE_UNREGISTER|NULL|

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#44](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#45](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]

##  <a name="onfinalrelease"></a>  CCmdTarget::OnFinalRelease

Vom Framework aufgerufen, wenn der letzte OLE-Verweis zum oder vom Objekt freigegeben wird.

```
virtual void OnFinalRelease();
```

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um eine sonderverarbeitung für diese Situation bereitzustellen. Die Standardimplementierung wird das Objekt gelöscht.

##  <a name="restorewaitcursor"></a>  CCmdTarget::RestoreWaitCursor

Mit dieser Funktion können Sie entsprechende Sanduhrcursor wiederherstellen, nachdem der Systemcursor geändert wurde (z. B. nachdem ein Meldungsfeld geöffnet und dann während eines längeren Vorgangs geschlossen wurden).

```
void RestoreWaitCursor();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#43](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC ACDUAL-Beispiel](../../visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md)<br/>
[CDocument-Klasse](../../mfc/reference/cdocument-class.md)<br/>
[CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)<br/>
[CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[COleDispatchDriver-Klasse](../../mfc/reference/coledispatchdriver-class.md)
