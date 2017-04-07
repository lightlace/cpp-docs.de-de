---
title: Anwendungsinformationen und Anwendungsverwaltung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 17
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
ms.sourcegitcommit: 3d045736f9a54d344c67e3f7408198e65a0bc95f
ms.openlocfilehash: 89f2d1365929b8f5e153ac2bb33adc5e9adb2aaf
ms.lasthandoff: 03/29/2017

---
# <a name="application-information-and-management"></a>Anwendungsinformationen und Anwendungsverwaltung
Wenn Sie eine Anwendung schreiben, erstellen Sie ein einzelnes [CWinApp](../../mfc/reference/cwinapp-class.md)-abgeleitetes Objekt. Sie möchten in einigen Fällen erhalten Informationen über dieses Objekt außerhalb der `CWinApp`-abgeleitetes Objekt.  
  
 Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen, um Ihnen die Durchführung dieser Aufgaben zu erleichtern:  
  
### <a name="application-information-and-management-functions"></a>Anwendungsinformationen und Verwaltungsfunktionen  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|Erstellt einen neuen Thread an.|  
|[AfxEndThread](#afxendthread)|Beendet den aktuellen Thread.|  
|["AfxFreeLibrary"](#afxfreelibrary)|Dekrementiert den Verweiszähler des Moduls geladenen Dynamic Link Library (DLL); Wenn der Verweiszähler 0 erreicht hat, ist das Modul nicht zugeordnet.|  
|[AfxGetApp](#afxgetapp)|Gibt ein Zeiger auf die Anwendung einzelne's `CWinApp` Objekt.|  
|[AfxGetAppName](#afxgetappname)|Gibt eine Zeichenfolge, die den Namen der Anwendung enthält.|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Gibt eine `HINSTANCE` , die dieser Instanz der Anwendung darstellt.|  
|[AfxGetMainWnd](#afxgetmainwnd)|Gibt einen Zeiger auf das "main" aktuellen Fenster einer nicht-OLE-Anwendung oder das direkte Rahmenfenster einer Serveranwendung zurück.|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Mit dieser Funktion können Sie bestimmen, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|Gibt eine `HINSTANCE` auf den Quellcode der Anwendung-Standardressourcen. Hiermit können Sie die Ressourcen der Anwendung direkt zugreifen.|  
|[AfxGetThread](#afxgetthread)|Ruft einen Zeiger auf das aktuelle [CWinThread](../../mfc/reference/cwinthread-class.md) Objekt.|  
|[AfxInitRichEdit](#afxinitrichedit)|Initialisiert die Version 1.0 Rich-edit-Steuerelement für die Anwendung an.|  
|[AfxInitRichEdit2](#afxinitrichedit2)|Initialisiert die Version 2.0 oder höher Rich-edit-Steuerelement für die Anwendung an.|  
|["AfxLoadLibrary"](#afxloadlibrary)|Ordnet ein DLL-Modul, und gibt ein Handle, das zum Abrufen der Adresse einer DLL-Funktion verwendet werden kann.|  
|[AfxRegisterClass](#afxregisterclass)|Registriert eine Fensterklasse in eine DLL, die MFC verwendet.|  
|[AfxRegisterWndClass](#afxregisterwndclass)|Registriert eine Windows-Fensterklasse als Ergänzung für die von MFC automatisch registriert.|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Legt fest, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|Legt die `HINSTANCE` Handle, unter dem die Standardressourcen der Anwendung geladen werden.|  
|[AfxSocketInit](#afxsocketinit)|Wird aufgerufen, einem `CWinApp::InitInstance` überschreiben, um die Windows-Sockets nicht initialisieren.|  
|[AfxWinInit](#afxwininit)|Von MFC bereitgestellte aufgerufen `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) Initialisierung einer GUI-basierte Anwendung, zum Initialisieren von MFC. Muss für konsolenanwendungen direkt aufgerufen werden, die MFC verwenden.|  
  

  
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
 `pfnThreadProc`  
 Zeigt auf die Steuerungsfunktion für den Arbeitsthread. Nicht mit **NULL**. Diese Funktion muss wie folgt deklariert werden:  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 RUNTIME_CLASS eines Objekts abgeleitet [CWinThread](../../mfc/reference/cwinthread-class.md).  
  
 *pParam*  
 An die Steuerungsfunktion zu übergebender Parameter, wie im Parameter für die Funktionsdeklaration in `pfnThreadProc` gezeigt.  
  
 `nPriority`  
 Die gewünschte Priorität des Threads. Eine vollständige Liste und Beschreibung der verfügbaren Prioritäten, finden Sie unter [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nStackSize`  
 Gibt die Stapelgröße für den neuen Thread in Bytes an. Mit dem Wert 0 wird die Stapelgröße standardmäßig so groß wie die des erstellenden Threads.  
  
 `dwCreateFlags`  
 Gibt ein zusätzliches Flag an, das die Erstellung des Threads steuert. Dieses Flag kann einen von zwei Werten enthalten:  
  
- **CREATE_SUSPENDED** der Thread wird mit einem Unterbrechungszähler 1 gestartet. Verwendung **CREATE_SUSPENDED** , wenn Sie beliebige Memberdaten des initialisieren möchten die `CWinThread` Objekt, z. B. [M_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) oder Member der abgeleiteten Klasse, befor der Thread ausgeführt wird. Sobald die Initialisierung abgeschlossen ist, verwenden [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) an den Thread zu starten. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.  
  
- **0** direkt nach dem Erstellen der Thread gestartet.  
  
 `lpSecurityAttrs`  
 Verweist auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die die Sicherheitsattribute für den Thread angibt. Wenn **NULL**, die gleichen Sicherheitsattribute des erstellenden Threads verwendet werden soll. Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das neu erstellte Threadobjekt oder **NULL** tritt ein Fehler auf.  
  
### <a name="remarks"></a>Hinweise  
 Mit der ersten Form von `AfxBeginThread` wird ein Arbeitsthread erstellt. Mit der zweiten Form wird ein Thread erstellt, der als Benutzeroberflächenthread oder als Arbeitsthread dienen kann.  
  
 `AfxBeginThread`erstellt ein neues `CWinThread` -Objekt, ruft seine [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) Funktion, um die Ausführung des Threads gestartet, und gibt einen Zeiger auf den Thread. Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte. Um den Thread zu beenden, rufen [AfxEndThread](#afxendthread) aus innerhalb der Thread oder aus der Steuerungsfunktion des Arbeitsthreads zurück.  
  
 Multithreading muss durch die Anwendung aktiviert werden, andernfalls erzeugt diese Funktion einen Fehler. Weitere Informationen zur Aktivierung von multithreading finden Sie unter [/MD, / MT, / ld (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) unter *Visual C++-Compileroptionen*.  
  
 Weitere Informationen zu `AfxBeginThread`, finden Sie in den Artikeln [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md) und [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxendthread"></a>AfxEndThread  
 Rufen Sie diese Funktion, um den gerade ausgeführten Thread zu beenden.  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>Parameter  
 *nExitCode*  
 Gibt den Exitcode des Threads an.  
  
 *bLöschen*  
 Wird das Threadobjekt aus dem Arbeitsspeicher gelöscht.  
  
### <a name="remarks"></a>Hinweise  
 Müssen von innerhalb der zu beendenden Thread aufgerufen werden.  
  
 Weitere Informationen zu `AfxEndThread`, finden Sie im Artikel [Multithreading: Beenden von Threads](../../parallel/multithreading-terminating-threads.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxfreelibrary"></a>"AfxFreeLibrary"  
 Beide `AfxFreeLibrary` und `AfxLoadLibrary` einen Verweiszähler für jede geladene Bibliotheksmodul verwalten.  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>Parameter  
 *hInstLib*  
 Ein Handle des geladenen Moduls. ["AfxLoadLibrary"](#afxloadlibrary) gibt dieses Handle zurück.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn die Funktion erfolgreich ist; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 `AfxFreeLibrary`Dekrementiert den Verweiszähler des Moduls geladenen Dynamic Link Library (DLL). Wenn der Verweiszähler 0 erreicht hat, das Modul nicht aus dem Adressraum des aufrufenden Prozesses zugeordnet ist, und das Handle ist nicht mehr gültig. Diese Verweiszähler dieser Planergruppe wird jedes Mal inkrementiert `AfxLoadLibrary` aufgerufen wird.  
  
 Vor dem Aufheben der Zuordnung einer Bibliotheksmodul, kann das System die DLL So trennen Sie die Prozesse, die verwendet wird. Auf diese Weise kann der DLL zum Bereinigen von Ressourcen, die im Auftrag des aktuellen Prozesses zugeordnet. Nachdem die Einstiegspunktfunktion zurückgegeben hat, wird das Bibliotheksmodul aus dem Adressraum des aktuellen Prozesses entfernt.  
  
 Verwendung `AfxLoadLibrary` ein DLL-Modul zugeordnet.  
  
 Achten Sie darauf, dass Sie verwenden `AfxFreeLibrary` und `AfxLoadLibrary` (anstelle der Win32-Funktionen **FreeLibrary** und **LoadLibrary**) Wenn Ihre Anwendung mehrere Threads verwendet. Mit `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass das Starten und Herunterfahren Code, der ausgeführt wird, wenn die Erweiterung DLL wird geladen und entladen, die nicht über den Status der globalen MFC beschädigt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für ["AfxLoadLibrary"](#afxloadlibrary).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdll_.h  
  
##  <a name="afxgetapp"></a>AfxGetApp  
 Der von dieser Funktion zurückgegebenen Zeiger kann auf Anwendungsinformationen wie z. B. der wichtigsten nachrichtenverteilung Code oder die obersten Fensters verwendet werden.  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die einzelnen `CWinApp` Objekt für die Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode NULL zurückgibt, kann dies darauf hinweisen, dass das Hauptfenster der Anwendung nicht vollständig initialisiert wurde. Es kann auch ein Problem hinweisen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxgetappname"></a>AfxGetAppName  
 Die Zeichenfolge, die von dieser Funktion zurückgegebenen kann für temporäre Zeichenfolgennamen für diagnosemeldungen oder als Stamm verwendet werden.  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine auf Null endende Zeichenfolge, die den Namen der Anwendung enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[127 NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxgetinstancehandle"></a>AfxGetInstanceHandle  
 Mit dieser Funktion können Sie das Instanzhandle der aktuellen Anwendung abrufen.  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HINSTANCE` mit der aktuellen Instanz der Anwendung. Wenn Sie von einer mit der USRDLL-Version von MFC verknüpften DLL aufgerufen ein `HINSTANCE` mit der DLL zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 `AfxGetInstanceHandle`Gibt immer die `HINSTANCE` der ausführbaren Datei (. EXE-Datei), wenn sie innerhalb von aufgerufen wird eine DLL verknüpft, mit der USRDLL-Version von MFC. In diesem Fall gibt es eine `HINSTANCE` auf die DLL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxgetmainwnd"></a>AfxGetMainWnd  
 Wenn Ihre Anwendung einen OLE-Server ist, rufen Sie diese Funktion zum Abrufen von eines Zeigers auf das aktiven Hauptfenster der Anwendung und nicht direkt auf die [M_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) Member des Anwendungsobjekts.  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Server über ein Objekt verfügt, das innerhalb eines Containers direkt aktiv ist, und dieser Container aktiv ist, gibt diese Funktion einen Zeiger auf das Rahmenfensterobjekt zurück, das das direkt aktive Dokument enthält.  
  
 Wenn es kein Objekt gibt, das innerhalb eines Containers direkt aktiv ist, oder es sich bei der Anwendung nicht um einen OLE-Server handelt, gibt diese Funktion lediglich den `m_pMainWnd` des Anwendungsobjekts zurück.  
  
 Wenn `AfxGetMainWnd` vom primären Thread der Anwendung aufgerufen wird, wird das Hauptfenster der Anwendung gemäß den oben genannten Regeln zurückgegeben. Wenn die Funktion von einem sekundären Thread in der Anwendung aufgerufen wird, gibt die Funktion das Hauptfenster zurück, das dem aufrufenden Thread zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn es sich bei der Anwendung nicht um einen OLE-Server handelt, entspricht das Aufrufen dieser Funktion dem direkten Verweisen auf den `m_pMainWnd`-Member des Anwendungsobjekts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration  
 Mit dieser Funktion können Sie bestimmen, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass die Registrierungsinformationen weitergeleitet wird die **HKCU** Knoten `FALSE` gibt an, dass die Anwendung auf den Standardknoten für die Informationen in der Registrierung schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die registrierungsumleitung aktivieren, leitet das Framework den Zugriff auf **HKCR** auf **HKEY_CURRENT_USER\Software\Classes**. Die Umleitung sind nur für die MFC und ATL-Frameworks betroffen.  
  
 Verwenden Sie zum Ändern, ob die Anwendung den Registrierungszugriff leitet [AfxSetPerUserRegistration](#afxsetperuserregistration).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxstat_.h    
  
##  <a name="afxgetresourcehandle"></a>AfxGetResourceHandle  
 Verwenden der `HINSTANCE` von dieser Funktion der Anwendung Zugriff auf Ressourcen direkt, z. B. in Aufrufe an die Windows-Funktion zurückgegebene Handle **FindResource**.  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HINSTANCE` Handle, unter dem die Standardressourcen der Anwendung geladen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxgetthread"></a>AfxGetThread  
 Mit dieser Funktion können Sie einen Zeiger auf die [CWinThread](../../mfc/reference/cwinthread-class.md) Objekt, das den derzeit ausgeführten Thread darstellt.  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf den gerade ausgeführten Thread; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Muss aus dem gewünschten Thread aufgerufen werden.  
  
> [!NOTE]
>  Wenn Sie ein Aufruf von MFC-Projekt Portieren `AfxGetThread` von Visual C++-Versionen 4.2, 5.0 oder 6.0, `AfxGetThread` Aufrufe [AfxGetApp](#afxgetapp) Wenn keine Threads gefunden wird. In Visual c++ .NET und höher `AfxGetThread` gibt **NULL** Wenn kein Thread gefunden wurde. Wenn Thread der Anwendung werden sollen, müssen Sie aufrufen `AfxGetApp`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxinitrichedit"></a>AfxInitRichEdit  
 Mit dieser Funktion können die rich-Edit-Steuerelement (Version 1.0) für die Anwendung zu initialisieren.  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird für Abwärtskompatibilität bereitgestellt. Mit Visual C++ .NET und spätere Verwendung erstellte Anwendungen [AfxInitRichEdit2](#afxinitrichedit2).  
  
 `AfxInitRichEdit`Lädt RICHED32. DLL Version 1.0 von rich-Edit-Steuerelement zu initialisieren. Version 2.0 und 3.0, das rich-Edit-Steuerelements RICHED20 verwenden zu können. Die DLL muss geladen werden soll. Dies erfolgt mit einem Aufruf von [AfxInitRichEdit2](#afxinitrichedit2). Wenn Sie Ressourcen mit dem rich-Edit-Steuerelement vor Visual C++ .NET erstellt haben, sind die rich-Edit-Steuerelemente automatisch die Version 1.0. Rich-Edit-Steuerelemente mit Ressourcen-Editor von Visual C++ .NET eingefügt werden, Version 2.0.  
  
 Öffnen Sie zum Aktualisieren von rich-Edit-Steuerelemente in vorhandenen Visual C++-Anwendungen zu Version 2.0 der. RC-Datei als Text, ändern Sie den Klassennamen jedes rich-Edit-Steuerelements von "RICHEDIT", "RichEdit20a". Ersetzen Sie den Aufruf von `AfxInitRichEdit` mit `AfxInitRichEdit2`.  
  
 Diese Funktion initialisiert die Bibliothek für Standardsteuerelemente, auch, wenn die Bibliothek nicht bereits für den Prozess initialisiert wurde. Wenn Sie direkt von der MFC-Anwendung das rich-Edit-Steuerelement verwenden, sollten Sie durch Aufrufen dieser Funktion können Sie sicherstellen, dass die rich-Edit-Steuerelement-Laufzeit von MFC ordnungsgemäß initialisiert wurde. Wenn Sie die Create-Methode der Aufrufen [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), müssen Sie normalerweise nicht diese Funktion aufrufen, aber in einigen Fällen kann es erforderlich sein.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxinitrichedit2"></a>AfxInitRichEdit2  
 Mit dieser Funktion können die rich-Edit-Steuerelement (Version 2.0 oder höher) für die Anwendung zu initialisieren.  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Laden der RICHED20. DLL, und initialisieren Sie Version 2.0 für die Rich-edit-Steuerelement. Wenn Sie die Create-Methode der Aufrufen [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), müssen Sie normalerweise nicht diese Funktion aufrufen, aber in einigen Fällen kann es erforderlich sein.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxloadlibrary"></a>"AfxLoadLibrary"  
 Verwendung `AfxLoadLibrary` ein DLL-Modul zugeordnet.  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>Parameter  
 *lpszModuleName*  
 Verweist auf eine auf Null endende Zeichenfolge, die den Namen des Moduls enthält (entweder ein. DLL oder. EXE-Datei). Der angegebene Name ist der Dateiname des Moduls.  
  
 Wenn die Zeichenfolge einen Pfad gibt, aber die Datei im angegebenen Verzeichnis nicht vorhanden, schlägt die Funktion fehl.  
  
 Wenn kein Pfad angegeben ist, und die Dateierweiterung nicht angegeben wird, die standarderweiterung. DLL angefügt ist. Allerdings kann die dateizeichenfolge einbeziehen eine nachfolgende Punkt (.) an, dass der Modulname setzt keine Erweiterung besitzt. Wenn kein Pfad angegeben wird, sucht die Funktion für die Datei in der folgenden Reihenfolge:  
  
-   Das Verzeichnis, aus dem die Anwendung geladen.  
  
-   Das aktuelle Verzeichnis.  
  
- **Windows 95-und Windows 98:** Windows-Systemverzeichnis. **Windows NT:** 32-Bit-Windows-Systemverzeichnis. Der Name dieses Verzeichnisses ist "System32".  
  
- **Nur Windows NT:** der 16-Bit-Windows-Systemverzeichnis. Es gibt keine Win32-Funktion, die den Pfad dieses Verzeichnisses abruft, sondern gesucht. Der Name dieses Verzeichnisses ist SYSTEM.  
  
-   Das Windows-Verzeichnis.  
  
-   Die Verzeichnisse, die in der PATH-Umgebungsvariable aufgeführt sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ein Handle für das Modul an. Wenn die Funktion fehlschlägt, ist der Rückgabewert NULL.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt ein Handle, das in verwendet werden kann [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) beim Abrufen der Adresse einer DLL-Funktion. `AfxLoadLibrary`kann auch verwendet werden, um andere ausführbare Module zuzuordnen.  
  
 Jeder Prozess verwaltet einen Verweiszähler für jede geladene Bibliotheksmodul. Diese Verweiszähler dieser Planergruppe wird jedes Mal inkrementiert `AfxLoadLibrary` aufgerufen wird und wird wieder um eins erniedrigt jedes Mal `AfxFreeLibrary` aufgerufen wird. Wenn der Verweiszähler 0 erreicht hat, das Modul nicht aus dem Adressraum des aufrufenden Prozesses zugeordnet ist, und das Handle ist nicht mehr gültig.  
  
 Achten Sie darauf, dass Sie verwenden `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle der Win32-Funktionen **LoadLibrary** und **FreeLibrary**), wenn Ihre Anwendung mehrere Threads verwendet und dynamisch eine Erweiterungs-DLL geladen. Mit `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass das Starten und Herunterfahren Code, der ausgeführt wird, wenn die Erweiterungs-DLL geladen und entladen wird, die nicht über den Status der globalen MFC beschädigt.  
  
 Mit `AfxLoadLibrary` in einer Anwendung erfordert, dass Sie dynamisches Verknüpfen mit der DLL-Version von MFC; die Headerdatei für `AfxLoadLibrary`, Afxdll_.h, ist nur enthalten, wenn MFC an die Anwendung als DLL verknüpft ist. Dies ist beabsichtigt, da müssen Sie auf die DLL-Version von MFC verwenden, oder erstellen die Erweiterungs-DLLs zu verknüpfen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_DLLUser Nr. 1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser #2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser Nr. 3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdll_.h  
   
  
##  <a name="afxregisterclass"></a>AfxRegisterClass  
 Verwenden Sie diese Funktion zum Registrieren von Fensterklassen in einer DLL, die MFC verwendet.  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>Parameter  
 *lpWndClass*  
 Zeiger auf eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur mit Informationen über die Fensterklasse registriert werden. Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn die Klasse wurde erfolgreich registriert; andernfalls ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion verwenden, ist die Klasse automatisch aufgehoben, wenn die DLL entladen wird.  
  
 Bei der Builderstellung-fremde DLL die `AfxRegisterClass` Bezeichner wird als ein Makro, um die Windows-Funktion definiert **RegisterClass**, da die Klassen, die in einer Anwendung registriert automatisch aufgehoben werden. Bei Verwendung von `AfxRegisterClass` anstelle von **RegisterClass**, Ihren Code ohne Änderung in einer Anwendung sowohl in einer DLL verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_DLL NR. 3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxregisterwndclass"></a>AfxRegisterWndClass  
 Bietet die Möglichkeit, eigene Fensterklassen zu registrieren.  
  
```  
 
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 *nClassStyle*  
 Gibt den Stil der Windows-Klasse oder Kombination von Formatvorlagen, die mit dem bitweisen OR-erstellt ( **|**)-Operator, für die Fensterklasse. Eine Liste der Stile Klasse, finden Sie unter der [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn **NULL**, die Standardwerte werden wie folgt festgelegt werden:  
  
-   Legt das Format der Maus auf **CS_DBLCLKS**, sendet Nachrichten an die Fensterprozedur doppelklicken, wenn der Benutzer die Maustaste doppelklickt.  
  
-   Legt die Art des Pfeils Cursor auf der Windows-Standard **IDC_ARROW**.  
  
-   Legt den Hintergrundpinsel auf **NULL**, damit das Fenster des Hintergrunds nicht gelöscht werden.  
  
-   Legt das Symbol auf der standardmäßigen, Winkende Flag Windows Logo-Symbol fest.  
  
 `hCursor`  
 Gibt ein Handle für die Cursorressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, erhalten Sie den Standard **IDC_ARROW** Cursor.  
  
 *hbrBackground*  
 Gibt ein Handle für die Pinselressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, müssen eine **NULL** Hintergrundpinsel und Ihre Fenster wird standardmäßig nicht gelöscht. den Hintergrund beim Verarbeiten von [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055).  
  
 `hIcon`  
 Gibt ein Handle für die Symbolressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, erhalten Sie die standardmäßige, Winkende Flag Windows Logo-Symbol.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine auf Null endende Zeichenfolge, enthält der Name der Klasse. Sie können diese Namen der Klasse, übergeben die **erstellen** Memberfunktion in `CWnd` oder andere **CWnd -**abgeleiteten Klassen zum Erstellen eines Fensters. Der Name wird durch die Microsoft Foundation Class Library generiert.  
  
> [!NOTE]
>  Der Rückgabewert ist ein Zeiger auf einen statischen Puffer. Um diese Zeichenfolge zu speichern, weisen sie Sie einer `CString` Variable.  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class-Bibliothek registriert automatisch mehrere standard Fensterklassen für Sie. Rufen Sie diese Funktion, wenn Sie eine eigene Fensterklassen registrieren möchten.  
  
 Der Name für eine Klasse durch registriert `AfxRegisterWndClass` ausschließlich hängt von den Parametern. Beim Aufrufen `AfxRegisterWndClass` mehrmals mit identischen Parametern registriert nur eine Klasse beim ersten Aufruf. Nachfolgende Aufrufe `AfxRegisterWndClass` mit identischen Parametern einfach Zurückgeben der Klassenname bereits registriert.  
  
 Beim Aufrufen `AfxRegisterWndClass` für mehrere CWnd abgeleitete Klassen mit identischen Parametern, anstatt eine separate Fensterklasse für jede Klasse erste teilt jede Klasse die gleichen Fensterklasse. Dies kann Probleme verursachen, wenn die **CS_CLASSDC** Klassenstil verwendet wird. Anstatt mehrere **CS_CLASSDC** Fensterklassen, Sie am Ende einer **CS_CLASSDC** Fensterklasse und alle C++-Fenster, in denen die Klasse gemeinsam nutzen, den gleichen Domänencontroller. Um dieses Problem zu vermeiden, rufen [AfxRegisterClass](#afxregisterclass) zum Registrieren der Klasse.  
  
 Finden Sie in der technischen Hinweis [TN001: Fensterklassenregistrierung](../../mfc/tn001-window-class-registration.md) Weitere Informationen zu fensterklassenregistrierung und die `AfxRegisterWndClass` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration  
 Legt fest, ob die Anwendung den Registrierungszugriff auf leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Gibt an, dass die Registrierungsinformationen weitergeleitet wird die **HKCU** Knoten `FALSE` gibt an, dass die Anwendung auf den Standardknoten für die Informationen in der Registrierung schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Hinweise  
 Vor dem [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], Anwendungen, die in der Regel Zugriff auf die Registrierung der **HKEY_CLASSES_ROOT** Knoten. Allerdings bei [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], müssen Sie eine Anwendung ausführen, im erweiterten Modus zum Schreiben in **HKCR**.  
  
 Diese Methode ermöglicht der Anwendung zu lesen und Schreiben in die Registrierung ohne Ausführung im Modus mit erhöhten Rechten durch das Umleiten von Registrierungszugriff von **HKCR** auf **HKCU**. Weitere Informationen finden Sie unter [Linker-Eigenschaftenseiten](../../ide/linker-property-pages.md).  
  
 Wenn Sie die registrierungsumleitung aktivieren, leitet das Framework den Zugriff auf **HKCR** auf **HKEY_CURRENT_USER\Software\Classes**. Die Umleitung sind nur für die MFC und ATL-Frameworks betroffen.  
  
 Die standardmäßige Implementierung greift auf die Registrierung unter **HKCR**.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxstat_.h    
  
##  <a name="afxsetresourcehandle"></a>AfxSetResourceHandle  
 Mit dieser Funktion können Sie legen die `HINSTANCE` -Handle, das bestimmt, wo die Standardressourcen der Anwendung geladen werden.  
  
```  
 
void  
AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>Parameter  
 `hInstResource`  
 Die Instanz oder ein Modul Handle für ein. EXE- oder DLL-Datei aus dem die Ressourcen der Anwendung geladen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing #135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="afxsocketinit"></a>AfxSocketInit  
 Rufen Sie diese Funktion in Ihrer `CWinApp::InitInstance` Außerkraftsetzung Windows Sockets nicht initialisieren.  
  
```  
 
BOOL  
AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 `lpwsaData`  
 Ein Zeiger auf eine [WSADATA](../../mfc/reference/wsadata-structure.md) Struktur. Wenn `lpwsaData` stimmt nicht mit `NULL`, klicken Sie dann die Adresse der `WSADATA` Struktur wird ausgefüllt, durch den Aufruf von `WSAStartup`. Diese Funktion wird auch sichergestellt, dass `WSACleanup` für Sie aufgerufen wird, bevor die Anwendung beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie MFC-Sockets in sekundären Threads in einer statisch verknüpften MFC_Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jedem Thread, der Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. Standardmäßig `AfxSocketInit` nur im primären Thread aufgerufen wird.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** Datei afxsock.h  
  
##  <a name="afxwininit"></a>AfxWinInit  
 Diese Funktion wird aufgerufen, von dem MFC bereitgestellten `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) Initialisierung einer GUI-basierte Anwendung, zum Initialisieren von MFC.  
  
```  
 
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,  
    HINSTANCE hPrevInstance,  
    LPTSTR lpCmdLine,  
    int nCmdShow);  
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Das Handle des derzeit ausgeführten Moduls.  
  
 *hPrevInstance*  
 Ein Handle für eine frühere Instanz der Anwendung. Für eine Win32-basierte Anwendung dieser Parameter ist immer **NULL**.  
  
 `lpCmdLine`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die die Befehlszeile für die Anwendung angeben.  
  
 `nCmdShow`  
 Gibt an, wie das Hauptfenster einer GUI-Anwendung angezeigt werden würden.  
  
### <a name="remarks"></a>Hinweise  
 Für eine Konsolenanwendung, die nicht verwendet MFC bereitgestellte `WinMain` -Funktion, die Sie aufrufen müssen `AfxWinInit` direkt zum Initialisieren von MFC.  
  
 Beim Aufrufen `AfxWinInit` selbst, sollten Sie eine Instanz von Deklarieren einer `CWinApp` Klasse. Für eine Konsolenanwendung, empfiehlt sich nicht leiten Sie eine eigene Klasse von `CWinApp` und stattdessen eine Instanz von `CWinApp` direkt. Dieses Verfahren ist geeignet, wenn Sie sich entscheiden, lassen Sie alle Funktionen für Ihre Anwendung in der Implementierung von **main**.  
  
> [!NOTE]
>  Wenn es einen Aktivierungskontext für eine Assembly erstellt, verwendet MFC eine Manifestressource, die vom Benutzermodul bereitgestellt. Der Aktivierungskontext wird erstellt, `AfxWinInit`. Weitere Informationen finden Sie unter [Unterstützung für Aktivierungskontexte im MFC-Modulstatus](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_AfxWinInit Nr. 1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)

