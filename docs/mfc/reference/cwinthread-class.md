---
title: CWinThread-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7cbdcc1c5534d8dd9ba5d4f895af70a8ec16ac5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376965"
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
|[CWinThread:: CreateThread](#createthread)|Startet die Ausführung einer `CWinThread` Objekt.|  
|[CWinThread::ExitInstance](#exitinstance)|Außer Kraft setzen Sie, um zu bereinigen, wenn der Thread beendet wird.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Ruft einen Zeiger auf das Hauptfenster des Threads ab.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Ruft die Priorität des aktuellen Threads ab.|  
|[CWinThread::InitInstance](#initinstance)|Überschreiben Sie, um die instanzeninitialisierung des Threads ausführen.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Überprüft, ob besondere Nachrichten.|  
|[CWinThread::OnIdle](#onidle)|Überschreiben Sie, um die threadspezifische leerlaufzeitverarbeitung ausführen.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Sendet eine Meldung an eine andere `CWinThread` Objekt.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Filtert Nachrichten, bevor sie an die Windows-Funktionen verteilt sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Bestimmte Nachrichten abfängt, bevor sie die Anwendung nicht erreichen.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Fängt alle Ausnahmefehler, die von der Thread-Nachricht und Befehlshandler ausgelöst.|  
|[CWinThread::PumpMessage](#pumpmessage)|Enthält die Nachrichtenschleife für den Thread.|  
|[CWinThread:: ResumeThread](#resumethread)|Dekrementiert eine Thread den Unterbrechungszähler an.|  
|[Hauptmeldungsschleife](#run)|Die Steuerungsfunktion für Threads mit der ein Nachrichtensystem. Außer Kraft setzen Sie, um die Standard-Nachrichtenschleife anzupassen.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Legt die Priorität des aktuellen Threads fest.|  
|[CWinThread:: SuspendThread](#suspendthread)|Inkremente ein Thread den Unterbrechungszähler an.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinThread::operator HANDLE](#operator_handle)|Ruft das Handle der ab dem `CWinThread` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Gibt an, ob das Objekt Threadbeendigung zu zerstören.|  
|[CWinThread::m_hThread](#m_hthread)|Handle für den aktuellen Thread.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|Die ID des aktuellen Threads.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Ein Zeiger auf das Hauptfenster der containeranwendung, wenn ein OLE-Server in-Place aktiv ist.|  
|[CWinThread:: M_pmainwnd](#m_pmainwnd)|Enthält einen Zeiger auf das Hauptfenster der Anwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Der Hauptthread der Ausführung werden normalerweise von einem Objekt abgeleitet bereitgestellt `CWinApp`; `CWinApp` stammt aus `CWinThread`. Zusätzliche `CWinThread` Objekte können mehrere Threads innerhalb einer bestimmten Anwendung.  
  
 Es gibt zwei allgemeine Arten von Threads, die `CWinThread` unterstützt: Arbeitsthreads und Benutzeroberflächenthreads. Anzahl der Arbeitsthreads haben keine Nachrichtensystem: z. B. einen Thread, der im Hintergrund Berechnungen in einer Kalkulationstabelle-Anwendung ausführt. Benutzeroberflächenthreads Meldungsverteilschleife und Verarbeiten von Nachrichten, die vom System empfangen. [CWinApp](../../mfc/reference/cwinapp-class.md) und davon abgeleitete Klassen sind Beispiele für Benutzeroberflächenthreads. Andere Benutzeroberflächenthreads können auch direkt aus abgeleitet werden `CWinThread`.  
  
 Objekte der Klasse `CWinThread` in der Regel für die Dauer des Threads vorhanden sind. Wenn Sie dieses Verhalten ändern möchten, legen Sie [M_bAutoDelete](#m_bautodelete) auf **"false"**.  
  
 Die `CWinThread` Klasse ist erforderlich, Code und alle MFC vollständig threadsicher zu erstellen. Threadlokalen Daten, die vom Framework verwendet wird, um die Thread-spezifische Informationen verwalten erfolgt durch `CWinThread` Objekte. Aufgrund dieser Abhängigkeit von `CWinThread` um threadlokalen Daten behandeln zu können, muss jeder Thread, der MFC verwendet von MFC erstellt werden. Z. B. ein von der Funktion zur Laufzeit erstellten Thread [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) können keine MFC-APIs verwenden.  
  
 Rufen Sie zum Erstellen eines Threads [AfxBeginThread](application-information-and-management.md#afxbeginthread). Es gibt zwei Formen, je nachdem, ob einen Thread Worker- oder die Benutzeroberfläche angezeigt werden soll. Gegebenenfalls ein Benutzeroberflächenthread übergeben werden, um `AfxBeginThread` ein Zeiger auf die `CRuntimeClass` von Ihrer `CWinThread`-abgeleitete Klasse. Wenn ein Arbeitsthread erstellt werden sollen, übergeben Sie an `AfxBeginThread` einen Zeiger auf die Steuerungsfunktion und den Parameter an die Steuerungsfunktion. Für Arbeitsthreads und Benutzeroberflächenthreads können Sie optional Parameter angeben, die Priorität, Stapelgröße Erstellung Flags und Sicherheitsattribute ändern. `AfxBeginThread` Gibt einen Zeiger zurück, in die neue `CWinThread` Objekt.  
  
 Statt `AfxBeginThread`, für das Konstruieren einer `CWinThread`-abgeleitete Objekt und rufen Sie dann `CreateThread`. Diese Methode zweistufige Konstruktion ist nützlich, wenn Sie wiederverwenden möchten, die `CWinThread` Objekt zwischen aufeinander folgenden erstellen und der Thread Ausführungen Beendigungen.  
  
 Weitere Informationen zu `CWinThread`, finden Sie in den Artikeln [Multithreading mit C++ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading: Erstellen von Arbeitsthreads Threads](../../parallel/multithreading-creating-worker-threads.md), und [Multithreading: Gewusst wie: Verwenden von Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="createthread"></a>  CWinThread:: CreateThread  
 Erstellt einen Thread innerhalb des Adressraums des aufrufenden Prozesses ausgeführt.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwCreateFlags`  
 Gibt ein zusätzliches Flag an, das die Erstellung des Threads steuert. Dieses Flag kann einen von zwei Werten enthalten:  
  
- **CREATE_SUSPENDED** der Thread wird mit einem Unterbrechungszähler 1 gestartet. Verwendung **CREATE_SUSPENDED** , wenn Sie beliebige Memberdaten des initialisieren möchten die `CWinThread` Objekt, z. B. [M_bAutoDelete](#m_bautodelete) oder Member der abgeleiteten Klasse, befor der Thread ausgeführt wird. Sobald die Initialisierung abgeschlossen ist, verwenden die [CWinThread:: ResumeThread](#resumethread) an den Thread zu starten. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.  
  
- **0** direkt nach dem Erstellen der Thread gestartet.  
  
 `nStackSize`  
 Gibt die Stapelgröße für den neuen Thread in Bytes an. Wenn **0**, die Größe des Stapels wird standardmäßig auf die gleiche Größe wie der primäre Thread des Prozesses.  
  
 `lpSecurityAttrs`  
 Verweist auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die die Sicherheitsattribute für den Thread angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Thread wurde erfolgreich erstellt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `AfxBeginThread` zum Erstellen eines Threadobjekts, und führen Sie es in einem Schritt. Verwendung `CreateThread` , wenn Sie das Threadobjekt zwischen aufeinander folgenden erstellen und Beenden des Threads Ausführungen wiederverwenden möchten.  
  
##  <a name="cwinthread"></a>  CWinThread::CWinThread  
 Erstellt ein `CWinThread`-Objekt.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Hinweise  
 Um die Ausführung des Threads zu beginnen, rufen Sie die [CreateThread](#createthread) Memberfunktion. Erstellen Sie in der Regel Threads durch Aufruf [AfxBeginThread](application-information-and-management.md#afxbeginthread), der dieser Konstruktor aufgerufen und `CreateThread`.  
  
##  <a name="exitinstance"></a>  CWinThread::ExitInstance  
 Vom Framework aus überschriebenen eine selten aufgerufen [ausführen](#run) Memberfunktion versucht, diese Instanz des Threads, beendet oder wenn ein Aufruf von [InitInstance](#initinstance) ein Fehler auftritt.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Thread-Exitcode; 0 gibt an, keine Fehler, und geben einen Fehler an Werte größer als 0. Dieser Wert kann abgerufen werden, durch den Aufruf [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht diese Memberfunktion überall jedoch innerhalb der **ausführen** Memberfunktion. Diese Memberfunktion ist nur in Benutzeroberflächenthreads verwendet.  
  
 Die standardmäßige Implementierung dieser Funktion löscht den `CWinThread` Objekt, wenn [M_bAutoDelete](#m_bautodelete) ist **"true"**. Überschreiben Sie diese Funktion, wenn Sie möchten zusätzliche Bereinigung ausführen, wenn der Thread beendet wird. Ihre Implementierung von `ExitInstance` sollten die Basisklassenversion aufrufen, nachdem der Code ausgeführt wird.  
  
##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd  
 Wenn Ihre Anwendung einen OLE-Server ist, rufen Sie diese Funktion zum Abrufen von eines Zeigers auf das aktiven Hauptfenster der Anwendung und nicht direkt auf die `m_pMainWnd` Member des Anwendungsobjekts.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt einen Zeiger auf einen der zwei Arten von Fenstern. Wenn der Thread Teil der OLE-Server ist und verfügt über ein Objekt, das in-Place aktiv innerhalb einer aktiven Container ist, gibt diese Funktion die [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) Datenmember der `CWinThread` Objekt.  
  
 Diese Funktion gibt zurück, wenn kein Objekt, das in-Place aktiv in einem Container vorhanden ist oder die Anwendung keinen OLE-Server, der [M_pMainWnd](#m_pmainwnd) -Datenmember des Threadobjekts.  
  
### <a name="remarks"></a>Hinweise  
 Für Benutzeroberflächenthreads, dies entspricht dem direkten verweisen auf die `m_pActiveWnd` Member des Anwendungsobjekts.  
  
 Wenn es sich bei der Anwendung nicht um einen OLE-Server handelt, entspricht das Aufrufen dieser Funktion dem direkten Verweisen auf den `m_pMainWnd`-Member des Anwendungsobjekts.  
  
 Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.  
  
##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority  
 Ruft den aktuellen Thread Prioritätsstufe dieses Threads ab.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Thread Prioritätsstufe innerhalb seiner Prioritätsklasse. Der zurückgegebene Wert werden die folgenden von der höchsten Priorität zur niedrigsten aufgeführt:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **RANGFOLGE VON THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Weitere Informationen über diese Prioritäten finden Sie unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) im Windows SDK.  
  
##  <a name="initinstance"></a>  CWinThread::InitInstance  
 `InitInstance` muss überschrieben werden, um jede neue Instanz eines Threads für die Benutzeroberfläche zu initialisieren.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie in der Regel `InitInstance` Aufgaben, die abgeschlossen sein müssen, wenn ein Thread erstellt wird.  
  
 Diese Memberfunktion ist nur in Benutzeroberflächenthreads verwendet. Führen Sie die Initialisierung von Worker-Threads in die Steuerungsfunktion zu übergeben [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage  
 Überschreiben Sie diese Funktion zu **OnIdle** aufgerufen wird, nachdem bestimmte Nachrichten generiert werden.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Verweist auf die aktuelle Nachricht verarbeitet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `OnIdle` sollte aufgerufen werden, nach der Verarbeitung Nachricht, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung rufen nicht **OnIdle** nach redundante Maus und Nachrichten von blinkt, Caretzeichen generiert.  
  
 Wenn eine Anwendung einen kurzen Timer erstellt hat **OnIdle** aufgerufen wird, in vielen Fällen Leistungsprobleme verursacht. Überschreiben Sie zur Verbesserung der Leistung einer solchen Anwendung des `IsIdleMessage` in der Anwendungsverzeichnis `CWinApp`-abgeleitete Klasse zu suchende `WM_TIMER` Nachrichten wie folgt:  
  
 [!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Behandlung von `WM_TIMER` auf diese Weise wird die Leistung verbessert, kurze Timer verwenden.  
  
##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete  
 Gibt an, ob das `CWinThread`-Objekt der Threadbeendigung automatisch gelöscht werden soll.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_bAutoDelete` -Datenmember ist eine öffentliche Variable des Typs **BOOL**.  
  
 Der Wert von `m_bAutoDelete` beeinflusst nicht, wie das zugrunde liegende Threadhandle geschlossen wird. Das Threadhandle wird immer geschlossen, wenn das `CWinThread`-Objekt zerstört wird.  
  
##  <a name="m_hthread"></a>  CWinThread::m_hThread  
 Handle für den Thread an diese angefügt `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hThread` -Datenmember ist eine öffentliche Variable des Typs `HANDLE`. Es ist nur gültig, wenn die zugrunde liegende Thread derzeit vorhanden ist.  
  
##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID  
 ID des Threads angefügte `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die **M_nThreadID** -Datenmember ist eine öffentliche Variable des Typs `DWORD`. Es ist nur gültig, wenn die zugrunde liegende Thread derzeit vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd  
 Verwenden Sie dieses Datenelement, um einen Zeiger auf die aktive Fensterobjekt des Threads zu speichern.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class-Bibliothek wird automatisch Threads beendet, wenn das Fenster mit den bezeichnet `m_pActiveWnd` geschlossen wird. Wenn dieser Thread der primäre Thread für eine Anwendung ist, wird die Anwendung ebenfalls beendet. Wenn der Datenmember ist **NULL**, das aktive Fenster für der Anwendungsverzeichnis `CWinApp` Objekt geerbt werden. `m_pActiveWnd` ist eine öffentliche Variable des Typs **CWnd\***.  
  
 In der Regel legen Sie diese Membervariable beim Überschreiben `InitInstance`. In einem Arbeitsthread wird der Wert dieses Datenelements von seinem übergeordneten Thread geerbt.  
  
##  <a name="m_pmainwnd"></a>  CWinThread:: M_pmainwnd  
 Verwenden Sie dieses Datenelement, um einen Zeiger auf den Thread im Hauptfenster Objekt speichern.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class-Bibliothek wird automatisch Threads beendet, wenn das Fenster mit den bezeichnet `m_pMainWnd` geschlossen wird. Wenn dieser Thread der primäre Thread für eine Anwendung ist, wird die Anwendung ebenfalls beendet. Wenn dieses Datenelement ist **NULL**, die im Hauptfenster der Anwendung `CWinApp` Objekt wird verwendet, um zu bestimmen, wann der Thread beendet. `m_pMainWnd` ist eine öffentliche Variable des Typs **CWnd\***.  
  
 In der Regel legen Sie diese Membervariable beim Überschreiben `InitInstance`. In einem Arbeitsthread wird der Wert dieses Datenelements von seinem übergeordneten Thread geerbt.  
  
##  <a name="onidle"></a>  CWinThread::OnIdle  
 Überschreiben Sie diese Memberfunktion, um die Zeit im Leerlauf Verarbeitung durchzuführen.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Eine erhöht, jedes Mal `OnIdle` wird aufgerufen, wenn der Thread-Nachrichtenwarteschlange leer ist. Diese Anzahl wird jedes Mal auf 0 zurückgesetzt, wenn eine neue Nachricht verarbeitet wird. Sie können die `lCount` Parameter, um die relative Dauer Ermitteln der Thread wurde ohne Verarbeitung einer Nachricht im Leerlauf.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL im Leerlauf Verarbeitungszeit empfangen; 0, wenn keine weiteren Leerlaufzeiten benötigt wird.  
  
### <a name="remarks"></a>Hinweise  
 `OnIdle` wird in der Standardeinstellung Nachrichtenschleife aufgerufen werden, wenn der Thread-Nachrichtenwarteschlange leer ist. Verwenden Sie die Außerkraftsetzung, um eigene Hintergrund Aufgaben im Leerlauf Ereignishandler aufzurufen.  
  
 `OnIdle` sollte zurückgeben 0 an, um anzugeben, dass keine zusätzliche Leerlaufzeit-Verarbeitung erforderlich ist. Die `lCount` Parameter wird jedes Mal inkrementiert `OnIdle` wird aufgerufen, wenn die Nachrichtenwarteschlange leer ist und wird jedes Mal eine neue Nachricht verarbeitet wird auf 0 zurückgesetzt. Sie können Ihre verschiedenen im Leerlauf Routinen, die basierend auf diese Anzahl aufrufen.  
  
 Die standardmäßige Implementierung des diese Memberfunktion gibt die temporäre Objekte und nicht verwendeten DLL-Dateien aus dem Arbeitsspeicher frei.  
  
 Diese Memberfunktion ist nur in Benutzeroberflächenthreads verwendet.  
  
 Da die Anwendung Nachrichten erst verarbeiten kann `OnIdle` zurückgegeben wird, führen Sie langwierige Aufgaben in dieser Funktion nicht aus.  
  
##  <a name="operator_handle"></a>  CWinThread::operator HANDLE  
 Ruft das Handle der ab dem `CWinThread` Objekt.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle für das Threadobjekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie das Handle, um die Windows-APIs direkt aufrufen.  
  
##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage  
 Wird aufgerufen, um eine benutzerdefinierte Nachricht in eine andere zu senden `CWinThread` Objekt.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `message`  
 ID der benutzerdefinierten Meldung.  
  
 `wParam`  
 Ersten Meldungsparameter.  
  
 `lParam`  
 Zweiten Meldungsparameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die bereitgestellte Nachricht wird an den entsprechenden Meldungshandler zugeordnet, durch die Nachricht Map-Makro `ON_THREAD_MESSAGE`.  
  
> [!NOTE]
>  Beim Aufrufen der Windows [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) Funktion innerhalb einer MFC-Anwendung, die MFC-Nachricht, die Handler nicht aufgerufen werden. Weitere Informationen finden Sie unter im Knowledge Base-Artikel "PRB: MFC-Message-Handler nicht aufgerufen, mit PostThreadMessage()" (Q142415).  
  
##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage  
 Überschreiben Sie diese Funktion zu filtern, bevor sie an die Windows-Funktionen verteilt sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Verweist auf eine [MSG-Struktur](../../mfc/reference/msg-structure1.md) , die die zu verarbeitende Meldung enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Nachricht in vollständig verarbeitet war `PreTranslateMessage` und sollten nicht weiter verarbeitet werden. 0 (null), wenn die Nachricht auf die übliche Weise verarbeitet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist nur in Benutzeroberflächenthreads verwendet.  
  
##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter  
 Hookfunktion für das Framework ruft diese Memberfunktion filtern oder nur auf bestimmte Windows-Nachrichten reagiert.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 Gibt einen Hookcode. Diese Memberfunktion verwendet den Code, um zu bestimmen, wie verarbeitet `lpMsg.`  
  
 `lpMsg`  
 Ein Zeiger auf ein Windows [MSG-Struktur](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Hookfunktion verarbeitet Ereignisse vor dem Senden an die Anwendung normal Nachricht verarbeiten.  
  
 Wenn Sie diese erweiterte Funktion überschreiben, müssen Sie die Basisklassenversion zum Verwalten des Frameworks aufrufen Verarbeitung zu verknüpfen.  
  
##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException  
 Das Framework ruft diese Memberfunktion auf, wenn der Handler eine in einem der Meldung des Threads oder Befehlshandler ausgelöste Ausnahme nicht abfängt.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 *e*  
 Verweist auf eine nicht behandelte Ausnahme.  
  
 `pMsg`  
 Verweist auf eine [MSG-Struktur](../../mfc/reference/msg-structure1.md) mit Informationen über die Windows-Meldung, die das Framework eine Ausnahme verursacht hat.  
  
### <a name="return-value"></a>Rückgabewert  
 -1, wenn eine `WM_CREATE` Ausnahme wird generiert; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion nicht direkt auf.  
  
 Die Standardimplementierung von dieser Memberfunktion behandelt nur Ausnahmen, die aus den folgenden Nachrichten generiert:  
  
|Befehl|Aktion|  
|-------------|------------|  
|`WM_CREATE`|Ein Fehler auf.|  
|`WM_PAINT`|Überprüfen Sie das betroffene Fenster, und somit verhindert, dass eine andere `WM_PAINT` Nachricht generiert werden.|  
  
 Überschreiben Sie diese Memberfunktion zum globalen Behandlung der Ausnahmen bereitzustellen. Rufen Sie die Basisfunktionalität, nur dann, wenn das Standardverhalten angezeigt werden sollen.  
  
 Diese Memberfunktion ist nur in Threads verwendet, die ein Nachrichtensystem aufweisen.  
  
##  <a name="pumpmessage"></a>  CWinThread::PumpMessage  
 Enthält die Nachrichtenschleife für den Thread.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Hinweise  
 `PumpMessage` Enthält die Nachrichtenschleife für den Thread. **PumpMessage** wird aufgerufen, indem Sie `CWinThread` zum Weiterleiten von Nachrichten für den Thread. Sie können Aufrufen `PumpMessage` direkt zum Erzwingen von Nachrichten an die verarbeitet werden, oder überschreiben `PumpMessage` sein Standardverhalten zu ändern.  
  
 Aufrufen von `PumpMessage` direkt und sein Standardverhalten zu überschreiben, wird nur für fortgeschrittene Benutzer empfohlen.  
  
##  <a name="resumethread"></a>  CWinThread:: ResumeThread  
 Wird aufgerufen, um die Ausführung eines Threads fortgesetzt werden, die angehalten wurde, indem die [SuspendThread](#suspendthread) Memberfunktion oder ein Thread erstellt, mit der **CREATE_SUSPENDED** Flag.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Thread des vorherigen Unterbrechungszähler bei Erfolg; `0xFFFFFFFF` andernfalls. Wenn der Rückgabewert 0 (null) ist, wurde der aktuelle Thread nicht angehalten. Wenn der Rückgabewert eines ist, wird der Thread wurde angehalten, aber jetzt neu gestartet wird. Rückgabewerte, die größer als ein bedeutet, dass der Thread bleibt angehalten.  
  
### <a name="remarks"></a>Hinweise  
 Der Unterbrechungszähler des aktuellen Threads ist um eins verringert. Wenn der Unterbrechungszähler reduziert wird auf 0 (null), setzt der Thread die Ausführung; andernfalls bleibt der Thread angehalten.  
  
##  <a name="run"></a>  Hauptmeldungsschleife  
 Stellt eine Standard-Nachrichtenschleife für Benutzeroberflächenthreads bereit.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `int` Wert, der vom Thread zurückgegeben wird. Dieser Wert kann abgerufen werden, durch den Aufruf [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Hinweise  
 **Führen Sie** erhält und Windows-Meldungen sendet, bis die Anwendung empfängt eine [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) Nachricht. Wenn der Thread-Nachrichtenwarteschlange derzeit keine Nachrichten enthält **ausführen** Aufrufe `OnIdle` leerlaufzeitverarbeitung ausführen. Eingehende Nachrichten werden an die [PreTranslateMessage](#pretranslatemessage) Memberfunktion für spezielle Verarbeitung und dann in der Windows-Funktion [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) für die Standardtastatur Übersetzung. Schließlich die [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktion wird aufgerufen.  
  
 **Führen Sie** wird selten überschrieben wird, aber Sie können überschreiben, um spezielle Verhalten zu implementieren.  
  
 Diese Memberfunktion ist nur in Benutzeroberflächenthreads verwendet.  
  
##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority  
 Diese Funktion legt die Prioritätsstufe des aktuellen Threads innerhalb seiner Prioritätsklasse.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Parameter  
 `nPriority`  
 Gibt die neue Prioritätsebene innerhalb seiner Prioritätsklasse. Dieser Parameter muss einer der folgenden Werte an, von der höchsten Priorität zur niedrigsten aufgeführt werden:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **RANGFOLGE VON THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Weitere Informationen über diese Prioritäten finden Sie unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Er kann nur aufgerufen werden, nachdem [CreateThread](#createthread) erfolgreich ausgeführt wurde.  
  
##  <a name="suspendthread"></a>  CWinThread:: SuspendThread  
 Inkrementiert den aktuellen Thread den Unterbrechungszähler.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Thread des vorherigen Unterbrechungszähler bei Erfolg; `0xFFFFFFFF` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen beliebigen Thread den Unterbrechungszähler über 0 (null) aufweist, wird dieser Thread nicht ausgeführt. Der Thread kann fortgesetzt werden, durch Aufrufen der [ResumeThread](#resumethread) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
