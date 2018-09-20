---
title: Anwendungsinformationen und Anwendungsverwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b64e92eaca38743f0bc9de31f9be7684271c4674
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374358"
---
# <a name="application-information-and-management"></a>Anwendungsinformationen und Anwendungsverwaltung

Wenn Sie eine Anwendung schreiben, erstellen Sie eine einzelne [CWinApp](../../mfc/reference/cwinapp-class.md)-abgeleitetes Objekt. In einigen Fällen sollten Sie zum Abrufen von Informationen über dieses Objekt außerhalb der `CWinApp`-abgeleitetes Objekt. Oder benötigen Sie möglicherweise Zugriff auf andere globale "Manager"-Objekte.

Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen, damit Sie diese Aufgaben ausführen können:

### <a name="application-information-and-management-functions"></a>Anwendungsinformationen und Management-Funktionen

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|Erstellt einen neuen Thread.|
|[Globale AfxContextMenuManager](#afxcontextmenumanager)|Zeiger auf die globale [Kontext-Menü-Manager](ccontextmenumanager-class.md).|
|[AfxEndThread](#afxendthread)|Beendet den aktuellen Thread.|
|[AfxFindResourceHandle](#afxfindresourcehandle)|Führt die Ressourcenkette, und suchen Sie eine bestimmte Ressourcen nach Ressourcen-ID und den Ressourcentyp. |
|["AfxFreeLibrary"](#afxfreelibrary)|Dekrementiert den Verweiszähler des Moduls geladenen Dynamic Link Library (DLL); Wenn der Verweiszähler null erreicht, ist das Modul nicht zugeordnet.|
|[AfxGetApp](#afxgetapp)|Gibt ein Zeiger auf die Anwendung ist einzelne `CWinApp` Objekt.|
|[AfxGetAppName](#afxgetappname)|Gibt eine Zeichenfolge, die den Namen der Anwendung enthält.|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Gibt eine HINSTANCE, die dieser Instanz der Anwendung darstellt.|
|[AfxGetMainWnd](#afxgetmainwnd)|Gibt einen Zeiger auf das aktuelle "main" von einer nicht-OLE-Anwendung oder das direkte Rahmenfenster einer Serveranwendung zurück.|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Diese Funktion verwenden, um festzustellen, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|
|[AfxGetResourceHandle](#afxgetresourcehandle)|Gibt eine HINSTANCE der Quelle des Standard-Ressourcen der Anwendung zurück. Verwenden Sie diese Option, um die Ressourcen der Anwendung direkt zugreifen.|
|[AfxGetThread](#afxgetthread)|Ruft einen Zeiger auf die aktuelle [CWinThread](../../mfc/reference/cwinthread-class.md) Objekt.|
|[AfxInitRichEdit](#afxinitrichedit)|Initialisiert die Version 1.0 Rich-Edit-Steuerelement für die Anwendung an.|
|[AfxInitRichEdit2](#afxinitrichedit2)|Initialisiert die Version 2.0 oder höher Rich-Edit-Steuerelement für die Anwendung an.|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|Bestimmt, ob das jeweilige Fenster ein erweitertes Rahmenobjekt ist.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|Bestimmt, ob das angegebene Fenster ein Symbolleistenobjekt.|
|[AfxKeyboardManager](#afxkeyboardmanager)|Zeiger auf die globale [Tastatur Manager](ckeyboardmanager-class.md).|
|[AfxLoadLibrary](#afxloadlibrary)|Ordnet ein DLL-Modul, und gibt ein Handle, das zum Abrufen der Adresse einer DLL-Funktion verwendet werden kann.|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|Zeiger auf die globale [Tearoff-Menü-Manager](cmenutearoffmanager-class.md).|
|[AfxMouseManager](#afxmousemanager)|Zeiger auf die globale [Maus Manager](cmousemanager-class.md).|
|[AfxRegisterClass](#afxregisterclass)|Registriert eine Fensterklasse in eine DLL, die MFC verwendet.|
|[AfxRegisterWndClass](#afxregisterwndclass)|Registriert eine Windows-Fensterklasse als Ergänzung für die automatisch von MFC registriert.|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|
|[AfxSetResourceHandle](#afxsetresourcehandle)|Legt fest, dass das Handle HINSTANCE, in denen die Standardressourcen der Anwendung geladen werden.|
|[Globale AfxShellManager](#afxshellmanager)|Zeiger auf die globale [Shell-Manager](cshellmanager-class.md). |
|[AfxSocketInit](#afxsocketinit)|Wird aufgerufen, einem `CWinApp::InitInstance` überschreiben, um die Windows-Sockets nicht initialisieren.|
|[AfxUserToolsManager](#afxusertoolsmanager)|Zeiger auf die globale [Vorgesetzten des Benutzers Tools](cusertoolsmanager-class.md).|
|[AfxWinInit](#afxwininit)|Wird aufgerufen, von dem vom MFC bereitgestellten `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) Initialisierung einer GUI-basierte Anwendung, zum Initialisieren von MFC. Muss für konsolenanwendungen direkt aufgerufen werden, die MFC verwenden.|



##  <a name="afxbeginthread"></a>  AfxBeginThread

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
Zeigt auf die Steuerungsfunktion für den Arbeitsthread. Darf nicht NULL sein. Diese Funktion muss wie folgt deklariert werden:

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
RUNTIME_CLASS-Objektinstanz, die von abgeleiteten [CWinThread](../../mfc/reference/cwinthread-class.md).

*pParam*<br/>
Parameter, der an die Steuerungsfunktion übergeben werden, wie in den Parameter, um die Funktionsdeklaration in *PfnThreadProc*.

*nPriority*<br/>
Die gewünschte Priorität des Threads. Eine vollständige Liste und Beschreibung der verfügbaren Prioritäten, finden Sie unter [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) im Windows SDK.

*nStackSize*<br/>
Gibt die Stapelgröße für den neuen Thread in Bytes an. Mit dem Wert 0 wird die Stapelgröße standardmäßig so groß wie die des erstellenden Threads.

*dwCreateFlags*<br/>
Gibt ein zusätzliches Flag an, das die Erstellung des Threads steuert. Dieses Flag kann einen von zwei Werten enthalten:

- Der Thread wird mit dem Unterbrechungszähler eines CREATE_SUSPENDED gestartet. CREATE_SUSPENDED verwenden, wenn Sie beliebige Memberdaten des initialisieren möchten die `CWinThread` Objekt, z. B. [M_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) oder beliebige Member der abgeleiteten Klasse, befor der Thread ausgeführt wird. Sobald die Initialisierung abgeschlossen ist, verwenden [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) auf den Thread zu starten. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.

- **0** der Thread wird unmittelbar nach der Erstellung gestartet.

*lpSecurityAttrs*<br/>
Verweist auf eine [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Struktur, die Attribute für die Sicherheit für den Thread angibt. Wenn der Wert NULL ist, werden die gleichen Sicherheitsattribute als der erstellende Thread verwendet werden. Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.

### <a name="return-value"></a>Rückgabewert

Zeiger auf die neu erstellte Threadobjekt oder NULL, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Mit der ersten Form von `AfxBeginThread` wird ein Arbeitsthread erstellt. Mit der zweiten Form wird ein Thread erstellt, der als Benutzeroberflächenthread oder als Arbeitsthread dienen kann.

`AfxBeginThread` erstellt ein neues `CWinThread` Objekt, ruft seine [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) Funktion, um die Ausführung des Threads gestartet und gibt einen Zeiger auf den Thread. Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte. Um den Thread zu beenden, rufen [AfxEndThread](#afxendthread) aus in den Thread oder den Rückgabewert aus der Steuerungsfunktion des Arbeitsthreads.

Multithreading muss durch die Anwendung aktiviert werden, andernfalls erzeugt diese Funktion einen Fehler. Weitere Informationen zum Aktivieren des Multithreadings finden Sie unter [/MD, / MT, / ld (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) unter *Visual C++-Compileroptionen*.

Weitere Informationen zu `AfxBeginThread`, finden Sie in den Artikeln [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md) und [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach).

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

## <a name="afxcontextmenumanager"></a> Globale AfxContextMenuManager

Zeiger auf die globale [Kontext-Menü-Manager](ccontextmenumanager-class.md).

### <a name="syntax"></a>Syntax

```
CContextMenuManager* afxContextMenuManager;
```
### <a name="requirements"></a>Anforderungen

**Header:** afxcontextmenumanager.h

### <a name="see-also"></a>Siehe auch

[CContextMenuManager-Klasse](ccontextmenumanager-class.md)


##  <a name="afxendthread"></a>  AfxEndThread

Mit dieser Funktion können Sie der aktuell ausgeführten Thread beendet.

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>Parameter

*nExitCode*<br/>
Gibt den Exitcode des Threads an.

*bLöschen*<br/>
Löscht das Threadobjekt aus dem Arbeitsspeicher.

### <a name="remarks"></a>Hinweise

Müssen von innerhalb der zu beendenden Thread aufgerufen werden.

Weitere Informationen zu `AfxEndThread`, finden Sie im Artikel [Multithreading: Beenden von Threads](../../parallel/multithreading-terminating-threads.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
Verwendung `AfxFindResourceHandle` Ressourcenkette durchlaufen und einen bestimmten Typ von Ressourcen nach Ressourcen-ID und Ressourcen zu suchen.

### <a name="syntax"></a>Syntax

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```
### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, enthält die Ressourcen-ID.
*lpszType*<br/>
Ein Zeiger auf den Typ der Ressource. Eine Liste der Ressourcentypen, finden Sie unter [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Modul, das die Ressource enthält.

### <a name="remarks"></a>Hinweise

`AfxFindResourceHandle` Sucht die jeweilige Ressource aus, und gibt ein Handle für das Modul, das die Ressource enthält. Die Ressource möglicherweise in alle MFC-Erweiterungs-DLL, die Sie geladen haben. `AfxFindResourceHandle` Erfahren Sie, welche die Ressource besitzt.

Die Module werden in der folgenden Reihenfolge gesucht:

1. Das Hauptmodul (sofern es sich um eine MFC-Erweiterungs-DLL ist).

1. Nicht zum System-Module.

1. Sprachspezifische Module.

1. Das Hauptmodul (sofern es sich um ein System-DLL ist).

1. Systemmodule.

### <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)

##  <a name="afxfreelibrary"></a>  "AfxFreeLibrary"

Beide `AfxFreeLibrary` und `AfxLoadLibrary` verwalten einen Verweiszähler für jedes Modul geladenen Bibliothek.

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>Parameter

*hInstLib*<br/>
Ein Handle des geladenen Moduls. [AfxLoadLibrary](#afxloadlibrary) dieses Handle zurückgibt.

### <a name="return-value"></a>Rückgabewert

True, wenn die Funktion erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

`AfxFreeLibrary` Dekrementiert den Verweiszähler des Moduls geladenen Dynamic Link Library (DLL). Wenn der Verweiszähler null erreicht, wird das Modul nicht aus dem Adressraum des aufrufenden Prozesses zugeordnet ist, und das Handle ist nicht mehr gültig. Diese Verweiszähler erhöht sich beim `AfxLoadLibrary` aufgerufen wird.

Vor dem Aufheben der Zuordnung eines Moduls für die Bibliothek, kann das System die DLL getrennt von den Prozessen, die es verwenden. Der DLL haben auf diese Weise die Möglichkeit zum Bereinigen von Ressourcen, die für den aktuellen Prozess zugewiesen wird. Nachdem die Einstiegspunktfunktion zurückgibt, wird das Bibliotheksmodul aus dem Adressraum des aktuellen Prozesses entfernt.

Verwendung `AfxLoadLibrary` ein DLL-Modul zugeordnet.

Verwenden Sie `AfxFreeLibrary` und `AfxLoadLibrary` (anstelle der Win32-Funktionen `FreeLibrary` und `LoadLibrary`) Wenn Ihre Anwendung mehrere Threads verwendet. Mithilfe von `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass den starten und Herunterfahren Code, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL geladen und entladen den globalen MFC-Status nicht beschädigt ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [AfxLoadLibrary](#afxloadlibrary).

### <a name="requirements"></a>Anforderungen

  **Header** afxdll_.h

##  <a name="afxgetapp"></a>  AfxGetApp

Der von dieser Funktion zurückgegebenen Zeiger kann verwendet werden, auf die Anwendungsinformationen wie z. B. den Code der main-Senden von Nachrichten oder das oberste Fenster.

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den einzelnen `CWinApp` Objekt für die Anwendung.

### <a name="remarks"></a>Hinweise

Wenn diese Methode NULL zurückgibt, kann dies darauf hinweisen, dass das Hauptfenster der Anwendung noch vollständig nicht initialisiert wurde. Es kann auch ein Problem hinweisen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxgetappname"></a>  AfxGetAppName

Die Zeichenfolge, die von dieser Funktion zurückgegebenen kann für temporäre Zeichenfolgennamen für diagnosemeldungen oder als Stamm verwendet werden.

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>Rückgabewert

Eine mit Null endende Zeichenfolge, die den Namen der Anwendung enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxgetinstancehandle"></a>  AfxGetInstanceHandle

Mit dieser Funktion können Sie den Instanzhandle, der aktuellen Anwendung abrufen.

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>Rückgabewert

Ein HINSTANCE der aktuellen Instanz der Anwendung. Wenn von einer mit der USRDLL-Version von MFC verknüpften DLL aufgerufen wird, wird eine HINSTANCE der DLL zurückgegeben.

### <a name="remarks"></a>Hinweise

`AfxGetInstanceHandle` Gibt immer auf die HINSTANCE der ausführbaren Datei (. EXE-Datei), wenn sie aus aufgerufen wird eine DLL-Datei verknüpft, mit der USRDLL-Version von MFC. In diesem Fall gibt es eine HINSTANCE, für die DLL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd

Wenn Ihre Anwendung einen OLE-Server ist, rufen Sie diese Funktion zum Abrufen der eines Zeigers auf das aktiven Hauptfenster der Anwendung anstelle der direkten verweisen auf die [M_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) Member des Anwendungsobjekts.

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>Rückgabewert

Wenn der Server über ein Objekt verfügt, das innerhalb eines Containers direkt aktiv ist, und dieser Container aktiv ist, gibt diese Funktion einen Zeiger auf das Rahmenfensterobjekt zurück, das das direkt aktive Dokument enthält.

Wenn kein Objekt, das direkt aktiv in einem Container vorhanden ist, oder die Anwendung keinen OLE-Server, gibt diese Funktion einfach die *M_pMainWnd* des Anwendungsobjekts.

Wenn `AfxGetMainWnd` vom primären Thread der Anwendung aufgerufen wird, wird das Hauptfenster der Anwendung gemäß den oben genannten Regeln zurückgegeben. Wenn die Funktion von einem sekundären Thread in der Anwendung aufgerufen wird, gibt die Funktion das Hauptfenster zurück, das dem aufrufenden Thread zugeordnet ist.

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung keinen OLE-Server, wird das Aufrufen dieser Funktion entspricht der direkten verweisen auf die *M_pMainWnd* Member des Anwendungsobjekts.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration

Diese Funktion verwenden, um festzustellen, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** ( **HKCU**) Knoten.

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>Rückgabewert

TRUE gibt an, dass die Informationen in der Registrierung auf den HKCU-Knoten geleitet wird; FALSE gibt an, dass die Anwendung Informationen in der Registrierung auf den Standardknoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Hinweise

Wenn Sie den registrierungsumleitung aktivieren, leitet das Framework den Zugriff von **HKCR** zu **HKEY_CURRENT_USER\Software\Classes**. Nur die MFC und ATL-Frameworks sind von der Umleitung betroffen.

Verwenden Sie zum Ändern, ob die Anwendung Zugriff auf die Registrierung leitet [AfxSetPerUserRegistration](#afxsetperuserregistration).

### <a name="requirements"></a>Anforderungen

  **Header** afxstat_.h

##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle

Zurückgegeben, die von dieser Funktion auf die Ressourcen der Anwendung direkten Zugriff auf die HINSTANCE behandeln verwenden z. B. in Aufrufen an die Windows-Funktion `FindResource`.

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>Rückgabewert

Ein HINSTANCE-Handle, in denen die Standardressourcen der Anwendung geladen werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxgetthread"></a>  AfxGetThread

Mit dieser Funktion können Sie einen Zeiger auf die [CWinThread](../../mfc/reference/cwinthread-class.md) Objekt, das den aktuell ausgeführten Thread darstellt.

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den gerade ausgeführten Thread; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Muss von den gewünschten Thread aufgerufen werden.

> [!NOTE]
>  Wenn Sie eine MFC-Projekt aufrufen Portieren `AfxGetThread` von Visual C++-Versionen 4.2, 5.0 oder 6.0 `AfxGetThread` Aufrufe [AfxGetApp](#afxgetapp) Wenn kein Thread gefunden wird. In neueren Versionen des Compilers `AfxGetThread` gibt NULL zurück, wenn kein Thread wurde nicht gefunden. Wenn der Thread der Anwendung werden sollen, müssen Sie aufrufen `AfxGetApp`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxinitrichedit"></a>  AfxInitRichEdit

Rufen Sie diese Funktion, um die rich-Edit-Steuerelement (Version 1.0) für die Anwendung zu initialisieren.

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Hinweise

Diese Funktion wird für die Abwärtskompatibilität bereitgestellt. Neue Anwendungen sollten verwenden [AfxInitRichEdit2](#afxinitrichedit2).

`AfxInitRichEdit` Lädt RICHED32 an. DLL Version 1.0 des rich-Edit-Steuerelements initialisiert werden. Version 2.0 und 3.0 des rich-Edit-Steuerelements RICHED20 verwenden zu können. Die DLL muss geladen werden. Dies erfolgt durch einen Aufruf von [AfxInitRichEdit2](#afxinitrichedit2).

Um rich-Edit-Steuerelemente in vorhandenen Visual C++-Anwendungen zu Version 2.0 aktualisieren, öffnen Sie die. RC-Datei als Text, ändern Sie den Klassennamen des jedes rich-Edit-Steuerelement aus "RICHEDIT", "RichEdit20a". Ersetzen Sie dann auf den Aufruf von `AfxInitRichEdit` mit `AfxInitRichEdit2`.

Diese Funktion initialisiert auch die allgemeine Steuerelementbibliothek, wenn die Bibliothek, die noch nicht für den Prozess initialisiert wurde. Wenn Sie das rich-Edit-Steuerelement direkt von der MFC-Anwendung verwenden, sollten Sie durch Aufrufen dieser Funktion, um sicherzustellen, dass die rich-Edit-Steuerelement-Laufzeit von MFC ordnungsgemäß initialisiert wurde. Wenn Sie die Create-Methode der Aufrufen [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), müssen Sie normalerweise nicht diese Funktion aufrufen, aber in einigen Fällen kann es sein erforderlich.

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxinitrichedit2"></a>  AfxInitRichEdit2

Rufen Sie diese Funktion, um die rich-Edit-Steuerelement (Version 2.0 und höher) für die Anwendung zu initialisieren.

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um die RICHED20 zu laden. DLL und initialisieren, Version 2.0 von der Rich edit-Steuerelement. Wenn Sie die Create-Methode der Aufrufen [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), müssen Sie normalerweise nicht diese Funktion aufrufen, aber in einigen Fällen kann es sein erforderlich.

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

  ## <a name="afxisextendedframeclass"></a>  AfxIsExtendedFrameClass
Bestimmt, ob das jeweilige Fenster ein erweitertes Rahmenobjekt ist.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```
### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Ein Zeiger auf ein Objekt, das von abgeleitet ist `CWnd`.

### <a name="return-value"></a>Rückgabewert

True, wenn das angegebene Fenster ein erweitertes rahmenobjekt ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode gibt "true" zurück, wenn *aufnehmen* leitet sich von einer der folgenden Klassen:

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

Diese Methode ist nützlich, wenn Sie überprüfen müssen, ob ein Funktions- oder Methodenparameter ein erweitertes Rahmenfenster ist.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

### <a name="see-also"></a>Siehe auch

[CWnd-Klasse](cwnd-class.md)<br/>
[CFrameWndEx-Klasse](cframewndex-class.md)

## <a name="afxismfctoolbar"></a> AfxIsMFCToolBar

Bestimmt, ob das angegebene Fenster ein Symbolleistenobjekt.

### <a name="syntax"></a>Syntax

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```
### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
[in] Ein Zeiger auf ein Objekt, das von abgeleitet ist `CWnd`.

### <a name="return-value"></a>Rückgabewert

True, wenn das angegebene Fenster ein Symbolleistenobjekt. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode gibt `TRUE` Wenn *aufnehmen* leitet sich von `CMFCToolBar`. Diese Methode ist nützlich, wenn Sie zu überprüfen, ob ein Funktion oder Methode Parameter haben eine `CMFCToolBar` Objekt.

### <a name="requirements"></a>Anforderungen

**Header:** „afxpriv.h“

### <a name="see-also"></a>Siehe auch

[CWnd-Klasse](cwnd-class.md)<br/>
[CMFCToolBar-Klasse](cmfctoolbar-class.md)


## <a name="afxkeyboardmanager"></a> AfxKeyboardManager

Zeiger auf die globale [Tastatur Manager](ckeyboardmanager-class.md).

### <a name="syntax"></a>Syntax

```
CKeyboardManager* afxKeyboardManager;
```
### <a name="requirements"></a>Anforderungen

**Header:** afxkeyboardmanager.h

### <a name="see-also"></a>Siehe auch

[Makros, globale Funktionen und globale Variablen](mfc-macros-and-globals.md)<br/>
[CKeyboardManager-Klasse](ckeyboardmanager-class.md)


##  <a name="afxloadlibrary"></a>  "AfxLoadLibrary"

Verwendung `AfxLoadLibrary` ein DLL-Modul zugeordnet.

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>Parameter

*lpszModuleName*<br/>
Verweist auf eine Null-terminierte Zeichenfolge mit dem Namen des Moduls zurück (entweder ein. DLL oder. EXE-Datei). Der angegebene Name ist der Dateiname des Moduls.

Wenn die Zeichenfolge einen Pfad gibt, aber die Datei im angegebenen Verzeichnis nicht vorhanden, schlägt die Funktion fehl.

Wenn kein Pfad angegeben ist, und die Dateierweiterung nicht angegeben wird, lautet die standarderweiterung. DLL wird angefügt. Allerdings kann die dateizeichenfolge um anzugeben, dass es sich bei der Namen des Moduls keine Erweiterung besitzt ein nachgestellten Punkt Zeichen (.) enthalten. Wenn kein Pfad angegeben ist, sucht die Funktion der Datei in der folgenden Reihenfolge:

- Das Verzeichnis, aus denen die Anwendung geladen.

- Das aktuelle Verzeichnis.

- **Windows 95/98:** das Windows-Systemverzeichnis. **Windows NT:** das 32-Bit-Windows-Systemverzeichnis. Der Name dieses Verzeichnisses ist "System32".

- **Nur Windows NT:** der 16-Bit-Windows-Systemverzeichnis. Es gibt keine Win32-Funktion, die den Pfad für dieses Verzeichnis abruft, aber es durchsucht wird. Der Name dieses Verzeichnisses ist SYSTEM.

- Das Windows-Verzeichnis.

- Die Verzeichnisse, die in der PATH-Umgebungsvariablen aufgelistet sind.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ein Handle für das Modul an. Wenn die Funktion fehlschlägt, ist der Rückgabewert NULL.

### <a name="remarks"></a>Hinweise

Gibt ein Handle, das verwendet werden kann [GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212) um die Adresse einer DLL-Funktion abzurufen. `AfxLoadLibrary` kann auch verwendet werden, um andere ausführbare Module zuzuordnen.

Jeder Prozess verwaltet einen Verweiszähler für jedes Modul geladenen Bibliothek. Diese Verweiszähler erhöht sich beim `AfxLoadLibrary` aufgerufen wird, und erniedrigt wird jedes Mal `AfxFreeLibrary` aufgerufen wird. Wenn der Verweiszähler null erreicht, wird das Modul nicht aus dem Adressraum des aufrufenden Prozesses zugeordnet ist, und das Handle ist nicht mehr gültig.

Verwenden Sie `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle der Win32-Funktionen `LoadLibrary` und `FreeLibrary`) Wenn Ihre Anwendung mehrere Threads verwendet, und wenn sie dynamisch eine MFC-Erweiterungs-DLL geladen wird. Mithilfe von `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass der starten und Herunterfahren Code, der ausgeführt wird, wenn die MFC-Erweiterungs-DLL geladen und entladen wird den globalen MFC-Status nicht beschädigt ist.

Mithilfe von `AfxLoadLibrary` erfordert, dass Sie dynamisch verknüpfen mit der DLL-Version von MFC in einer Anwendung die Headerdatei für `AfxLoadLibrary`, Afxdll_.h, ist nur enthalten, wenn MFC zur Anwendung wie einer DLL verknüpft ist. Dies ist beabsichtigt, denn Sie müssen auf die DLL-Version von MFC oder MFC-Erweiterungs-DLLs zu verknüpfen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxdll_.h

## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

Zeiger auf die globale [Tearoff-Menü-Manager](cmenutearoffmanager-class.md).

### <a name="syntax"></a>Syntax

```
CMenuTearOffManager* g_pTearOffMenuManager;
```
### <a name="requirements"></a>Anforderungen

**Header:** afxmenutearoffmanager.h

### <a name="see-also"></a>Siehe auch

[CMenuTearOffManager-Klasse](cmenutearoffmanager-class.md)

## <a name="afxmousemanager"></a>  AfxMouseManager

Zeiger auf die globale [Maus Manager](cmousemanager-class.md).

### <a name="syntax"></a>Syntax

```
CMouseManager* afxMouseManager;
```
### <a name="requirements"></a>Anforderungen

**Header:** afxmousemanager.h

### <a name="see-also"></a>Siehe auch

[CMouseManager-Klasse](cmousemanager-class.md)



##  <a name="afxregisterclass"></a>  AfxRegisterClass

Verwenden Sie diese Funktion zum Registrieren von Fensterklassen in einer DLL, die MFC verwenden.

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>Parameter

*lpWndClass*<br/>
Zeiger auf eine [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur mit Informationen über die Fensterklasse registriert werden. Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.

### <a name="return-value"></a>Rückgabewert

True, wenn die Klasse erfolgreich registriert wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn Sie diese Funktion verwenden, ist die Klasse automatisch aufgehoben, wenn die DLL entladen wird.

In-fremde DLL-Builds die `AfxRegisterClass` Bezeichner wird als ein Makro, das an die Windows-Funktion definiert `RegisterClass`, da die Klassen, die in einer Anwendung registriert, automatisch aufgehoben werden. Bei Verwendung von `AfxRegisterClass` anstelle von `RegisterClass`, Ihr Code kann unverändert sowohl in einer Anwendung als auch in einer DLL verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass

Ermöglicht Ihnen, Ihre eigenen Klassen zu registrieren.

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>Parameter

*nClassStyle*<br/>
Gibt den Stil für Windows-Klasse oder eine Kombination von Stilen, die das bitweise OR mit erstellt ( **&#124;**) Operator, für die Fensterklasse. Eine Liste der Klassenstile, finden Sie unter den [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur im Windows SDK. Wenn der Wert NULL ist, werden die Standardwerte wie folgt festgelegt werden:

- Legt den Stil der Maus auf CS_DBLCLKS, sendet Nachrichten an die Fensterprozedur doppelklicken, wenn der Benutzer die Maustaste doppelklickt fest.

- Legt den Cursor Pfeilstil auf der Windows-standard-IDC_ARROW fest.

- Legt den Hintergrundpinsel für NULL-Werte fest, damit das Fenster den Hintergrund nicht gelöscht werden.

- Legt das Symbol fest, um die standardmäßige ","-Flags winken Windows Logo-Symbol.

*hCursor*<br/>
Gibt ein Handle auf die Cursorressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, erhalten Sie den standardmäßigen IDC_ARROW-Cursor.

*hbrBackground*<br/>
Gibt ein Handle für die Pinselressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, Sie haben ein Hintergrundpinsel für die NULL und das Fenster wird standardmäßig nicht löschen, des Hintergrunds, während der Verarbeitung [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd).

*hIcon*<br/>
Gibt ein Handle für die Symbolressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, erhalten Sie die standardmäßige ","-Flags winken Windows Logo-Symbol.

### <a name="return-value"></a>Rückgabewert

Eine mit Null endende Zeichenfolge, die den Namen der Klasse enthält. Sie können diese Name der Klasse übergeben die `Create` Memberfunktion in `CWnd` oder andere **CWnd -** abgeleiteten Klassen, um ein Fenster zu erstellen. Der Name wird von der Microsoft Foundation Class-Bibliothek generiert.

> [!NOTE]
>  Der Rückgabewert ist ein Zeiger auf einen statischen Puffer. Um diese Zeichenfolge speichern möchten, weisen Sie ihn ein `CString` Variable.

### <a name="remarks"></a>Hinweise

Die Microsoft Foundation Class-Bibliothek wird automatisch mehrere standardmäßige Fenstermanager-Klassen für Sie registriert. Rufen Sie diese Funktion, wenn Sie Ihre eigenen Klassen registrieren möchten.

Registrierter Name für eine Klasse von `AfxRegisterWndClass` ausschließlich auf den Parametern abhängig ist. Wenn Sie aufrufen `AfxRegisterWndClass` mehrmals mit identischen Parametern registriert nur eine Klasse beim ersten Aufruf. Nachfolgende Aufrufe von `AfxRegisterWndClass` einfach den bereits registrierten Klassennamen mit identischen Parametern zurück.

Wenn Sie aufrufen `AfxRegisterWndClass` für mehrere CWnd abgeleiteten Klassen mit identischen Parametern, die anstelle einer separaten Fenster-Klasse für jede Klasse, verwendet jede Klasse die gleichen Fensterklasse. Dies kann Probleme verursachen, wenn das Format der CS_CLASSDC-Klasse verwendet wird. Anstatt mehrere CS_CLASSDC Fensterklassen erhalten Sie eine CS_CLASSDC Fensterklasse, und alle C++-Fenster, die diese Klasse Freigabe der gleichen Domänencontroller zu verwenden. Um dieses Problem zu vermeiden, rufen Sie [AfxRegisterClass](#afxregisterclass) zum Registrieren der Klasse.

Finden Sie in der technischen Hinweis [TN001: Fensterklassenregistrierung](../../mfc/tn001-window-class-registration.md) für Weitere Informationen zu fensterklassenregistrierung und `AfxRegisterWndClass` Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration

Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet der **HKEY_CURRENT_USER** ( **HKCU**) Knoten.

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] TRUE gibt an, dass die Informationen in der Registrierung auf den HKCU-Knoten geleitet wird; FALSE gibt an, dass die Anwendung Informationen in der Registrierung auf den Standardknoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).

### <a name="remarks"></a>Hinweise

Vor Windows Vista Anwendungen, die die Registrierung in der Regel verwendet, Zugriff auf die **HKEY_CLASSES_ROOT** Knoten. Mit Windows Vista oder höher, müssen Sie jedoch eine Anwendung im erweiterten Modus, in HKCR schreiben ausführen.

Diese Methode ermöglicht Ihrer Anwendung zu lesen und Schreiben in die Registrierung ohne im Modus mit erhöhten Rechten ausgeführt werden, indem Sie Zugriff auf die Registrierung von HKCR auf HKCU umleiten. Weitere Informationen finden Sie unter [Linker-Eigenschaftenseiten](../../ide/linker-property-pages.md).

Wenn Sie den registrierungsumleitung aktivieren, leitet das Framework den Zugriff von HKCR geschriebenen Daten in **HKEY_CURRENT_USER\Software\Classes**. Nur die MFC und ATL-Frameworks sind von der Umleitung betroffen.

Die Standardimplementierung greift auf die Registrierung unter HKCR Vorzuziehen.

### <a name="requirements"></a>Anforderungen

  **Header** afxstat_.h

##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle

Verwenden Sie diese Funktion, um das HINSTANCE-Handle festzulegen, das bestimmt, in denen die Standardressourcen der Anwendung geladen werden.

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>Parameter

*hInstResource*<br/>
Das Handle-Instanz oder ein Modul ein. EXE- oder DLL-Datei, die von der die Ressourcen der Anwendung geladen werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

## <a name="afxshellmanager"></a>  Globale AfxShellManager

Zeiger auf die globale [Shell-Manager](cshellmanager-class.md).

### <a name="syntax"></a>Syntax

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxshellmanager.h

### <a name="see-also"></a>Siehe auch

[CShellManager-Klasse](cshellmanager-class.md)

##  <a name="afxsocketinit"></a>  AfxSocketInit

Rufen Sie diese Funktion Ihrer `CWinApp::InitInstance` überschreiben, um die Windows-Sockets nicht initialisieren.

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>Parameter

*lpwsaData*<br/>
Ein Zeiger auf eine [WSADATA](../../mfc/reference/wsadata-structure.md) Struktur. Wenn *LpwsaData* ist nicht gleich NULL ist, klicken Sie dann die Adresse der `WSADATA` Struktur wird ausgefüllt, durch den Aufruf von `WSAStartup`. Diese Funktion wird auch sichergestellt, dass `WSACleanup` für Sie aufgerufen wird, bevor die Anwendung beendet wird.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC-Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jeder Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. In der Standardeinstellung `AfxSocketInit` nur im primären Thread aufgerufen wird.

### <a name="requirements"></a>Anforderungen

  **Header** Datei afxsock.h

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager

Zeiger auf die globale [Vorgesetzten des Benutzers Tools](cusertoolsmanager-class.md).

### <a name="syntax"></a>Syntax

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>Anforderungen

**Header:** afxusertoolsmanager.h

### <a name="see-also"></a>Siehe auch

[CUserToolsManager-Klasse](cusertoolsmanager-class.md)


##  <a name="afxwininit"></a>  AfxWinInit

Diese Funktion wird aufgerufen, von dem vom MFC bereitgestellten `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) Initialisierung einer GUI-basierte Anwendung, zum Initialisieren von MFC.

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>Parameter

*hInstance*<br/>
Das Handle des derzeit ausgeführten Moduls.

*hPrevInstance*<br/>
Ein Handle für eine vorherige Instanz der Anwendung. Für eine Win32-basierte Anwendung, ist dieser Parameter immer **NULL**.

*lpCmdLine*<br/>
Verweist auf einen Null-terminierte Zeichenfolge, die die Befehlszeile für die Anwendung angeben.

*nCmdShow*<br/>
Gibt an, wie das Hauptfenster einer GUI-Anwendung angezeigt wird.

### <a name="remarks"></a>Hinweise

Für eine Konsolenanwendung, die verwendet nicht die MFC bereitgestellten `WinMain` -Funktion, die Sie aufrufen müssen `AfxWinInit` direkt in MFC zu initialisieren.

Wenn Sie aufrufen `AfxWinInit` selbst, sollten Sie eine Instanz des deklariert eine `CWinApp` Klasse. Für eine Konsolenanwendung, empfiehlt sich nicht um eine eigene Klasse von ableiten `CWinApp` und stattdessen eine Instanz von `CWinApp` direkt. Diese Technik ist geeignet, wenn Sie möchten, lassen Sie die gesamte Funktionalität für Ihre Anwendung in der Implementierung von **main**.

> [!NOTE]
>  Wenn sie einen Aktivierungskontext für eine Assembly erstellt, verwendet MFC eine Manifestressource, die vom Benutzermodul bereitgestellt. Der Aktivierungskontext wird erstellt, `AfxWinInit`. Weitere Informationen finden Sie unter [Unterstützung für Aktivierungskontexte im MFC-Modulstatus](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxwin.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)
