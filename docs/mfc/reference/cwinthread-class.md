---
title: CWinThread-Klasse
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: 0e02f123580696519e59d828ec590456cbd2a81c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323280"
---
# <a name="cwinthread-class"></a>CWinThread-Klasse

Stellt einen Ausführungsthread innerhalb einer Anwendung dar.

## <a name="syntax"></a>Syntax

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinThread::CWinThread](#cwinthread)|Erstellt ein `CWinThread`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CWinThread::CreateThread](#createthread)|Startet die Ausführung einer `CWinThread` Objekt.|
|[CWinThread::ExitInstance](#exitinstance)|Überschreiben Sie zum Bereinigen, wenn der Thread beendet wird.|
|[CWinThread::GetMainWnd](#getmainwnd)|Ruft einen Zeiger auf das Hauptfenster für den Thread ab.|
|[CWinThread::GetThreadPriority](#getthreadpriority)|Ruft die Priorität des aktuellen Threads ab.|
|[CWinThread::InitInstance](#initinstance)|Überschreiben Sie, um die instanzeninitialisierung des Threads ausführen.|
|[CWinThread::IsIdleMessage](#isidlemessage)|Überprüft, ob besondere Nachrichten.|
|[CWinThread::OnIdle](#onidle)|Überschreiben Sie, um die threadspezifische leerlaufzeitverarbeitung ausführen.|
|[CWinThread::PostThreadMessage](#postthreadmessage)|Sendet eine Meldung an einen anderen `CWinThread` Objekt.|
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Filtert Nachrichten, bevor sie für die Windows-Funktionen weitergeleitet werden [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).|
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Bestimmte Nachrichten abfängt, bevor sie die Anwendung erreichen.|
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Fängt alle nicht behandelte Ausnahmen, die von der Thread die Nachricht und befehlshandlern ausgelöst.|
|[CWinThread::PumpMessage](#pumpmessage)|enthält die Nachrichtenschleife des Threads.|
|[CWinThread::ResumeThread](#resumethread)|Wird ein Thread den Unterbrechungszähler.|
|[CWinThread::Run](#run)|Die Steuerungsfunktion für Threads mit der eine Meldungsverteilschleife. Überschreiben Sie, um die Standardnachrichtenschleife anpassen.|
|[CWinThread::SetThreadPriority](#setthreadpriority)|Legt die Priorität des aktuellen Threads fest.|
|[CWinThread::SuspendThread](#suspendthread)|Schritten ein Thread den Unterbrechungszähler.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CWinThread::operator HANDLE](#operator_handle)|Ruft das Handle des dem `CWinThread` Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Gibt an, ob das Objekt bei Threadbeendigung zu zerstören.|
|[CWinThread::m_hThread](#m_hthread)|Handle für den aktuellen Thread.|
|[CWinThread::m_nThreadID](#m_nthreadid)|Die ID des aktuellen Threads.|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Zeiger auf das Hauptfenster der containeranwendung, wenn ein OLE-Server direkt aktiv ist.|
|[CWinThread::m_pMainWnd](#m_pmainwnd)|Enthält einen Zeiger auf das Hauptfenster der Anwendung.|

## <a name="remarks"></a>Hinweise

Der Hauptthread der Ausführung erfolgt in der Regel von einem Objekt abgeleitet `CWinApp`; `CWinApp` ergibt sich aus `CWinThread`. Zusätzliche `CWinThread` Objekte ermöglichen es mehreren Threads in einer bestimmten Anwendung.

Es gibt zwei allgemeine Arten von Threads, die `CWinThread` unterstützt: Anzahl der Arbeitsthreads und Benutzeroberflächen-Threads. Anzahl der Arbeitsthreads haben keine Nachrichtensystem: z. B. ein Thread, der die Hintergrund-Berechnungen in einem Tabellenkalkulationsprogramm ausführt. Benutzeroberflächenthreads Meldungsverteilschleife und Verarbeiten von Nachrichten aus dem System. [CWinApp](../../mfc/reference/cwinapp-class.md) und davon abgeleitete Klassen sind Beispiele für Benutzeroberflächen-Threads. Andere UI-Threads können auch direkt von abgeleitet werden `CWinThread`.

Objekte der Klasse `CWinThread` in der Regel für die Dauer des Threads vorhanden sind. Wenn Sie dieses Verhalten ändern möchten, legen Sie [M_bAutoDelete](#m_bautodelete) auf "false".

Die `CWinThread` Klasse ist erforderlich, um Ihren Code und MFC-vollständig threadsicher zu machen. Thread-lokalen Daten, die vom Framework verwendet werden, um die Thread-spezifische Informationen zu verwalten, die von verwaltet werden `CWinThread` Objekte. Aufgrund dieser Abhängigkeit `CWinThread` um threadlokalen Daten behandeln zu können, muss jeder Thread, der verwendet MFC von MFC erstellt werden. Z. B. ein Thread, die von der Laufzeit-Funktion erstellt [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) können keine MFC-APIs verwenden.

Rufen Sie zum Erstellen eines Threads [AfxBeginThread](application-information-and-management.md#afxbeginthread). Es gibt zwei Formen, je nachdem, ob einen Worker- oder UI-Thread angezeigt werden soll. Gegebenenfalls einen Benutzeroberflächen-Thread übergeben, um `AfxBeginThread` ein Zeiger auf die `CRuntimeClass` von Ihrem `CWinThread`-abgeleitete Klasse. Wenn ein Arbeitsthread erstellt werden sollen, übergeben Sie an `AfxBeginThread` einen Zeiger auf die Steuerungsfunktion und den Parameter an die Steuerungsfunktion. Für die Anzahl der Arbeitsthreads und Benutzeroberflächen-Threads können Sie optional Parameter angeben, die Priorität, Stapelgröße, erstellungs-Flags und Attribute für Sicherheit ändern. `AfxBeginThread` Gibt einen Zeiger auf die neue `CWinThread` Objekt.

Statt `AfxBeginThread`, können Sie erstellen eine `CWinThread`-Typ abgeleitete Objekt und rufen Sie dann `CreateThread`. Diese zweistufige Konstruktion-Methode ist nützlich, wenn Sie wiederverwenden möchten die `CWinThread` Objekt zwischen aufeinander folgenden Erstellung und kündigungen von Thread-Ausführungen.

Weitere Informationen zu `CWinThread`, finden Sie in den Artikeln [Multithreading mit C++ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md), und [Multithreading: Gewusst wie: der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="createthread"></a>  CWinThread::CreateThread

Erstellt einen Thread innerhalb des Adressraums des aufrufenden Prozesses ausgeführt.

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Parameter

*dwCreateFlags*<br/>
Gibt ein zusätzliches Flag an, das die Erstellung des Threads steuert. Dieses Flag kann einen von zwei Werten enthalten:

- Der Thread wird mit dem Unterbrechungszähler eines CREATE_SUSPENDED gestartet. CREATE_SUSPENDED verwenden, wenn Sie beliebige Memberdaten des initialisieren möchten die `CWinThread` Objekt, z. B. [M_bAutoDelete](#m_bautodelete) oder beliebige Member der abgeleiteten Klasse, befor der Thread ausgeführt wird. Sobald die Initialisierung abgeschlossen ist, verwenden die [CWinThread:: ResumeThread](#resumethread) auf den Thread zu starten. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.

- **0** der Thread wird unmittelbar nach der Erstellung gestartet.

*nStackSize*<br/>
Gibt die Stapelgröße für den neuen Thread in Bytes an. Wenn **0**, die Größe des Stapels wird standardmäßig auf die gleiche Größe wie der primäre Thread des Prozesses.

*lpSecurityAttrs*<br/>
Verweist auf eine [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Struktur, die Attribute für die Sicherheit für den Thread angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Thread wurde erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwendung `AfxBeginThread` zum Erstellen von einem Thread-Objekt, und führen Sie ihn in einem Schritt. Verwendung `CreateThread` , wenn Sie das Threadobjekt zwischen aufeinander folgenden Erstellung und Beendigung der Ausführung des Threads wiederverwenden möchten.

##  <a name="cwinthread"></a>  CWinThread::CWinThread

Erstellt ein `CWinThread`-Objekt.

```
CWinThread();
```

### <a name="remarks"></a>Hinweise

Um den Thread der Ausführung zu starten, rufen Sie die [CreateThread](#createthread) Member-Funktion. Erstellen Sie in der Regel Threads durch Aufruf [AfxBeginThread](application-information-and-management.md#afxbeginthread), der dieser Konstruktor aufgerufen und `CreateThread`.

##  <a name="exitinstance"></a>  CWinThread::ExitInstance

Wird aufgerufen, durch das Framework aus, in einer nur selten außer Kraft gesetzte [ausführen](#run) Memberfunktion versucht, diese Instanz des Threads, beendet oder wenn ein Aufruf von [InitInstance](#initinstance) ein Fehler auftritt.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Rückgabewert

Code zum Beenden des Threads; 0 gibt an, keine Fehler, und geben einen Fehler an Werte größer als 0. Dieser Wert kann abgerufen werden, durch den Aufruf [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).

### <a name="remarks"></a>Hinweise

Rufen Sie nicht diese Memberfunktion von überall aus aber noch innerhalb der `Run` Member-Funktion. Diese Memberfunktion wird nur im UI-Threads verwendet.

Die Standardimplementierung dieser Funktion löscht den `CWinThread` Objekt, wenn [M_bAutoDelete](#m_bautodelete) ist "true". Überschreiben Sie diese Funktion, wenn Sie möchten weitere Bereinigung durchführen, wenn der Thread beendet wird. Die Implementierung von `ExitInstance` sollte Version von der Basisklasse aufrufen, nachdem Ihr Code ausgeführt wird.

##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd

Wenn Ihre Anwendung einen OLE-Server ist, rufen Sie diese Funktion zum Abrufen der eines Zeigers auf das aktiven Hauptfenster der Anwendung anstelle der direkten verweisen auf die `m_pMainWnd` Member des Anwendungsobjekts.

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>Rückgabewert

Diese Funktion gibt einen Zeiger auf einen der zwei Arten von Fenstern. Wenn der Thread Teil von einem OLE-Server ist und ein Objekt, das direkt aktiv in einem aktiven Container ist, wird diese Funktion gibt die [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) Datenmember der `CWinThread` Objekt.

Diese Funktion gibt zurück, wenn kein Objekt, das direkt aktiv in einem Container vorhanden ist, oder Ihre Anwendung ist nicht mit einem OLE-Server, die [M_pMainWnd](#m_pmainwnd) -Datenmember des Threadobjekts.

### <a name="remarks"></a>Hinweise

Für Benutzeroberflächen-Threads, dies entspricht dem direkten verweisen auf die `m_pActiveWnd` Member des Anwendungsobjekts.

Wenn es sich bei der Anwendung nicht um einen OLE-Server handelt, entspricht das Aufrufen dieser Funktion dem direkten Verweisen auf den `m_pMainWnd`-Member des Anwendungsobjekts.

Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.

##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority

Ruft die aktuelle Prioritätsebene des Threads ab.

```
int GetThreadPriority();
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Thread Prioritätsstufe innerhalb seiner Prioritätsklasse. Der zurückgegebene Wert wird einer der folgenden, von der höchsten zur niedrigsten aufgeführt:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Weitere Informationen zu dieser Prioritäten, finden Sie unter [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) im Windows SDK.

##  <a name="initinstance"></a>  CWinThread::InitInstance

`InitInstance` muss überschrieben werden, um jede neue Instanz eines Benutzeroberflächen-Threads zu initialisieren.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Initialisierung erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

In der Regel, die Sie überschreiben `InitInstance` für Aufgaben, die ausgeführt werden müssen, wenn ein Thread erstellt wird.

Diese Memberfunktion wird nur im UI-Threads verwendet. Führen Sie die Initialisierung von Worker-Threads im, die an die Steuerungsfunktion [AfxBeginThread](application-information-and-management.md#afxbeginthread).

##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage

Überschreiben Sie diese Funktion zu `OnIdle` aufgerufen wird, nachdem bestimmte Nachrichten generiert wurden.

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Verweist auf die aktuelle Nachricht verarbeitet wird.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL `OnIdle` aufgerufen werden soll, nach der Verarbeitung Meldung, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung ruft nicht `OnIdle` nach redundante mausmeldungen und vom blinkt Caretzeichen generiert wurden.

Wenn eine Anwendung einen kurzen Timer erstellt hat `OnIdle` wird aufgerufen, in vielen Fällen Leistungsprobleme. Überschreiben Sie zur Verbesserung der Leistung für eine solche Anwendung des `IsIdleMessage` in der Anwendung `CWinApp`-abgeleitete Klasse zu prüfen, WM_TIMER Nachrichten wie folgt:

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

Behandlung WM_TIMER auf diese Weise wird die Leistung von Anwendungen verbessert, die kurze Timer zu verwenden.

##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete

Gibt an, ob das `CWinThread`-Objekt der Threadbeendigung automatisch gelöscht werden soll.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Hinweise

Die `m_bAutoDelete` -Datenmember ist eine öffentliche Variable des Typs "bool".

Der Wert von `m_bAutoDelete` beeinflusst nicht, wie das zugrunde liegende Threadhandle geschlossen wird. Das Threadhandle wird immer geschlossen, wenn das `CWinThread`-Objekt zerstört wird.

##  <a name="m_hthread"></a>  CWinThread::m_hThread

Handle für den Thread angefügte `CWinThread`.

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Hinweise

Die `m_hThread` -Datenmember ist eine öffentliche Variable des Typs HANDLE. Es ist nur gültig, wenn derzeit zugrunde liegenden Thread vorhanden ist.

##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID

ID des Threads angefügte `CWinThread`.

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Hinweise

Die `m_nThreadID` -Datenmember ist eine öffentliche Variable vom Typ DWORD. Es ist nur gültig, wenn derzeit zugrunde liegenden Thread vorhanden ist.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [AfxGetThread](application-information-and-management.md#afxgetthread).

##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd

Verwenden Sie dieses Datenelement, um einen Zeiger auf des aktiven Fensterobjekt des Threads zu speichern.

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Hinweise

Die Microsoft Foundation Class-Bibliothek automatisch den Thread beendet, wenn das Fenster mit den bezeichnet `m_pActiveWnd` geschlossen wird. Wenn dieser Thread auf den primären Thread für eine Anwendung ist, wird die Anwendung ebenfalls beendet. Dieses Datenelement ist NULL, das aktive Fenster für der Anwendung die `CWinApp` Objekt ist vererbt werden. `m_pActiveWnd` ist eine öffentliche Variable des Typs `CWnd*`.

In der Regel Sie diese Membervariable festlegen, wenn Sie außer Kraft setzen `InitInstance`. In einem Arbeitsthread wird der Wert dieses Datenelements von seinem übergeordneten Thread geerbt.

##  <a name="m_pmainwnd"></a>  CWinThread::m_pMainWnd

Verwenden Sie dieses Datenelement, um einen Zeiger auf des Threads im Hauptfenster Objekt zu speichern.

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Hinweise

Die Microsoft Foundation Class-Bibliothek automatisch den Thread beendet, wenn das Fenster mit den bezeichnet `m_pMainWnd` geschlossen wird. Wenn dieser Thread auf den primären Thread für eine Anwendung ist, wird die Anwendung ebenfalls beendet. Wenn dieses Datenelement NULL im Hauptfenster der Anwendung ist `CWinApp` Objekt wird verwendet, um zu bestimmen, wann der Thread beendet. `m_pMainWnd` ist eine öffentliche Variable des Typs `CWnd*`.

In der Regel Sie diese Membervariable festlegen, wenn Sie außer Kraft setzen `InitInstance`. In einem Arbeitsthread wird der Wert dieses Datenelements von seinem übergeordneten Thread geerbt.

##  <a name="onidle"></a>  CWinThread::OnIdle

Überschreiben Sie diese Memberfunktion, um die Verarbeitung der Leerlauf-Ablaufzeitpunkt durchzuführen.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Parameter

*lCount*<br/>
Ein Zähler erhöht, jedes Mal `OnIdle` wird aufgerufen, wenn der Thread die Warteschlange leer ist. Diese Anzahl wird jedes Mal auf 0 zurückgesetzt, wenn eine neue Nachricht verarbeitet wird. Sie können die *lCount* Parameter, um die relative Dauer zu ermitteln, der Thread wurde ohne Verarbeitung einer Nachricht im Leerlauf befindet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL im Leerlauf-Verarbeitungszeit empfangen; 0, wenn keine weiteren Verarbeitung Leerlaufzeit benötigt wird.

### <a name="remarks"></a>Hinweise

`OnIdle` wird in die Standardnachrichtenschleife aufgerufen werden, wenn der Thread die Warteschlange leer ist. Verwenden Sie die Außerkraftsetzung, um eigene Hintergrund im Leerlauf-Handler Aufgaben aufzurufen.

`OnIdle` sollte zurückgeben 0 an, um anzugeben, dass keine zusätzliche Leerlaufzeit-Verarbeitung erforderlich ist. Die *lCount* Parameter wird jedes Mal inkrementiert `OnIdle` wird aufgerufen, wenn die Nachrichtenwarteschlange leer ist, und jedes Mal eine neue Nachricht verarbeitet wird auf 0 zurückgesetzt. Sie können Ihre anderen im Leerlauf Routinen, die basierend auf diesen aufrufen.

Die Standardimplementierung von dieser Memberfunktion wird die temporäre Objekte und nicht verwendeten DLL-Bibliotheken aus dem Speicher freigegeben.

Diese Memberfunktion wird nur im UI-Threads verwendet.

Da die Anwendung nicht, Nachrichten bis verarbeiten kann `OnIdle` zurückgegeben wird, führen Sie keine langwierige Aufgaben in dieser Funktion.

##  <a name="operator_handle"></a>  CWinThread::operator HANDLE

Ruft das Handle des dem `CWinThread` Objekt.

```
operator HANDLE() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, das Handle des Objekts Thread andernfalls NULL.

### <a name="remarks"></a>Hinweise

Verwenden Sie das Handle, um die Windows-APIs direkt aufrufen.

##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage

Wird aufgerufen, um eine benutzerdefinierte Nachricht in eine andere post `CWinThread` Objekt.

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*message*<br/>
Die ID der benutzerdefinierten Meldung.

*wParam*<br/>
Ersten Meldungsparameter.

*lParam*<br/>
Zweiten Meldungsparameter.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die bereitgestellte Nachricht wird an den entsprechenden Meldungshandler durch das Makro ON_THREAD_MESSAGE der Message-Zuordnung zugeordnet.

> [!NOTE]
> Beim Aufruf [PostThreadMessage](/windows/desktop/api/winuser/nf-winuser-postthreadmessagea), die Nachricht wird in der Thread die Warteschlange eingefügt. Jedoch, da auf diese Weise zu geposteten Nachrichten keinem Fenster zugeordnet sind, wird MFC nicht diese an die Nachricht oder einen Befehl Handler ausgewählt werden. Um diese Nachrichten zu verarbeiten, überschreiben die `PreTranslateMessage()` Funktion Ihrer CWinApp-abgeleitete Klasse, und die Nachrichten manuell verarbeiten.

##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage

Außer Kraft setzen diese Funktion fenstermeldungen zu filtern, bevor sie für die Windows-Funktionen weitergeleitet werden [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*pMsg*<br/>
Verweist auf eine [MSG-Struktur](/windows/desktop/api/winuser/ns-winuser-tagmsg) , die die zu verarbeitende Meldung enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Nachricht vollständig, im verarbeitet wurde `PreTranslateMessage` und sollten nicht weiter verarbeitet werden. NULL, wenn die Nachricht auf die übliche Weise verarbeitet werden soll.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird nur im UI-Threads verwendet.

##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter

Die Framework Hook-Funktion ruft diese Memberfunktion zum Filtern von und reagieren auf bestimmte Windows-Nachrichten.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Parameter

*Code*<br/>
Gibt einen Hookcode. Diese Memberfunktion verwendet der Code, um zu bestimmen, wie verarbeiten *LpMsg.*

*lpMsg*<br/>
Ein Zeiger auf ein Windows [MSG-Struktur](/windows/desktop/api/winuser/ns-winuser-tagmsg).

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Hookfunktion verarbeitet Ereignisse vor dem Senden an die normale Meldung von der Anwendung verarbeitet.

Wenn Sie diese erweiterte Funktion überschreiben, achten Sie darauf, ruft die Version der Basisklasse zum Verwalten des Frameworks Verarbeitung zu verknüpfen.

##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException

Das Framework ruft diese Memberfunktion auf, wenn der Handler eine Ausnahme in einem des Threads-Nachricht oder Befehlshandler nicht abfängt.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Parameter

*e*<br/>
Verweist auf eine nicht behandelte Ausnahme.

*pMsg*<br/>
Verweist auf eine [MSG-Struktur](/windows/desktop/api/winuser/ns-winuser-tagmsg) mit Informationen über die Windows-Meldung, die das Framework eine Ausnahme verursacht hat.

### <a name="return-value"></a>Rückgabewert

-1, wenn eine WM_CREATE-Ausnahme generiert wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion nicht direkt auf.

Die Standardimplementierung von dieser Memberfunktion behandelt nur die Ausnahmen, die aus den folgenden Nachrichten generiert:

|Befehl|Aktion|
|-------------|------------|
|WM_CREATE|Ein Fehler auf.|
|WM_PAINT|Überprüfen Sie das betroffene Fenster, und somit verhindert, dass eine andere WM_PAINT-Meldung generiert wird.|

Überschreiben Sie diese Memberfunktion zum globalen Behandlung für die Ausnahmen bereitzustellen. Rufen Sie die grundlegende Funktionen nur, wenn Sie das Standardverhalten anzeigen möchten.

Diese Memberfunktion ist nur in Threads verwendet, die eine Meldungsverteilschleife.

##  <a name="pumpmessage"></a>  CWinThread::PumpMessage

enthält die Nachrichtenschleife des Threads.

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Hinweise

`PumpMessage` enthält die Nachrichtenschleife des Threads. `PumpMessage` wird aufgerufen, indem `CWinThread` , des Threads Nachrichten senden. Rufen Sie `PumpMessage` direkt erzwingen, dass Nachrichten verarbeitet werden, oder überschreiben `PumpMessage` sein Standardverhalten zu ändern.

Aufrufen von `PumpMessage` direkt und überschreiben das Standardverhalten wird nur für fortgeschrittene Benutzer empfohlen.

##  <a name="resumethread"></a>  CWinThread:: ResumeThread

Wird aufgerufen, um die Ausführung eines Threads fortzusetzen, indem Sie angehalten wurde, die [SuspendThread](#suspendthread) Memberfunktion oder ein Thread, der mit dem CREATE_SUSPENDED-Flag erstellt.

```
DWORD ResumeThread();
```

### <a name="return-value"></a>Rückgabewert

Der Thread die vorherigen Unterbrechungszähler-Methode auf, wenn erfolgreich; `0xFFFFFFFF` andernfalls. Wenn der Rückgabewert 0 (null) ist, wurde der aktuelle Thread nicht angehalten. Wenn der Rückgabewert eine ist, wird der Thread wurde angehalten, aber jetzt neu gestartet wird. Jeder Rückgabewert größer als ein bedeutet, dass der Thread bleibt angehalten.

### <a name="remarks"></a>Hinweise

Der Unterbrechungszähler des aktuellen Threads wird um eins verringert. Wenn der Unterbrechungszähler reduziert ist 0 (null), wird der Thread die Ausführung; fortgesetzt andernfalls bleibt der Thread angehalten.

##  <a name="run"></a>  Hauptmeldungsschleife

Stellt eine Standard-Meldungsschleife für Benutzeroberflächen-Threads bereit.

```
virtual int Run();
```

### <a name="return-value"></a>Rückgabewert

Ein **Int** -Wert, der durch den Thread zurückgegeben wird. Dieser Wert kann abgerufen werden, durch den Aufruf [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread).

### <a name="remarks"></a>Hinweise

`Run` reserviert und Windows-Meldungen sendet, bis die Anwendung empfängt eine [WM_QUIT](/windows/desktop/winmsg/wm-quit) Nachricht. Wenn der Thread die Warteschlange derzeit keine Nachrichten von der enthält `Run` Aufrufe `OnIdle` auszuführenden leerlaufzeitverarbeitung. Eingehende Nachrichten werden an die [PreTranslateMessage](#pretranslatemessage) Memberfunktion zur speziellen Verarbeitung, und klicken Sie dann an die Windows-Funktion [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) für die Standardtastatur Übersetzung. Zum Schluss die [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktion wird aufgerufen.

`Run` nur selten überschrieben wird, kann jedoch überschrieben werden, um besonderes Verhalten zu implementieren.

Diese Memberfunktion wird nur im UI-Threads verwendet.

##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority

Diese Funktion legt die Prioritätsebene des aktuellen Threads innerhalb seiner Prioritätsklasse.

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>Parameter

*nPriority*<br/>
Gibt die neue Prioritätsebene innerhalb seiner Prioritätsklasse an. Dieser Parameter muss eine der folgenden Werte an, von der höchsten zur niedrigsten aufgeführt sein:

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

Weitere Informationen zu dieser Prioritäten, finden Sie unter [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Funktion erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Es kann nur aufgerufen werden, nachdem [CreateThread](#createthread) erfolgreich zurückgegeben wird.

##  <a name="suspendthread"></a>  CWinThread:: SuspendThread

Erhöht die aktuelle Anzahl der Unterbrechungen des Threads.

```
DWORD SuspendThread();
```

### <a name="return-value"></a>Rückgabewert

Der Thread die vorherigen Unterbrechungszähler-Methode auf, wenn erfolgreich; `0xFFFFFFFF` andernfalls.

### <a name="remarks"></a>Hinweise

Wenn Sie einen beliebigen Thread den Unterbrechungszähler über 0 (null) aufweist, wird dieser Thread nicht ausgeführt. Der Thread kann fortgesetzt werden, durch den Aufruf der [ResumeThread](#resumethread) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
