---
title: Anwendungsinformationen und Anwendungsverwaltung
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 52e6dbaa07fa8343a07533f071d538d9f76b0f61
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741169"
---
# <a name="application-information-and-management"></a>Anwendungsinformationen und Anwendungsverwaltung

Wenn Sie eine Anwendung schreiben, erstellen Sie ein einzelnes von [CWinApp](../../mfc/reference/cwinapp-class.md)abgeleitetes Objekt. Manchmal möchten Sie möglicherweise Informationen zu diesem Objekt von außerhalb des `CWinApp`von abgeleiteten Objekts erhalten. Oder Sie benötigen möglicherweise Zugriff auf andere globale "Mananger"-Objekte.

Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen, die Ihnen bei der Ausführung dieser Aufgaben helfen:

### <a name="application-information-and-management-functions"></a>Anwendungsinformationen und Verwaltungsfunktionen

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Erstellt einen neuen Thread.|
|[AfxContextMenuManager](#afxcontextmenumanager)|Zeiger auf den globalen [Kontextmenü-Manager](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Beendet den aktuellen Thread.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Durchläuft die Ressourcen Kette und ermittelt eine bestimmte Ressource anhand der Ressourcen-ID und des Ressourcentyps. |
|[AfxFreeLibrary](#afxfreelibrary)|Dekremente den Verweis Zähler des geladenen DLL-Moduls (Dynamic-Link Library). Wenn der Verweis Zähler Null erreicht, wird das Modul nicht zugeordnet.|
|[AfxGetApp](#afxgetapp)|Gibt einen Zeiger auf das einzelne `CWinApp` Objekt der Anwendung zurück.|
|[AfxGetAppName](#afxgetappname)|Gibt eine Zeichenfolge zurück, die den Namen der Anwendung enthält.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Gibt eine HINSTANCE zurück, die diese Instanz der Anwendung darstellt.|
|[AfxGetMainWnd](#afxgetmainwnd)|Gibt einen Zeiger auf das aktuelle Hauptfenster einer nicht-OLE-Anwendung oder das direkte Rahmen Fenster einer Serveranwendung zurück.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Verwenden Sie diese Funktion, um zu bestimmen, ob die Anwendung den Registrierungs Zugriff auf den Knoten **HKEY_CURRENT_USER** ( **HKCU**) umleitet.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Gibt eine HINSTANCE an die Quelle der Standard Ressourcen der Anwendung zurück. Verwenden Sie diese Informationen, um direkt auf die Ressourcen der Anwendung zuzugreifen.|
|[AfxGetThread](#afxgetthread)|Ruft einen Zeiger auf das aktuelle [CWinThread](../../mfc/reference/cwinthread-class.md) -Objekt ab.|
|[AfxInitRichEdit](#afxinitrichedit)|Initialisiert das Rich Edit-Steuerelement der Version 1,0 für die Anwendung.|
|[AfxInitRichEdit2](#afxinitrichedit2)|Initialisiert das Rich Edit-Steuerelement der Version 2,0 und höher für die Anwendung.|
|[Afxisextendedframeclass](#afxisextendedframeclass)|Bestimmt, ob das jeweilige Fenster ein erweitertes Rahmenobjekt ist.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Bestimmt, ob das angegebene Fenster ein Toolbar-Objekt ist.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Zeiger auf den globalen [Tastatur-Manager](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|Ordnet ein dll-Modul zu und gibt ein Handle zurück, das zum Abrufen der Adresse einer DLL-Funktion verwendet werden kann.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Zeiger auf den globalen [Tearoff-Menü-Manager](cmenutearoffmanager-class.md).|
|[Afxmouscmanager](#afxmousemanager)|Zeiger auf den globalen [Maus-Manager](cmousemanager-class.md).|
|[Afxregisterclass](#afxregisterclass)|Registriert eine Fenster Klasse in einer DLL, die MFC verwendet.|
|[AfxRegisterWndClass](#afxregisterwndclass)|Registriert eine Windows-Fenster Klasse, um die automatisch von MFC registrierten Registrierungen zu ergänzen.|
|[Afxsetperuserregistration](#afxsetperuserregistration)|Legt fest, ob die Anwendung den Registrierungs Zugriff auf den Knoten **HKEY_CURRENT_USER** ( **HKCU**) umleitet.|
|[Afxort tresourcehandle](#afxsetresourcehandle)|Legt den HINSTANCE-Handle fest, in dem die Standard Ressourcen der Anwendung geladen werden.|
|[AfxShellManager](#afxshellmanager)|Zeiger auf den Global [Shell Manager](cshellmanager-class.md). |
|[AfxSocketInit](#afxsocketinit)|Wird in einer `CWinApp::InitInstance` außer Kraft Setzung aufgerufen, um Windows Sockets zu initialisieren.|
|[AfxUserToolsManager](#afxusertoolsmanager)|Zeiger auf den globalen [benutzertool-Manager](cusertoolsmanager-class.md).|
|[AfxWinInit](#afxwininit)|Wird von der MFC- `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) -Initialisierung einer GUI-basierten Anwendung aufgerufen, um MFC zu initialisieren. Muss direkt für Konsolen Anwendungen aufgerufen werden, die MFC verwenden.|

##  <a name="afxbeginthread"></a>AfxBeginThread

Rufen Sie diese Funktion auf, um einen neuen Thread zu erstellen.

```
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>Parameter

*pfnThreadProc*<br/>
Zeigt auf die Steuerungsfunktion für den Arbeitsthread. Lässt keine NULL-Werte zu. Diese Funktion muss wie folgt deklariert werden:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
Der RUNTIME_CLASS eines Objekts, das von [CWinThread](../../mfc/reference/cwinthread-class.md)abgeleitet wurde.

*pParam*<br/>
-Parameter, der an die Steuerungsfunktion übergeben werden soll, wie im-Parameter für die Funktionsdeklaration in *pfnthreadproc*gezeigt.

*nPriority*<br/>
Die gewünschte Priorität des Threads. Eine vollständige Liste und Beschreibung der verfügbaren Prioritäten finden Sie unter [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) in der Windows SDK.

*nStackSize*<br/>
Gibt die Stapelgröße für den neuen Thread in Bytes an. Mit dem Wert 0 wird die Stapelgröße standardmäßig so groß wie die des erstellenden Threads.

*dwCreateFlags*<br/>
Gibt ein zusätzliches Flag an, das die Erstellung des Threads steuert. Dieses Flag kann einen von zwei Werten enthalten:

- CREATE_SUSPENDED starten Sie den Thread mit einer Unterbrechungs Anzahl von 1. Verwenden Sie CREATE_SUSPENDED, wenn Sie alle Elementdaten des `CWinThread` Objekts initialisieren möchten, z. b. [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) oder alle Member der abgeleiteten Klasse, bevor der Thread gestartet wird. Verwenden Sie nach Abschluss der Initialisierung [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) , um den Thread zu starten, der ausgeführt wird. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.

- **0** starten Sie den Thread sofort nach der Erstellung.

*lpSecurityAttrs*<br/>
Verweist auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) -Struktur, die die Sicherheits Attribute für den Thread angibt. Wenn der Wert NULL ist, werden dieselben Sicherheits Attribute wie der erstellende Thread verwendet. Weitere Informationen zu dieser Struktur finden Sie in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neu erstellte Thread Objekt oder NULL, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Mit der ersten Form von `AfxBeginThread` wird ein Arbeitsthread erstellt. Mit der zweiten Form wird ein Thread erstellt, der als Benutzeroberflächenthread oder als Arbeitsthread dienen kann.

`AfxBeginThread`erstellt ein neues `CWinThread` -Objekt, ruft seine " [foratethread](../../mfc/reference/cwinthread-class.md#createthread) "-Funktion auf, um die Ausführung des Threads zu starten, und gibt einen Zeiger auf den Thread zurück. Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte. Um den Thread zu beenden, müssen Sie [AfxEndThread](#afxendthread) aus dem Thread heraus abrufen oder von der Steuerungsfunktion des Arbeitsthreads zurückgeben.

Multithreading muss durch die Anwendung aktiviert werden, andernfalls erzeugt diese Funktion einen Fehler. Weitere Informationen zum Aktivieren von Multithreading finden Sie unter " [/MD", "/MT", "/LD" (Lauf Zeit Bibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) unter " *visuelle C++ Compileroptionen*".

Weitere Informationen zu finden `AfxBeginThread`Sie in den Artikeln [Multithreading: Erstellen von](../../parallel/multithreading-creating-worker-threads.md) Arbeitsthreads [und Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach).

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

## <a name="afxcontextmenumanager"></a>Afxcontextmenumanager

Zeiger auf den globalen [Kontextmenü-Manager](ccontextmenumanager-class.md).

### <a name="syntax"></a>Syntax

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxcontextmenumanager. h

##  <a name="afxendthread"></a>AfxEndThread

Diese Funktion wird aufgerufen, um den derzeit ausgeführten Thread zu beenden.

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Parameter

*nExitCode*<br/>
Gibt den Exitcode des Threads an.

*bDelete*<br/>
Löscht das Thread Objekt aus dem Arbeitsspeicher.

### <a name="remarks"></a>Hinweise

Muss innerhalb des Threads aufgerufen werden, der beendet werden soll.

Weitere Informationen zu `AfxEndThread`finden Sie im Artikel [Multithreading: Beenden von](../../parallel/multithreading-terminating-threads.md)Threads.

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Verwenden `AfxFindResourceHandle` Sie, um die Ressourcen Kette zu durchlaufen und eine bestimmte Ressource nach Ressourcen-ID und Ressourcentyp zu suchen.

### <a name="syntax"></a>Syntax

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Ressourcen-ID enthält.
*lpszType*<br/>
Ein Zeiger auf den Ressourcentyp. Eine Liste der Ressourcentypen finden Sie unter [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea) in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Modul, das die Ressource enthält.

### <a name="remarks"></a>Hinweise

`AfxFindResourceHandle`sucht die jeweilige Ressource und gibt ein Handle für das Modul zurück, das die Ressource enthält. Die Ressource kann in einer beliebigen MFC-Erweiterungs-DLL enthalten sein, die Sie geladen haben. `AfxFindResourceHandle`Gibt an, welche Ressource über die Ressource verfügt.

Die Module werden in dieser Reihenfolge durchsucht:

1. Das Hauptmodul (wenn es sich um eine MFC-Erweiterungs-DLL handelt).

1. Nicht-Systemmodule.

1. Sprachspezifische Module.

1. Das Hauptmodul (wenn es sich um eine System-DLL handelt).

1. System Module.

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="afxfreelibrary"></a>AfxFreeLibrary

Sowohl `AfxFreeLibrary` als `AfxLoadLibrary` auch behalten einen Verweis Zähler für jedes geladene Bibliotheks Modul bei.

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Parameter

*hInstLib*<br/>
Ein Handle des geladenen Bibliotheks Moduls. [AfxLoadLibrary](#afxloadlibrary) gibt dieses Handle zurück.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Funktion erfolgreich ausgeführt wird. andernfalls false.

### <a name="remarks"></a>Hinweise

`AfxFreeLibrary`Dekremente den Verweis Zähler des geladenen DLL-Moduls (Dynamic-Link Library). Wenn der Verweis Zähler Null erreicht, wird das Modul nicht mehr dem Adressraum des aufrufenden Prozesses zugeordnet, und das Handle ist nicht mehr gültig. Dieser Verweis Zähler wird jedes Mal inkrementiert, wenn `AfxLoadLibrary` aufgerufen wird.

Vor dem Entfernen der Zuordnung eines Bibliotheks Moduls ermöglicht das System der dll, die von den Prozessen verwendeten Prozesse zu trennen. Dadurch haben Sie die Möglichkeit, im Namen des aktuellen Prozesses zugeordnete Ressourcen zu bereinigen. Nachdem die Einstiegspunkt Funktion zurückgegeben wurde, wird das Bibliotheks Modul aus dem Adressraum des aktuellen Prozesses entfernt.

Verwenden `AfxLoadLibrary` Sie, um ein dll-Modul zuzuordnen.

Stellen Sie sicher, `AfxFreeLibrary` dass `AfxLoadLibrary` Sie und verwenden (anstelle der `FreeLibrary` Win32 `LoadLibrary`-Funktionen und), wenn Ihre Anwendung mehrere Threads verwendet. Durch `AfxLoadLibrary` die `AfxFreeLibrary` Verwendung von und wird sichergestellt, dass beim Laden und Entladen der MFC-Erweiterungs-DLL der globale MFC-Status durch das Starten und Herunterfahren des Codes beschädigt wird.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [AfxLoadLibrary](#afxloadlibrary).

### <a name="requirements"></a>Anforderungen

  **Header** afxdll_. h

##  <a name="afxgetapp"></a>AfxGetApp

Der Zeiger, der von dieser Funktion zurückgegeben wird, kann für den Zugriff auf Anwendungsinformationen verwendet werden, wie z. b. den hauptnachrichtendispatchcode oder das oberste Fenster

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das einzelne `CWinApp` Objekt für die Anwendung.

### <a name="remarks"></a>Hinweise

Wenn diese Methode NULL zurückgibt, kann dies darauf hinweisen, dass das Hauptfenster der Anwendung noch nicht vollständig initialisiert wurde. Dies kann auch auf ein Problem hinweisen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxgetappname"></a>Afxgetappname

Die von dieser Funktion zurückgegebene Zeichenfolge kann für Diagnosemeldungen oder als Stamm für temporäre Zeichen folgen Namen verwendet werden.

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Rückgabewert

Eine mit NULL endenden Zeichenfolge, die den Namen der Anwendung enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxgetinstancehandle"></a>AfxGetInstanceHandle

Diese Funktion ermöglicht das Abrufen des Instanzhandles der aktuellen Anwendung.

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Rückgabewert

Eine HINSTANCE zur aktuellen Instanz der Anwendung. Wenn Sie innerhalb einer DLL aufgerufen wird, die mit der Version von MFC für die Aktualisierung von MFC verknüpft ist, wird eine HINSTANCE zur dll zurückgegeben.

### <a name="remarks"></a>Hinweise

`AfxGetInstanceHandle`gibt immer die HINSTANCE der ausführbaren Datei zurück (. EXE), es sei denn, Sie werden innerhalb einer DLL aufgerufen, die mit der Version von MFC von rdll verknüpft ist. In diesem Fall wird eine HINSTANCE an die dll zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxgetmainwnd"></a>Afxgetmainwnd

Wenn es sich bei der Anwendung um einen OLE-Server handelt, rufen Sie diese Funktion auf, um einen Zeiger auf das aktive Hauptfenster der Anwendung abzurufen, statt direkt auf den [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) -Member des Anwendungs Objekts zu verweisen.

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Rückgabewert

Wenn der Server über ein Objekt verfügt, das innerhalb eines Containers direkt aktiv ist, und dieser Container aktiv ist, gibt diese Funktion einen Zeiger auf das Rahmenfensterobjekt zurück, das das direkt aktive Dokument enthält.

Wenn in einem Container kein Objekt vorhanden ist, das direkt aktiv ist, oder wenn es sich bei der Anwendung nicht um einen OLE-Server handelt, gibt diese Funktion einfach den *m_pMainWnd* des Anwendungs Objekts zurück.

Wenn `AfxGetMainWnd` vom primären Thread der Anwendung aufgerufen wird, wird das Hauptfenster der Anwendung gemäß den oben genannten Regeln zurückgegeben. Wenn die Funktion von einem sekundären Thread in der Anwendung aufgerufen wird, gibt die Funktion das Hauptfenster zurück, das dem aufrufenden Thread zugeordnet ist.

### <a name="remarks"></a>Hinweise

Wenn es sich bei Ihrer Anwendung nicht um einen OLE-Server handelt, entspricht das Aufrufen dieser Funktion dem direkten Verweis auf den *m_pMainWnd* -Member des Anwendungs Objekts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxgetperuserregistration"></a>Afxgetperuserregistration

Verwenden Sie diese Funktion, um zu bestimmen, ob die Anwendung den Registrierungs Zugriff auf den Knoten **HKEY_CURRENT_USER** ( **HKCU**) umleitet.

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass die Registrierungsinformationen an den HKCU-Knoten weitergeleitet werden. FALSE gibt an, dass die Anwendung Registrierungsinformationen in den Standard Knoten schreibt. Der Standard Knoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Hinweise

Wenn Sie die Registrierungs Umleitung aktivieren, leitet das Framework den Zugriff von **HKCR** auf **HKEY_CURRENT_USER\Software\Classes**um. Die Umleitung wirkt sich nur auf MFC-und ATL-Frameworks aus.

Um zu ändern, ob die Anwendung den Registrierungs Zugriff umleitet, verwenden Sie [afxsetperuserregistration](#afxsetperuserregistration).

### <a name="requirements"></a>Anforderungen

  **Header** afxstat_. h

##  <a name="afxgetresourcehandle"></a>AfxGetResourceHandle

Verwenden Sie das von dieser Funktion zurückgegebene HINSTANCE-handle, um direkt auf die Ressourcen der Anwendung zuzugreifen (z. b. `FindResource`in Aufrufen der Windows-Funktion).

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Rückgabewert

Ein HINSTANCE-handle, bei dem die Standard Ressourcen der Anwendung geladen werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxgetthread"></a>Afxgetthread

Mit dieser Funktion können Sie einen Zeiger auf das [CWinThread](../../mfc/reference/cwinthread-class.md) -Objekt abrufen, das den derzeit ausgeführten Thread darstellt.

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den derzeit ausgeführten Thread. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Muss innerhalb des gewünschten Threads aufgerufen werden.

> [!NOTE]
>  Wenn Sie ein MFC-Projekt portieren, `AfxGetThread` das von C++ den Visual-Versionen 4,2, 5,0 oder `AfxGetThread` 6,0 aufgerufen wird, ruft [AfxGetApp](#afxgetapp) auf, wenn kein Thread gefunden wird. In neueren Versionen des Compilers gibt NULL `AfxGetThread` zurück, wenn kein Thread gefunden wurde. Wenn Sie den Anwendungs Thread abrufen `AfxGetApp`möchten, müssen Sie den Befehl.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxinitrichedit"></a>Afxinitrchedit

Mit dieser Funktion können Sie das Rich Edit-Steuerelement (Version 1,0) für die Anwendung initialisieren.

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird aus Gründen der Abwärtskompatibilität bereitgestellt. Neue Anwendungen sollten [AfxInitRichEdit2](#afxinitrichedit2)verwenden.

`AfxInitRichEdit`lädt riched32. DLL zum Initialisieren der Version 1,0 des Rich Edit-Steuer Elements. Um die Versionen 2,0 und 3,0 des Rich Edit-Steuer Elements zu verwenden, Riched20. Die dll muss geladen werden. Dies wird durch einen [AfxInitRichEdit2](#afxinitrichedit2)-aufrufswert erreicht.

Um Rich Edit-Steuerelemente in vorhandenen C++ visuellen Anwendungen auf Version 2,0 zu aktualisieren, öffnen Sie die. RC-Datei als Text ändern Sie den Klassennamen jedes Rich-Edit-Steuer Elements von "RichEdit" in "RichEdit20a". Ersetzen Sie `AfxInitRichEdit` dann den-Befehl `AfxInitRichEdit2`durch.

Diese Funktion initialisiert außerdem die Bibliothek für allgemeine Steuerelemente, wenn die Bibliothek nicht bereits für den Prozess initialisiert wurde. Wenn Sie das Rich Edit-Steuerelement direkt in der MFC-Anwendung verwenden, sollten Sie diese Funktion verwenden, um sicherzustellen, dass MFC die Rich-Edit-Lauf Zeitsteuerung ordnungsgemäß initialisiert hat. Wenn Sie die Create-Methode von [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)aufzurufen, müssen Sie diese Funktion in der Regel nicht aufzurufen, aber in einigen Fällen ist es möglicherweise erforderlich.

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxinitrichedit2"></a>AfxInitRichEdit2

Mit dieser Funktion können Sie das Rich Edit-Steuerelement (Version 2,0 und höher) für die Anwendung initialisieren.

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird das Riched20 geladen. DLL und initialisieren Version 2,0 des Rich Edit-Steuer Elements. Wenn Sie die Create-Methode von [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md)oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)aufzurufen, müssen Sie diese Funktion in der Regel nicht aufzurufen, aber in einigen Fällen ist es möglicherweise erforderlich.

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

  ## <a name="afxisextendedframeclass"></a>Afxisextendedframeclass
Bestimmt, ob das jeweilige Fenster ein erweitertes Rahmenobjekt ist.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Ein Zeiger auf ein Objekt, das von `CWnd`abgeleitet wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das angegebene Fenster ein erweitertes Rahmen Objekt ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode gibt true zurück, wenn *pwnd* von einer der folgenden Klassen abgeleitet ist:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Diese Methode ist nützlich, wenn Sie überprüfen müssen, ob ein Funktions- oder Methodenparameter ein erweitertes Rahmenfenster ist.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

## <a name="afxismfctoolbar"></a>Afxismfctoolbar

Bestimmt, ob das angegebene Fenster ein Toolbar-Objekt ist.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Ein Zeiger auf ein Objekt, das von `CWnd`abgeleitet wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das angegebene Fenster ein Toolbar-Objekt ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode gibt `TRUE` zurück, wenn *pwnd* von `CMFCToolBar`abgeleitet ist. Diese Methode ist nützlich, wenn Sie überprüfen müssen, ob ein Funktions-oder Methoden `CMFCToolBar` Parameter ein-Objekt ist.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

## <a name="afxkeyboardmanager"></a>Afxkeyboardmanager

Zeiger auf den globalen [Tastatur-Manager](ckeyboardmanager-class.md).

### <a name="syntax"></a>Syntax

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxkeyboardmanager. h

##  <a name="afxloadlibrary"></a>AfxLoadLibrary

Verwenden `AfxLoadLibrary` Sie, um ein dll-Modul zuzuordnen.

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Parameter

*lpszModuleName*<br/>
Verweist auf eine mit NULL endenden Zeichenfolge, die den Namen des Moduls enthält (entweder eine. DLL oder. EXE-Datei). Der angegebene Name ist der Dateiname des Moduls.

Wenn die Zeichenfolge einen Pfad angibt, die Datei jedoch im angegebenen Verzeichnis nicht vorhanden ist, schlägt die Funktion fehl.

Wenn kein Pfad angegeben wird und die Dateinamenerweiterung weggelassen wird, wird die Standard Erweiterung angegeben. Die dll wird angehängt. Die Dateiname-Zeichenfolge kann jedoch ein nachfolgendes Punktzeichen (.) enthalten, um anzugeben, dass der Modulname keine Erweiterung hat. Wenn kein Pfad angegeben wird, sucht die Funktion in der folgenden Reihenfolge nach der Datei:

- Das Verzeichnis, in dem die Anwendung geladen wurde.

- Das aktuelle Verzeichnis.

- **Windows 95/98:** Das Systemverzeichnis von Windows. **Windows NT:** Das 32-Bit-Windows-System Verzeichnis. Der Name dieses Verzeichnisses lautet "System32".

- **Nur Windows NT:** Das 16-Bit-Windows-System Verzeichnis. Es gibt keine Win32-Funktion, die den Pfad dieses Verzeichnisses erhält, sondern durchsucht wird. Der Name dieses Verzeichnisses ist System.

- Das Windows-Verzeichnis.

- Die Verzeichnisse, die in der PATH-Umgebungsvariablen aufgelistet sind.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ein Handle für das Modul. Wenn die Funktion fehlschlägt, ist der Rückgabewert NULL.

### <a name="remarks"></a>Hinweise

Es gibt ein Handle zurück, das in [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) verwendet werden kann, um die Adresse einer DLL-Funktion zu erhalten. `AfxLoadLibrary`kann auch verwendet werden, um andere ausführbare Module zuzuordnen.

Jeder Prozess verwaltet einen Verweis Zähler für jedes geladene Bibliotheks Modul. Dieser Verweis Zähler wird jedes Mal inkrementiert, wenn `AfxLoadLibrary` aufgerufen wird, und wird bei `AfxFreeLibrary` jedem Aufruf von dekrementiert. Wenn der Verweis Zähler Null erreicht, wird das Modul nicht mehr dem Adressraum des aufrufenden Prozesses zugeordnet, und das Handle ist nicht mehr gültig.

Stellen Sie sicher, `AfxLoadLibrary` dass `AfxFreeLibrary` Sie und verwenden (anstelle der `LoadLibrary` Win32 `FreeLibrary`-Funktionen und), wenn Ihre Anwendung mehrere Threads verwendet und eine MFC-Erweiterungs-DLL dynamisch geladen wird. Mit `AfxLoadLibrary` und`AfxFreeLibrary` wird sichergestellt, dass der Code zum Starten und Herunterfahren, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL geladen und entladen wird, den globalen MFC-Zustand nicht beschädigt.

Die `AfxLoadLibrary` Verwendung von in einer Anwendung erfordert, dass Sie dynamisch mit der dll-Version von MFC verknüpfen. `AfxLoadLibrary`die Header Datei für, Afxdll_. h, ist nur enthalten, wenn MFC als DLL mit der Anwendung verknüpft ist. Dies ist beabsichtigt, da Sie eine Verknüpfung zur DLL-Version von MFC herstellen müssen, um MFC-Erweiterungs-DLLs zu verwenden oder zu erstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxdll_. h

## <a name="afxmenutearoffmanager"></a>Afxmenutearoffmanager

Zeiger auf den globalen [Tearoff-Menü-Manager](cmenutearoffmanager-class.md).

### <a name="syntax"></a>Syntax

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxmenutearoffmanager. h

## <a name="afxmousemanager"></a>Afxmouscmanager

Zeiger auf den globalen [Maus-Manager](cmousemanager-class.md).

### <a name="syntax"></a>Syntax

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxmousmanager. h

##  <a name="afxregisterclass"></a>Afxregisterclass

Verwenden Sie diese Funktion, um Fenster Klassen in einer DLL zu registrieren, die MFC verwendet.

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Parameter

*lpWndClass*<br/>
Ein Zeiger auf eine [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) -Struktur, die Informationen über die Fenster Klasse enthält, die registriert werden soll. Weitere Informationen zu dieser Struktur finden Sie in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Klasse erfolgreich registriert wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Wenn Sie diese Funktion verwenden, wird die Registrierung der-Klasse automatisch aufgehoben, wenn die DLL entladen wird.

In nicht-dll-Builds wird `AfxRegisterClass` der Bezeichner als ein Makro definiert, das der Windows- `RegisterClass`Funktion zugeordnet ist, da in einer Anwendung registrierte Klassen automatisch die Registrierung aufheben. Wenn Sie anstelle `AfxRegisterClass` von `RegisterClass`verwenden, kann Ihr Code ohne Änderung in einer Anwendung und in einer DLL verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxregisterwndclass"></a>AfxRegisterWndClass

Ermöglicht Ihnen das Registrieren Ihrer eigenen Fenster Klassen.

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Parameter

*nClassStyle*<br/>
Gibt den Windows-Klassen Stil oder eine Kombination von Stilen an, die mit dem bitweisen or **&#124;** ()-Operator für die Fenster Klasse erstellt wurden. Eine Liste der Klassen Stile finden Sie in der [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) -Struktur in der Windows SDK. Wenn der Wert NULL ist, werden die Standardwerte wie folgt festgelegt:

- Legt den mausstil auf CS_DBLCLKS fest, der Doppelklick-Meldungen an die Fenster Prozedur sendet, wenn der Benutzer auf die Maus doppelklickt.

- Legt die Art des Pfeil Cursors auf den Windows-Standard IDC_ARROW fest.

- Legt den Hintergrund Pinsel auf NULL fest, damit das Fenster seinen Hintergrund nicht löscht.

- Legt das Symbol auf das Windows-Logo Symbol Standard, waving-Flag fest.

*hcursor*<br/>
Gibt ein Handle für die zu installierende Cursor Ressource in jedem Fenster an, das aus der Fenster Klasse erstellt wird. Wenn Sie den Standardwert **0**verwenden, erhalten Sie den standardmäßigen IDC_ARROW-Cursor.

*hbrBackground*<br/>
Gibt ein Handle für die Pinsel Ressource an, die in jedem Fenster installiert werden soll, das aus der Fenster Klasse erstellt wird. Wenn Sie den Standardwert **0**(null) verwenden, verfügen Sie über einen NULL-Hintergrund Pinsel, und das Fenster löscht seinen Hintergrund standardmäßig nicht, während [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)verarbeitet wird.

*hIcon*<br/>
Gibt ein Handle für die Symbol Ressource an, die in jedem Fenster installiert werden soll, das aus der Fenster Klasse erstellt wird. Wenn Sie den Standardwert **0**verwenden, erhalten Sie das Windows-Logo-Symbol Standard, waving-Flag.

### <a name="return-value"></a>Rückgabewert

Eine mit NULL endenden Zeichenfolge, die den Klassennamen enthält. Sie können diesen Klassennamen an die `Create` Member-Funktion in `CWnd` oder andere von **CWnd**abgeleitete Klassen übergeben, um ein Fenster zu erstellen. Der Name wird vom Microsoft Foundation Class-Bibliothek generiert.

> [!NOTE]
>  Der Rückgabewert ist ein Zeiger auf einen statischen Puffer. Um diese Zeichenfolge zu speichern, weisen Sie `CString` Sie einer Variablen zu.

### <a name="remarks"></a>Hinweise

Das Microsoft Foundation Class-Bibliothek registriert automatisch mehrere Standardfenster Klassen für Sie. Wenn Sie Ihre eigenen Fenster Klassen registrieren möchten, können Sie diese Funktion aufzurufen.

Der Name, der für eine Klasse `AfxRegisterWndClass` registriert ist, hängt ausschließlich von den Parametern ab. Wenn Sie mehrmals `AfxRegisterWndClass` mit identischen Parametern aufzurufen, wird nur eine Klasse beim ersten-Befehl registriert. Bei nachfolgenden `AfxRegisterWndClass` Aufrufen von mit identischen Parametern wird lediglich der bereits registrierte Klassenname zurückgegeben.

Wenn Sie für `AfxRegisterWndClass` mehrere CWnd-abgeleitete Klassen mit identischen Parametern aufzurufen, anstatt eine separate Fenster Klasse für jede Klasse zu erhalten, gibt jede Klasse dieselbe Fenster Klasse frei. Dies kann Probleme verursachen, wenn der CS_CLASSDC-Klassen Stil verwendet wird. Anstatt mehrere CS_CLASSDC-Fenster Klassen zu verwenden, wird am Ende eine CS_CLASSDC-Fenster Klasse angezeigt C++ , und alle Fenster, die diese Klasse verwenden, verwenden denselben DC. Um dieses Problem zu vermeiden, müssen Sie [afxregisterclass](#afxregisterclass) aufrufen, um die-Klasse zu registrieren.

Weitere Informationen finden Sie [unter Technical Note TN001: Fenster Klassen Registrierung](../../mfc/tn001-window-class-registration.md) , um weitere Informationen zur Fenster Klassen Registrierung und `AfxRegisterWndClass` der-Funktion zu finden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

##  <a name="afxsetperuserregistration"></a>Afxsetperuserregistration

Legt fest, ob die Anwendung den Registrierungs Zugriff auf den Knoten **HKEY_CURRENT_USER** ( **HKCU**) umleitet.

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in TRUE gibt an, dass die Registrierungsinformationen an den HKCU-Knoten weitergeleitet werden. FALSE gibt an, dass die Anwendung Registrierungsinformationen in den Standard Knoten schreibt. Der Standard Knoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Hinweise

Vor Windows Vista verwendeten Anwendungen, die auf die Registrierung zugegriffen haben, in der Regel den Knoten **HKEY_CLASSES_ROOT** . Bei Windows Vista oder höheren Betriebssystemen müssen Sie jedoch eine Anwendung im erweiterten Modus ausführen, um in HKCR zu schreiben.

Diese Methode ermöglicht der Anwendung das Lesen und Schreiben in die Registrierung, ohne im erweiterten Modus ausgeführt zu werden, indem der Registrierungs Zugriff von HKCR auf HKCU umgeleitet wird. Weitere Informationen finden Sie unter [Linker Property Pages](../../build/reference/linker-property-pages.md).

Wenn Sie die Registrierungs Umleitung aktivieren, leitet das Framework den Zugriff von HKCR auf **HKEY_CURRENT_USER\Software\Classes**um. Die Umleitung wirkt sich nur auf MFC-und ATL-Frameworks aus.

Die Standard Implementierung greift auf die Registrierung unter HKCR zu.

### <a name="requirements"></a>Anforderungen

  **Header** afxstat_. h

##  <a name="afxsetresourcehandle"></a>Afxort tresourcehandle

Verwenden Sie diese Funktion, um das HINSTANCE-Handle festzulegen, das bestimmt, wo die Standard Ressourcen der Anwendung geladen werden.

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Parameter

*hInstResource*<br/>
Die-Instanz oder das Modul Handle für einen. Die exe-oder DLL-Datei, aus der die Ressourcen der Anwendung geladen werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

## <a name="afxshellmanager"></a>Afxshellmanager

Zeiger auf den Global [Shell Manager](cshellmanager-class.md).

### <a name="syntax"></a>Syntax

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxshellmanager. h

##  <a name="afxsocketinit"></a>AfxSocketInit

Mit dieser Funktion können Sie `CWinApp::InitInstance` in ihrer außer Kraft Setzung Windows-Sockets initialisieren.

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Parameter

*lpwsaData*<br/>
Ein Zeiger auf eine [wsadata](/windows/win32/api/winsock2/ns-winsock2-wsadata) -Struktur. Wenn *lpwsadata* nicht gleich NULL ist, wird die Adresse der `WSADATA` -Struktur `WSAStartup`durch den-Befehl ausgefüllt. Diese Funktion stellt außerdem sicher `WSACleanup` , dass für Sie aufgerufen wird, bevor die Anwendung beendet wird.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC-Anwendung verwenden `AfxSocketInit` , müssen Sie in jedem Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. Standardmäßig `AfxSocketInit` wird nur im primären Thread aufgerufen.

### <a name="requirements"></a>Anforderungen

  **Header** AfxSock. h

## <a name="afxusertoolsmanager"></a>Afxusertoolsmanager

Zeiger auf den globalen [benutzertool-Manager](cusertoolsmanager-class.md).

### <a name="syntax"></a>Syntax

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxusertoolsmanager. h

##  <a name="afxwininit"></a>Afxwininit

Diese Funktion wird von der MFC- `WinMain` Funktion aufgerufen, die im Rahmen der [CWinApp](../../mfc/reference/cwinapp-class.md) -Initialisierung einer GUI-basierten Anwendung zum Initialisieren von MFC aufgerufen wird.

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Parameter

*hInstance*<br/>
Das Handle des derzeit laufenden Moduls.

*hPrevInstance*<br/>
Ein Handle für eine vorherige Instanz der Anwendung. Bei einer Win32-basierten Anwendung ist dieser Parameter immer **null**.

*lpCmdLine*<br/>
Zeigt auf eine auf NULL endenden Zeichenfolge, die die Befehlszeile für die Anwendung angibt.

*nCmdShow*<br/>
Gibt an, wie das Hauptfenster einer GUI-Anwendung angezeigt wird.

### <a name="remarks"></a>Hinweise

Bei einer Konsolenanwendung, in der die von MFC bereit `WinMain` gestellte Funktion nicht verwendet wird, muss direkt aufgerufen `AfxWinInit` werden, um MFC zu initialisieren.

Wenn Sie sich `AfxWinInit` selbst anrufen, sollten Sie eine Instanz `CWinApp` einer Klasse deklarieren. Bei einer Konsolenanwendung können Sie sich entscheiden, nicht Ihre eigene Klasse von `CWinApp` abzuleiten und stattdessen eine Instanz von `CWinApp` direkt zu verwenden. Dieses Verfahren eignet sich, wenn Sie sich entschließen, alle Funktionen für Ihre Anwendung in ihrer Implementierung von **Main**zu belassen.

> [!NOTE]
>  Wenn ein Aktivierungs Kontext für eine Assembly erstellt wird, verwendet MFC eine manifest-Ressource, die vom Benutzermodul bereitgestellt wird. Der Aktivierungs Kontext wird in `AfxWinInit`erstellt. Weitere Informationen finden Sie [unter Unterstützung für Aktivierungs Kontexte im MFC-Modulstatus](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** AFXWIN. h

## <a name="see-also"></a>Siehe auch

[Makros und Globals](mfc-macros-and-globals.md)<br/>
[CWinApp-Klasse](cwinapp-class.md)<br/>
[CContextMenuManager-Klasse](ccontextmenumanager-class.md)<br/>
[CWnd-Klasse](cwnd-class.md)<br/>
[CFrameWndEx-Klasse](cframewndex-class.md)<br/>
[CMFCToolBar-Klasse](cmfctoolbar-class.md)<br/>
[CKeyboardManager-Klasse](ckeyboardmanager-class.md)<br/>
[CMenuTearOffManager-Klasse](cmenutearoffmanager-class.md)<br/>
[CMouseManager-Klasse](cmousemanager-class.md)<br/>
[CShellManager-Klasse](cshellmanager-class.md)<br/>
[CUserToolsManager-Klasse](cusertoolsmanager-class.md)
