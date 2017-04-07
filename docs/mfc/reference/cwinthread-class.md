---
title: CWinThread-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- worker threads
- threading [MFC], safety
- CWinThread class
- threading [MFC], creating threads
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 866e847f9c1d73d6f9882e50b1274fbad9e21a39
ms.lasthandoff: 02/24/2017

---
# <a name="cwinthread-class"></a>CWinThread-Klasse
Stellt einen Ausführungsthread innerhalb einer Anwendung dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|Erstellt ein `CWinThread`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CreateThread](#createthread)|Startet die Ausführung einer `CWinThread` Objekt.|  
|[CWinThread::ExitInstance](#exitinstance)|Überschreiben Sie zum Bereinigen, wenn der Thread beendet wird.|  
|[CWinThread::GetMainWnd](#getmainwnd)|Ruft einen Zeiger auf das Hauptfenster für den Thread ab.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|Ruft die Priorität des aktuellen Threads ab.|  
|[CWinThread::InitInstance](#initinstance)|Überschreiben Sie, um die Instanz die Initialisierung ausführen.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|Überprüft, ob besondere Nachrichten.|  
|[CWinThread::OnIdle](#onidle)|Überschreiben Sie, um die threadspezifische leerlaufzeitverarbeitung ausführen.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|Sendet eine Nachricht an einen anderen `CWinThread` Objekt.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Filtert Nachrichten vor dem für die Windows-Funktionen sind [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|Bestimmte Nachrichten abfängt, bevor sie die Anwendung nicht erreichen.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|Fängt alle nicht behandelte Ausnahmen, die von der Thread-Nachricht und Befehlshandler ausgelöst.|  
|[CWinThread::PumpMessage](#pumpmessage)|Enthält die Meldungsschleife des Threads.|  
|[CWinThread:: ResumeThread](#resumethread)|Verringert ein Thread den Unterbrechungszähler.|  
|[Hauptmeldungsschleife](#run)|Steuerungsfunktion für Threads mit einem Nachrichtensystem. Überschreiben Sie, um die Standardnachrichtenschleife anpassen.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|Legt die Priorität des aktuellen Threads fest.|  
|[CWinThread:: SuspendThread](#suspendthread)|Schritten ein Thread den Unterbrechungszähler.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinThread::operator HANDLE](#operator_handle)|Ruft das Handle des dem `CWinThread` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|Gibt an, ob das Objekt Threadbeendigung zu zerstören.|  
|[CWinThread::m_hThread](#m_hthread)|Handle für den aktuellen Thread.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|Die ID des aktuellen Threads.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|Zeiger auf das Hauptfenster der containeranwendung, wenn ein OLE-Server direkt aktiv ist.|  
|[CWinThread:: M_pmainwnd](#m_pmainwnd)|Enthält einen Zeiger auf das Hauptfenster der Anwendung.|  
  
## <a name="remarks"></a>Hinweise  
 Der Hauptthread der Ausführung erfolgt in der Regel von einem Objekt abgeleitet `CWinApp`; `CWinApp` abgeleitet ist `CWinThread`. Zusätzliche `CWinThread` Objekte können mehrere Threads in der Anwendung.  
  
 Es gibt zwei allgemeine Arten von Threads, die `CWinThread` unterstützt: Arbeitsthreads und Benutzeroberflächen-Threads. Arbeitsthreads haben keine Nachrichtensystem: z. B. einen Thread, der in einem Tabellenkalkulationsprogramm Hintergrund Berechnungen durchführt. Benutzeroberflächenthreads Meldungsverteilschleife und Verarbeiten von Nachrichten aus dem System. [CWinApp](../../mfc/reference/cwinapp-class.md) und davon abgeleitete Klassen sind Beispiele für Benutzeroberflächen-Threads. Andere Benutzeroberflächen-Threads können auch direkt von abgeleitet werden `CWinThread`.  
  
 Objekte der Klasse `CWinThread` bestehen in der Regel für die Dauer des Threads. Wenn Sie dieses Verhalten ändern möchten, legen Sie [M_bAutoDelete](#m_bautodelete) auf **FALSE**.  
  
 Die `CWinThread` Klasse ist erforderlich, Code und MFC vollständig threadsicher zu machen. Threadlokale Daten, die vom Framework verwendet werden, um Informationen zu verwalten, die von verwaltet werden `CWinThread` Objekte. Aufgrund dieser Abhängigkeit `CWinThread` um threadlokalen Daten zu behandeln, muss jeder Thread, der MFC verwendet, von MFC erstellt werden. Z. B. von der Funktion zur Laufzeit erstellten Thread [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) keine MFC-APIs verwenden.  
  
 Rufen Sie zum Erstellen eines Threads [AfxBeginThread](application-information-and-management.md#afxbeginthread). Es gibt zwei Arten, je nachdem, ob Sie einen Worker oder Benutzeroberflächen-Thread. Gegebenenfalls einen Benutzeroberflächen-Thread übergeben `AfxBeginThread` ein Zeiger auf die `CRuntimeClass` von Ihrer `CWinThread`-abgeleiteten Klasse. Wenn Sie einen Arbeitsthread erstellen möchten, übergeben Sie an `AfxBeginThread` einen Zeiger auf die Steuerungsfunktion und den Parameter an die Steuerungsfunktion. Für Arbeitsthreads und Benutzeroberflächen-Threads können Sie optionale Parameter angeben, die Priorität, Stapelgröße, Erstellung Flags und Sicherheitsattribute ändern. `AfxBeginThread`Gibt einen Zeiger zurück, in die neue `CWinThread` Objekt.  
  
 Statt `AfxBeginThread`, kann eine `CWinThread`-abgeleitete Objekt und rufen dann `CreateThread`. Diese Methode für die Erstellung in zwei Schritten ist nützlich, wenn Sie wiederverwenden möchten, die `CWinThread` Objekt zwischen aufeinander folgenden Erstellung und Beendigungen eines Threads Ausführungen.  
  
 Weitere Informationen zu `CWinThread`, finden Sie in den Artikeln [Multithreading mit C++ und MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md), [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md), und [Multithreading: wie der Synchronisierungsklassen](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="createthread"></a>CreateThread  
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
  
- **CREATE_SUSPENDED** der Thread mit einem Unterbrechungszähler&1; gestartet. Verwendung **CREATE_SUSPENDED** Wenn Sie beliebige Memberdaten des initialisieren möchten die `CWinThread` Objekt, z. B. [M_bAutoDelete](#m_bautodelete) oder Member der abgeleiteten Klasse, bevor der Thread gestartet. Sobald die Initialisierung abgeschlossen ist, verwenden Sie die [CWinThread:: ResumeThread](#resumethread) auf den Thread zu starten. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.  
  
- **0** der Thread wird unmittelbar nach der Erstellung gestartet.  
  
 `nStackSize`  
 Gibt die Stapelgröße für den neuen Thread in Bytes an. Wenn **0**, die Größe des Stapels wird standardmäßig auf die gleiche Größe wie der primäre Thread des Prozesses.  
  
 `lpSecurityAttrs`  
 Verweist auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die die Sicherheitsattribute für den Thread angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Thread erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `AfxBeginThread` Threadobjekt erstellen und dieses in einem Schritt ausführen. Verwendung `CreateThread` Wenn das Threadobjekt zwischen aufeinander folgenden Erstellung und Beendigung des Threads Ausführungen erneut verwendet werden soll.  
  
##  <a name="cwinthread"></a>CWinThread::CWinThread  
 Erstellt ein `CWinThread`-Objekt.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Hinweise  
 Um die Ausführung des Threads zu starten, rufen Sie die [CreateThread](#createthread) Member-Funktion. Erstellen Sie in der Regel Threads durch Aufruf von [AfxBeginThread](http://msdn.microsoft.com/library/e9e8684d-24f7-4599-8fdf-1f4f560a753b), der dieser Konstruktor aufgerufen und `CreateThread`.  
  
##  <a name="exitinstance"></a>CWinThread::ExitInstance  
 Vom Framework von überschriebenen eine selten aufgerufen [ausführen](#run) Member-Funktion, um diese Instanz des Threads zu beenden oder einen Aufruf von [InitInstance](#initinstance) schlägt fehl.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Exitcode des Threads; 0 gibt keine Fehler an, und Werte größer als 0 Fehler an. Dieser Wert kann abgerufen werden, durch Aufrufen von [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht diese Memberfunktion überall aber noch innerhalb der **ausführen** Member-Funktion. Diese Memberfunktion ist nur in der Benutzeroberflächen-Threads verwendet.  
  
 Die standardmäßige Implementierung dieser Funktion löscht den `CWinThread` Objekt, wenn [M_bAutoDelete](#m_bautodelete) ist **TRUE**. Überschreiben Sie diese Funktion, um zusätzliche Bereinigung auszuführen, wenn der Thread beendet wird. Die Implementierung von `ExitInstance` sollten der Basisklasse aufrufen, nachdem der Code ausgeführt wird.  
  
##  <a name="getmainwnd"></a>CWinThread::GetMainWnd  
 Wenn Ihre Anwendung einen OLE-Server ist, rufen Sie diese Funktion rufen Sie einen Zeiger auf das aktiven Hauptfenster der Anwendung und nicht direkt auf die `m_pMainWnd` Member des Anwendungsobjekts.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Funktion gibt einen Zeiger auf einen von zwei Typen von Windows. Der Thread ist Teil des OLE-Server und verfügt über ein Objekt, das in-Place aktiv in einer aktiven Container ist, gibt diese Funktion die [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) Datenmember der `CWinThread` Objekt.  
  
 Diese Funktion gibt zurück, wenn kein Objekt, das innerhalb eines Containers in-Place aktiv ist oder die Anwendung kein OLE-Server ist, der [M_pMainWnd](#m_pmainwnd) -Datenmember des Thread-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Für Benutzeroberflächen-Threads, dies entspricht dem direkten verweisen auf die `m_pActiveWnd` Member des Anwendungsobjekts.  
  
 Wenn es sich bei der Anwendung nicht um einen OLE-Server handelt, entspricht das Aufrufen dieser Funktion dem direkten Verweisen auf den `m_pMainWnd`-Member des Anwendungsobjekts.  
  
 Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.  
  
##  <a name="getthreadpriority"></a>CWinThread::GetThreadPriority  
 Ruft die aktuelle Prioritätsebene des Threads ab.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Prioritätsebene innerhalb seiner Prioritätsklasse. Der zurückgegebene Wert ist eine der folgenden, von der höchsten Priorität in absteigender Reihenfolge aufgelistet:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST FEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Weitere Informationen zu diesen Prioritäten, finden Sie unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="initinstance"></a>CWinThread::InitInstance  
 `InitInstance`muss überschrieben werden, um jede neue Instanz eines Benutzeroberflächen-Threads zu initialisieren.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie in der Regel `InitInstance` Aufgaben, die ausgeführt werden müssen, wenn ein Thread erstellt wird.  
  
 Diese Memberfunktion ist nur in der Benutzeroberflächen-Threads verwendet. Initialisierung von Arbeitsthreads in die Steuerungsfunktion übergeben ausführen [AfxBeginThread](application-information-and-management.md#afxbeginthread).  
  
##  <a name="isidlemessage"></a>CWinThread::IsIdleMessage  
 Überschreiben Sie diese Funktion zu **OnIdle** aufgerufen wird, nachdem bestimmte Nachrichten generiert werden.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Verweist auf die aktuelle Nachricht verarbeitet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL `OnIdle` aufgerufen werden soll, nach der Verarbeitung Meldung, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung nicht aufgerufen **OnIdle** nach redundante Maus und Nachrichten von blinkt, Caretzeichen generiert.  
  
 Wenn eine Anwendung einen kurze Zeitgeber erstellt hat **OnIdle** aufgerufen wird häufig Leistungsprobleme verursacht. Überschreiben Sie zur Verbesserung der Leistung einer solchen Anwendung des `IsIdleMessage` in der Anwendungsverzeichnis `CWinApp`-abgeleiteten Klasse zu prüfen, ob `WM_TIMER` Nachrichten wie folgt:  
  
 [!code-cpp[NVC_MFCDocView&#189;](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 Behandlung von `WM_TIMER` auf diese Weise wird die Leistung verbessert, kurze Zeitgeber verwenden.  
  
##  <a name="m_bautodelete"></a>CWinThread::m_bAutoDelete  
 Gibt an, ob das `CWinThread`-Objekt der Threadbeendigung automatisch gelöscht werden soll.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_bAutoDelete` -Datenmember ist eine öffentliche Variable des Typs **BOOL**.  
  
 Der Wert von `m_bAutoDelete` beeinflusst nicht, wie das zugrunde liegende Threadhandle geschlossen wird. Das Threadhandle wird immer geschlossen, wenn das `CWinThread`-Objekt zerstört wird.  
  
##  <a name="m_hthread"></a>CWinThread::m_hThread  
 Handle für den Thread beigefügten `CWinThread`.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hThread` -Datenmember ist eine öffentliche Variable des Typs `HANDLE`. Es ist nur gültig, wenn derzeit zugrunde liegenden Thread vorhanden ist.  
  
##  <a name="m_nthreadid"></a>CWinThread::m_nThreadID  
 ID des Threads beigefügten `CWinThread`.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die **M_nThreadID** -Datenmember ist eine öffentliche Variable des Typs `DWORD`. Es ist nur gültig, wenn derzeit zugrunde liegenden Thread vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [AfxGetThread](application-information-and-management.md#afxgetthread).  
  
##  <a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd  
 Verwenden Sie dieses Datenelement, um einen Zeiger auf die aktive Fensterobjekt des Threads speichern.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class Library wird automatisch den Thread beendet, wenn das Fenster mit den bezeichnet `m_pActiveWnd` geschlossen wird. Wenn dieser Thread auf den primären Thread für eine Anwendung ist, wird auch die Anwendung beendet. Wenn der Datenmember ist **NULL**, das aktive Fenster für der Anwendungsverzeichnis `CWinApp` , Objekt geerbt werden. `m_pActiveWnd`ist eine öffentliche Variable des Typs **CWnd\***.  
  
 Üblicherweise legen Sie diese Membervariable beim Überschreiben von `InitInstance`. In einem Arbeitsthread wird der Wert dieses Datenelement aus seinem übergeordneten Thread geerbt.  
  
##  <a name="m_pmainwnd"></a>CWinThread:: M_pmainwnd  
 Verwenden Sie dieses Datenelement zum Speichern eines Zeigers auf Ihr Thread main Window-Objekt.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class Library wird automatisch den Thread beendet, wenn das Fenster mit den bezeichnet `m_pMainWnd` geschlossen wird. Wenn dieser Thread auf den primären Thread für eine Anwendung ist, wird auch die Anwendung beendet. Wenn der Datenmember ist **NULL**, das Hauptfenster der Anwendung `CWinApp` Objekt wird verwendet, um zu bestimmen, wann der Thread beendet. `m_pMainWnd`ist eine öffentliche Variable des Typs **CWnd\***.  
  
 Üblicherweise legen Sie diese Membervariable beim Überschreiben von `InitInstance`. In einem Arbeitsthread wird der Wert dieses Datenelement aus seinem übergeordneten Thread geerbt.  
  
##  <a name="onidle"></a>CWinThread::OnIdle  
 Überschreiben Sie diese Member-Funktion, um die Zeit im Leerlauf Verarbeitung durchzuführen.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Parameter  
 `lCount`  
 Ein Zähler jedes Mal erhöht `OnIdle` wird aufgerufen, wenn der Thread-Nachrichtenwarteschlange leer ist. Dieser Zähler wird jedes Mal auf 0 zurückgesetzt, wenn eine neue Nachricht verarbeitet wird. Sie können die `lCount` Parameter zum Bestimmen der relativen Dauer der Thread im Leerlauf ohne eine Nachricht verarbeitet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL erhalten mehr Leerlaufzeiten; 0, wenn keine weiteren Leerlaufzeiten erforderlich ist.  
  
### <a name="remarks"></a>Hinweise  
 `OnIdle`wird in der Standardeinstellung Nachrichtenschleife aufgerufen werden, wenn der Thread-Nachrichtenwarteschlange leer ist. Verwenden Sie überschreiben, um einen eigenen Hintergrund Aufgaben im Leerlauf-Handler aufzurufen.  
  
 `OnIdle`sollte zurückgeben 0 an, um anzugeben, dass keine zusätzlichen Leerlaufzeiten erforderlich ist. Die `lCount` Parameter wird jedes Mal inkrementiert `OnIdle` wird aufgerufen, wenn die Nachrichtenwarteschlange leer ist und wird jedes Mal eine neue Nachricht verarbeitet wird auf 0 zurückgesetzt. Sie können die anderen im Leerlauf Routinen, die basierend auf diese Anzahl aufrufen.  
  
 Die standardmäßige Implementierung von dieser Memberfunktion wird die temporäre Objekte und nicht verwendete DLL-Dateien aus dem Speicher freigegeben.  
  
 Diese Memberfunktion ist nur in der Benutzeroberflächen-Threads verwendet.  
  
 Da die Anwendung Nachrichten erst verarbeiten kann `OnIdle` zurückgegeben wird, führen Sie langwierige Aufgaben in dieser Funktion.  
  
##  <a name="operator_handle"></a>CWinThread::operator HANDLE  
 Ruft das Handle des dem `CWinThread` Objekt.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Falls erfolgreich, das Handle für das Threadobjekt. andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie den Griff, um Windows-APIs direkt aufzurufen.  
  
##  <a name="postthreadmessage"></a>CWinThread::PostThreadMessage  
 Wird aufgerufen, um eine benutzerdefinierte Meldung zu einem anderen Beitrag `CWinThread` Objekt.  
  
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
>  Beim Aufrufen der Windows [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) Funktion innerhalb einer MFC-Anwendung, die MFC-Nachricht Handler nicht aufgerufen werden. Weitere Informationen finden Sie im Knowledge Base-Artikel "PRB: MFC-Message-Handler nicht aufgerufen, mit PostThreadMessage()" (Q142415).  
  
##  <a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage  
 Überschreiben Sie diese Funktion Fenster, Nachrichten zu filtern, bevor sie an die Windows-Funktionen verteilt wurden [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `pMsg`  
 Verweist auf eine [MSG-Struktur](../../mfc/reference/msg-structure1.md) , enthält die zu verarbeitende Meldung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Meldung in vollständig verarbeitet wurde `PreTranslateMessage` und nicht weiter verarbeitet werden soll. 0 (null), wenn die Nachricht auf die übliche Weise verarbeitet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist nur in der Benutzeroberflächen-Threads verwendet.  
  
##  <a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter  
 Hookfunktion für das Framework ruft diese Memberfunktion zum Filtern und bestimmte Windows-Meldungen zu reagieren.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Parameter  
 `code`  
 Gibt einen Hookcode. Diese Memberfunktion verwendet der Code zum Bestimmen der Verarbeitung`lpMsg.`  
  
 `lpMsg`  
 Ein Zeiger auf ein Windows [MSG-Struktur](../../mfc/reference/msg-structure1.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Nachricht verarbeitet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Hookfunktion verarbeitet Ereignisse, bevor sie die Anwendung normal-Nachricht gesendet werden verarbeitet.  
  
 Wenn Sie diese erweiterte Funktion überschreiben, müssen Sie die Basisklassenversion zum Verwalten des Frameworks aufrufen Verarbeitung zu verknüpfen.  
  
##  <a name="processwndprocexception"></a>CWinThread::ProcessWndProcException  
 Das Framework ruft diese Memberfunktion auf, wenn der Handler eine Nachricht des Threads oder Befehlshandler ausgelöste Ausnahme nicht abfängt.  
  
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
 – 1, wenn ein `WM_CREATE` Ausnahme wird generiert, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion nicht direkt.  
  
 Die standardmäßige Implementierung von dieser Memberfunktion behandelt nur die Ausnahmen, die von den folgenden Nachrichten generiert:  
  
|Befehl|Aktion|  
|-------------|------------|  
|`WM_CREATE`|Ein Fehler auf.|  
|`WM_PAINT`|Überprüfen Sie die betroffenen Fenster, sodass eine andere `WM_PAINT` Nachricht generiert werden.|  
  
 Überschreiben Sie diese Memberfunktion zum globalen Behandlung für die Ausnahmen bereitzustellen. Rufen Sie die Basisfunktionalität nur, wenn Sie das Standardverhalten anzeigen möchten.  
  
 Diese Memberfunktion ist nur in Threads verwendet, die über ein Nachrichtensystem verfügen.  
  
##  <a name="pumpmessage"></a>CWinThread::PumpMessage  
 Enthält die Meldungsschleife des Threads.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Hinweise  
 `PumpMessage`enthält die Meldungsschleife des Threads. **PumpMessage** wird aufgerufen, indem Sie `CWinThread` zum Weiterleiten von Nachrichten für den Thread. Rufen Sie `PumpMessage` direkt zum Erzwingen von Nachrichten verarbeitet werden, oder Sie können `PumpMessage` sein Standardverhalten zu ändern.  
  
 Aufrufen von `PumpMessage` direkt und sein Standardverhalten zu überschreiben, wird nur für fortgeschrittene Benutzer empfohlen.  
  
##  <a name="resumethread"></a>CWinThread:: ResumeThread  
 Wird aufgerufen, um die Ausführung eines Threads fortzusetzen, indem Sie angehalten wurde, der [SuspendThread](#suspendthread) Member-Funktion oder einen Thread erstellt, mit der **CREATE_SUSPENDED** Flag.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Thread die vorherigen Unterbrechungszähler bei Erfolg; `0xFFFFFFFF` andernfalls. Wenn der Rückgabewert&0; (null) ist, wurde der aktuelle Thread nicht angehalten. Ist der Rückgabewert eine, wird der Thread unterbrochen wurde, aber jetzt neu gestartet. Rückgabewerte, die größer als ein Mittel, Threads bleibt angehalten.  
  
### <a name="remarks"></a>Hinweise  
 Der Unterbrechungszähler des aktuellen Threads wird um eins reduziert. Wenn der Unterbrechungszähler reduziert ist&0; (null), der Thread fortgesetzt; andernfalls bleibt der Thread angehalten.  
  
##  <a name="run"></a>Hauptmeldungsschleife  
 Bietet eine Standard-Meldungsschleife für Benutzeroberflächen-Threads.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `int` -Wert, der vom Thread zurückgegeben wird. Dieser Wert kann abgerufen werden, durch Aufrufen von [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190).  
  
### <a name="remarks"></a>Hinweise  
 **Führen Sie** reserviert und Windows-Meldungen sendet, bis die Anwendung empfängt eine [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) Nachricht. Wenn der Thread-Nachrichtenwarteschlange derzeit keine Nachrichten enthält **ausführen** Aufrufe `OnIdle` leerlaufzeitverarbeitung ausführen. Eingehende Nachrichten werden an die [PreTranslateMessage](#pretranslatemessage) Memberfunktion zur speziellen Verarbeitung und dann in der Windows-Funktion [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) für die Standardtastatur Übersetzung. Abschließend die [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktion wird aufgerufen.  
  
 **Führen Sie** wird selten überschrieben werden, Sie können jedoch überschreiben, um besonderes Verhalten zu implementieren.  
  
 Diese Memberfunktion ist nur in der Benutzeroberflächen-Threads verwendet.  
  
##  <a name="setthreadpriority"></a>CWinThread::SetThreadPriority  
 Diese Funktion legt den Grad der Priorität des aktuellen Threads innerhalb seiner Prioritätsklasse.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>Parameter  
 `nPriority`  
 Gibt die neue Prioritätsebene innerhalb seiner Prioritätsklasse. Dieser Parameter muss einer der folgenden Werte an, von der höchsten Priorität in absteigender Reihenfolge aufgelistet sein:  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST FEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 Weitere Informationen zu diesen Prioritäten, finden Sie unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Es kann nur aufgerufen werden, nachdem [CreateThread](#createthread) erfolgreich zurückgegeben wird.  
  
##  <a name="suspendthread"></a>CWinThread:: SuspendThread  
 Inkrementiert den aktuellen Thread den Unterbrechungszähler.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Thread die vorherigen Unterbrechungszähler bei Erfolg; `0xFFFFFFFF` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Weist jedem Thread Unterbrechungszähler über&0; (null), wird dieser Thread nicht ausgeführt. Der Thread kann fortgesetzt werden, durch Aufrufen der [ResumeThread](#resumethread) Member-Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)

