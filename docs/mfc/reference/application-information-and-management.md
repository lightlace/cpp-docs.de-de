---
title: Anwendungsinformationen und Verwaltung | Microsoft-Dokumentation
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cc9adde202f211d6e0a536e949b42772f0890ef6
ms.lasthandoff: 02/24/2017

---
# <a name="application-information-and-management"></a>Anwendungsinformationen und Anwendungsverwaltung
Wenn Sie eine Anwendung schreiben, erstellen Sie eine einzelne [CWinApp](../../mfc/reference/cwinapp-class.md)-abgeleitetes Objekt. Sie möchten von Zeit zu Zeit erhalten Informationen über dieses Objekt außerhalb der `CWinApp`-abgeleitetes Objekt.  
  
 Die Microsoft Foundation Class-Bibliothek bietet die folgenden globalen Funktionen, damit Sie diese Aufgaben ausführen können:  
  
### <a name="application-information-and-management-functions"></a>Informationen zur Anwendung und Management-Funktionen  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|Erstellt einen neuen Thread.|  
|[AfxEndThread](#afxendthread)|Beendet den aktuellen Thread.|  
|["AfxFreeLibrary"](#afxfreelibrary)|Dekrementiert den Verweiszähler des Moduls geladenen Dynamic Link Library (DLL); Wenn der Verweiszähler&0; erreicht, ist das Modul nicht zugeordnet.|  
|[AfxGetApp](#afxgetapp)|Gibt ein Zeiger auf die Anwendung einzelne's `CWinApp` Objekt.|  
|[AfxGetAppName](#afxgetappname)|Gibt eine Zeichenfolge, die den Namen der Anwendung enthält.|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|Gibt eine `HINSTANCE` , die dieser Instanz der Anwendung darstellt.|  
|[AfxGetMainWnd](#afxgetmainwnd)|Gibt einen Zeiger auf das aktuelle "main" von einer nicht-OLE-Anwendung oder das direkte Rahmenfenster der Server-Anwendung.|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|Mit dieser Funktion können Sie bestimmen, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|Gibt ein `HINSTANCE` an die Quelle von Standardressourcen für die Anwendung. Verwenden Sie diese Option, um die Ressourcen der Anwendung direkt zuzugreifen.|  
|[AfxGetThread](#afxgetthread)|Ruft einen Zeiger auf die aktuelle [CWinThread](../../mfc/reference/cwinthread-class.md) Objekt.|  
|[AfxInitRichEdit](#afxinitrichedit)|Initialisiert die Version 1.0 Rich-Edit-Steuerelement für die Anwendung.|  
|[AfxInitRichEdit2](#afxinitrichedit2)|Initialisiert die Version 2.0 und höher Rich-Edit-Steuerelement für die Anwendung.|  
|["AfxLoadLibrary"](#afxloadlibrary)|Ordnet ein DLL-Modul, und gibt ein Handle, das zum Abrufen der Adresse einer DLL-Funktion verwendet werden kann.|  
|[AfxRegisterClass](#afxregisterclass)|Eine Fensterklasse registriert, in einer DLL, die MFC verwenden.|  
|[AfxRegisterWndClass](#afxregisterwndclass)|Registriert eine Windows-Fensterklasse die registriert sind, automatisch von MFC zu ergänzen.|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|Legt die `HINSTANCE` Handle, in denen die Standardressourcen der Anwendung geladen werden.|  
|[AfxSocketInit](#afxsocketinit)|Namen in einem `CWinApp::InitInstance` überschreiben, um die Windows Sockets nicht initialisieren.|  
|[AfxWinInit](#afxwininit)|Von MFC bereitgestellte aufgerufen `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) Initialisierung einer GUI-basierte Anwendung, zum Initialisieren von MFC. Muss für konsolenanwendungen direkt aufgerufen werden, die MFC verwenden.|  
  

  
##  <a name="a-nameafxbeginthreada--afxbeginthread"></a><a name="afxbeginthread"></a>AfxBeginThread  
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
 Zeigt auf die Steuerungsfunktion für den Arbeitsthread. Nicht **NULL**. Diese Funktion muss wie folgt deklariert werden:  
  
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
  
- **CREATE_SUSPENDED** der Thread mit einem Unterbrechungszähler&1; gestartet. Verwendung **CREATE_SUSPENDED** Wenn Sie beliebige Memberdaten des initialisieren möchten die `CWinThread` Objekt, z. B. [M_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) oder Member der abgeleiteten Klasse, bevor der Thread gestartet. Sobald die Initialisierung abgeschlossen ist, verwenden Sie [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) auf den Thread zu starten. Der Thread wird erst ausgeführt, wenn `CWinThread::ResumeThread` aufgerufen wurde.  
  
- **0** der Thread wird unmittelbar nach der Erstellung gestartet.  
  
 `lpSecurityAttrs`  
 Verweist auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die die Sicherheitsattribute für den Thread angibt. Wenn **NULL**, die gleichen Sicherheitsattribute der erstellende Thread verwendet wird. Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das neu erstellte Threadobjekt oder **NULL** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Mit der ersten Form von `AfxBeginThread` wird ein Arbeitsthread erstellt. Mit der zweiten Form wird ein Thread erstellt, der als Benutzeroberflächenthread oder als Arbeitsthread dienen kann.  
  
 `AfxBeginThread`erstellt ein neues `CWinThread` Objekt, ruft seine [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) Funktion, um die Ausführung des Threads gestartet und gibt einen Zeiger auf den Thread. Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte. Um den Thread zu beenden, rufen [AfxEndThread](#afxendthread) aus dem Thread oder aus der Steuerungsfunktion des Arbeitsthreads zurück.  
  
 Multithreading muss durch die Anwendung aktiviert werden, andernfalls erzeugt diese Funktion einen Fehler. Weitere Informationen zum Aktivieren des Multithreadings finden Sie unter [/MD, / MT, / ld (Laufzeitbibliothek verwenden)](../../build/reference/md-mt-ld-use-run-time-library.md) unter *Visual C++-Compileroptionen*.  
  
 Weitere Informationen zu `AfxBeginThread`, finden Sie in den Artikeln [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md) und [Multithreading: Erstellen von Benutzeroberflächenthreads](../../parallel/multithreading-creating-user-interface-threads.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxendthreada--afxendthread"></a><a name="afxendthread"></a>AfxEndThread  
 Rufen Sie diese Funktion, um den gerade ausgeführten Thread zu beenden.  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>Parameter  
 *nExitCode*  
 Gibt den Exitcode des Threads.  
  
 *bLöschen*  
 Das Threadobjekt aus dem Speicher gelöscht.  
  
### <a name="remarks"></a>Hinweise  
 Muss von innerhalb der zu beendenden Thread aufgerufen werden.  
  
 Weitere Informationen zu `AfxEndThread`, finden Sie im Artikel [Multithreading: Beenden von Threads](../../parallel/multithreading-terminating-threads.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxfreelibrarya--afxfreelibrary"></a><a name="afxfreelibrary"></a>"AfxFreeLibrary"  
 Beide `AfxFreeLibrary` und `AfxLoadLibrary` einen Verweiszähler für die einzelnen geladenen Module verwalten.  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>Parameter  
 *hInstLib*  
 Ein Handle des geladenen Moduls. [AfxLoadLibrary](#afxloadlibrary) dieses Handle zurückgibt.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die Funktion erfolgreich ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 `AfxFreeLibrary`Dekrementiert den Verweiszähler des Moduls geladenen Dynamic Link Library (DLL). Wenn der Verweiszähler&0; erreicht, das Modul nicht aus dem Adressraum des aufrufenden Prozesses zugeordnet ist, und das Handle nicht mehr gültig ist. Diese Verweiszähler erhöht sich beim `AfxLoadLibrary` aufgerufen wird.  
  
 Vor dem Aufheben der Zuordnung eines Moduls Bibliothek, kann das System die DLL So trennen Sie die Prozesse verwendet wird. Auf diese Weise hat der DLL Gelegenheit zum Bereinigen von Ressourcen, die für den aktuellen Prozess zugewiesen wird. Nachdem die Einstiegspunktfunktion zurückgibt, wird das Modul aus dem Adressraum des aktuellen Prozesses entfernt.  
  
 Verwendung `AfxLoadLibrary` ein DLL-Modul zugeordnet.  
  
 Verwenden Sie `AfxFreeLibrary` und `AfxLoadLibrary` (anstelle der Win32-Funktionen **FreeLibrary** und **LoadLibrary**) Wenn Ihre Anwendung mehrere Threads verwendet. Mithilfe von `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass den starten und Herunterfahren Code, der ausgeführt wird, wenn die Erweiterung DLL geladen und entladen den globalen MFC-Status nicht beschädigt ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [AfxLoadLibrary](#afxloadlibrary).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdll_.h  
  
##  <a name="a-nameafxgetappa--afxgetapp"></a><a name="afxgetapp"></a>AfxGetApp  
 Der von dieser Funktion zurückgegebenen Zeiger kann verwendet werden, Zugriff auf Anwendungsinformationen z. B. den Code für die Haupt-Senden von Nachrichten oder das oberste Fenster.  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den einzelnen `CWinApp` -Objekt für die Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode NULL zurückgibt, darauf, dass das ermöglicht€™ s-Hauptfenster wurde nicht vollständig initialisiert noch. Es kann ebenfalls ein Problem hinweisen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#126;](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxgetappnamea--afxgetappname"></a><a name="afxgetappname"></a>AfxGetAppName  
 Die Zeichenfolge, die von dieser Funktion zurückgegebenen kann für temporäre Zeichenfolgennamen für Fehlermeldungen oder als Stamm verwendet werden.  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine auf Null endende Zeichenfolge, die den Namen der Anwendung enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[127 NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxgetinstancehandlea--afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>AfxGetInstanceHandle  
 Mit dieser Funktion können Sie das Instanzhandle der aktuellen Anwendung abrufen.  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HINSTANCE` mit der aktuellen Instanz der Anwendung. Wenn Sie von einer mit der USRDLL-Version von MFC verknüpften DLL aufgerufen ein `HINSTANCE` mit der DLL zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 `AfxGetInstanceHandle`Gibt immer die `HINSTANCE` der ausführbaren Datei (. (EXE), wenn sie, innerhalb aufgerufen wird eine DLL mit der USRDLL-Version von MFC verknüpft. In diesem Fall gibt es eine `HINSTANCE` auf die DLL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#128;](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxgetmainwnda--afxgetmainwnd"></a><a name="afxgetmainwnd"></a>AfxGetMainWnd  
 Wenn Ihre Anwendung einen OLE-Server ist, rufen Sie diese Funktion rufen Sie einen Zeiger auf das aktiven Hauptfenster der Anwendung und nicht direkt auf die [M_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) Member des Anwendungsobjekts.  
  
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
 [!code-cpp[NVC_MFCWindowing&#129;](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxgetperuserregistrationa--afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration  
 Mit dieser Funktion können Sie bestimmen, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Gibt an, dass die Registrierungsinformationen geleitet wird die **HKCU** Knoten; `FALSE` gibt an, dass die Anwendung Informationen in der Registrierung auf dem Knoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie den registrierungsumleitung aktivieren, leitet das Framework Zugriff auf **HKCR** auf **HKEY_CURRENT_USER\Software\Classes**. Die Umleitung sind nur die MFC- und ATL-Frameworks betroffen.  
  
 Verwenden Sie zum Ändern, ob die Anwendung Zugriff auf die Registrierung leitet [AfxSetPerUserRegistration](#afxsetperuserregistration).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxstat_.h    
  
##  <a name="a-nameafxgetresourcehandlea--afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>AfxGetResourceHandle  
 Verwenden der `HINSTANCE` von dieser Funktion auf die Ressourcen der Anwendung direkt, z. B. in Aufrufe an die Windows-Funktion zurückgegebene Handle **FindResource**.  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `HINSTANCE` Handle, in denen die Standardressourcen der Anwendung geladen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#130;](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxgetthreada--afxgetthread"></a><a name="afxgetthread"></a>AfxGetThread  
 Mit dieser Funktion können Sie einen Zeiger auf die [CWinThread](../../mfc/reference/cwinthread-class.md) Objekt, das den derzeit ausgeführten Thread darstellt.  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf den gerade ausgeführten Thread; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Muss aus dem gewünschten Thread aufgerufen werden.  
  
> [!NOTE]
>  Wenn Sie ein MFC-Projekt aufrufen Portieren `AfxGetThread` von Visual C++-Versionen 4.2, 5.0 oder 6.0, `AfxGetThread` Aufrufe [AfxGetApp](#afxgetapp) Wenn keine Threads gefunden wird. In Visual c++ .NET und höher `AfxGetThread` gibt **NULL** keinen Thread gefunden wurde. Thread der Anwendung werden soll, rufen Sie `AfxGetApp`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#132;](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxinitrichedita--afxinitrichedit"></a><a name="afxinitrichedit"></a>AfxInitRichEdit  
 Rufen Sie diese Funktion, um das rich-Edit-Steuerelement (Version 1.0) für die Anwendung zu initialisieren.  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist für die Abwärtskompatibilität bereitgestellt. Anwendung mit Visual C++ .NET und höher erstellt [AfxInitRichEdit2](#afxinitrichedit2).  
  
 `AfxInitRichEdit`Lädt RICHED32. DLL Version 1.0 des rich-Edit-Steuerelements initialisiert werden. Verwenden Sie Version 2.0 und 3.0 des rich-Edit-Steuerelements RICHED20. Die DLL muss geladen werden. Dies erfolgt mit einem Aufruf von [AfxInitRichEdit2](#afxinitrichedit2). Wenn Sie Ressourcen mit dem rich-Edit-Steuerelement vor Visual C++ .NET erstellt haben, sind die rich-Edit-Steuerelemente automatisch Version 1.0. Rich-Edit-Steuerelemente mit der Ressourcen-Editor von Visual C++ .NET eingefügt werden, Version 2.0.  
  
 Öffnen Sie zum Aktualisieren von rich-Edit-Steuerelemente in vorhandenen Visual C++-Anwendung auf Version 2.0 der. RC-Datei als Text, ändern Sie den Namen der einzelnen rich Edit-Steuerelement von "RICHEDIT", "RichEdit20a". Ersetzen Sie den Aufruf von `AfxInitRichEdit` mit `AfxInitRichEdit2`.  
  
 Diese Funktion initialisiert auch common Controls-Bibliothek, wenn die Bibliothek für den Prozess bereits initialisiert wurde. Wenn Sie die rich-Edit-Steuerelement direkt aus einer MFC-Anwendung verwenden, sollten Sie durch Aufrufen dieser Funktion können Sie sicherstellen, dass die rich-Edit-Steuerelement-Laufzeit von MFC ordnungsgemäß initialisiert wurde. Wenn Sie die Create-Methode der Aufrufen [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), Sie in der Regel müssen diese Funktion aufrufen, aber in einigen Fällen ist es möglicherweise erforderlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxinitrichedit2a--afxinitrichedit2"></a><a name="afxinitrichedit2"></a>AfxInitRichEdit2  
 Rufen Sie diese Funktion, um das rich-Edit-Steuerelement (Version 2.0 und höher) für die Anwendung zu initialisieren.  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Laden der RICHED20. DLL, und initialisieren Sie Version 2.0 von der Rich-edit-Steuerelement. Wenn Sie die Create-Methode der Aufrufen [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), oder [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), Sie in der Regel müssen diese Funktion aufrufen, aber in einigen Fällen ist es möglicherweise erforderlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxloadlibrarya--afxloadlibrary"></a><a name="afxloadlibrary"></a>"AfxLoadLibrary"  
 Verwendung `AfxLoadLibrary` ein DLL-Modul zugeordnet.  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>Parameter  
 *lpszModuleName*  
 Verweist auf eine auf Null endende Zeichenfolge, die den Namen des Moduls enthält (entweder ein. DLL oder. EXE-Datei). Der angegebene Name ist der Dateiname des Moduls.  
  
 Wenn die Zeichenfolge einen Pfad gibt, aber die Datei im angegebenen Verzeichnis nicht vorhanden, schlägt der Vorgang fehl.  
  
 Wenn kein Pfad angegeben ist, und die Erweiterung ausgelassen wird, automatisch hinzugefügt. DLL wird angefügt. Allerdings kann die Filename-Zeichenfolge an, dass der Name des Moduls keine Erweiterung besitzt ein nachfolgendes Punkt Zeichen (.) enthalten. Wenn kein Pfad angegeben ist, sucht die Funktion für die Datei in der folgenden Reihenfolge:  
  
-   Das Verzeichnis, aus dem die Anwendung geladen.  
  
-   Das aktuelle Verzeichnis.  
  
- **Windows 95/98:** Windows-Systemverzeichnis. **Windows NT:** 32-Bit-Windows-Systemverzeichnis. Der Name dieses Verzeichnisses ist "System32".  
  
- **Nur Windows NT:** der 16-Bit-Windows-Systemverzeichnis. Es gibt keine Win32-Funktion, die den Pfad für dieses Verzeichnis abruft, sondern gesucht. Der Name dieses Verzeichnisses ist SYSTEM.  
  
-   Das Windows-Verzeichnis.  
  
-   Die Verzeichnisse, die in der PATH-Umgebungsvariablen aufgelistet sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ein Handle für das Modul. Wenn die Funktion fehlschlägt, ist der Rückgabewert NULL.  
  
### <a name="remarks"></a>Hinweise  
 Es gibt ein Handle, das verwendet werden kann [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) einer DLL-Funktion abzurufen. `AfxLoadLibrary`kann auch verwendet werden, um andere ausführbare Module zuzuordnen.  
  
 Jeder Prozess verwaltet einen Verweiszähler für jedes geladenen Modul. Diese Verweiszähler erhöht sich beim `AfxLoadLibrary` aufgerufen und wird wieder um eins erniedrigt jedem `AfxFreeLibrary` aufgerufen wird. Wenn der Verweiszähler&0; erreicht, das Modul nicht aus dem Adressraum des aufrufenden Prozesses zugeordnet ist, und das Handle nicht mehr gültig ist.  
  
 Verwenden Sie `AfxLoadLibrary` und `AfxFreeLibrary` (anstelle der Win32-Funktionen **LoadLibrary** und **FreeLibrary**) Wenn Ihre Anwendung mehrere Threads verwendet, und wenn es dynamisch eine Erweiterung DLL laden. Mithilfe von `AfxLoadLibrary` und `AfxFreeLibrary` wird sichergestellt, dass der starten und Herunterfahren Code, der ausgeführt wird, wenn die Erweiterung DLL geladen und entladen wird, den globalen MFC-Status nicht beschädigt ist.  
  
 Mithilfe von `AfxLoadLibrary` in einer Anwendung erfordert, dass Sie dynamisch auf die DLL-Version von MFC verknüpfen die Headerdatei für `AfxLoadLibrary`, Afxdll_.h, ist nur enthalten, wenn die Anwendung als DLL MFC verknüpft ist. Dies ist beabsichtigt, da Sie um eine Verknüpfung mit der DLL-Version von MFC oder Erweiterungs-DLLs haben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_DLLUser&#1;](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser&#2;](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser&3;](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdll_.h  
   
  
##  <a name="a-nameafxregisterclassa--afxregisterclass"></a><a name="afxregisterclass"></a>AfxRegisterClass  
 Verwenden Sie diese Funktion zum Registrieren von Fensterklassen in einer DLL, die MFC verwenden.  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>Parameter  
 *lpWndClass*  
 Zeiger auf eine [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Struktur mit Informationen über die Fensterklasse registriert werden. Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die Klasse erfolgreich registriert; andernfalls ist **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion verwenden, ist die Klasse automatisch aufgehoben, wenn die DLL entladen wird.  
  
 In nicht-DLL-Builds die `AfxRegisterClass` Bezeichner ist definiert als ein Makro, um die Windows-Funktion **RegisterClass**, da die Klassen in einer Anwendung registriert automatisch aufgehoben werden. Bei Verwendung von `AfxRegisterClass` anstelle von **RegisterClass**, Ihren Code ohne Änderung in einer Anwendung sowohl in einer DLL verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_DLL&3;](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxregisterwndclassa--afxregisterwndclass"></a><a name="afxregisterwndclass"></a>AfxRegisterWndClass  
 Können Sie Ihre eigenen Klassen zu registrieren.  
  
```  
 
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>Parameter  
 *nClassStyle*  
 Gibt den Stil für Windows-Klasse oder eine Kombination von Stilen, die mit dem bitweisen OR-erstellt ( **|**)-Operator für Window-Klasse. Eine Liste der Klasse Formate finden Sie unter der [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn **NULL**, die Standardwerte werden wie folgt festgelegt werden:  
  
-   Legt das Format der Maus auf **CS_DBLCLKS**, welche sendet Nachrichten an die Fensterprozedur doppelklicken, wenn der Benutzer die Maus doppelklickt.  
  
-   Legt die Art des Pfeils Cursor mit dem Windows-Standard **IDC_ARROW**.  
  
-   Legt den Pinsel für den Hintergrund auf **NULL**, sodass das Fenster den Hintergrund nicht gelöscht werden.  
  
-   Wird das Symbol standard, Winkende Flag Windows Logo-Symbol.  
  
 `hCursor`  
 Gibt ein Handle für die Cursor-Ressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, erhalten Sie den Standard **IDC_ARROW** Cursor.  
  
 *hbrBackground*  
 Gibt ein Handle für die Pinselressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, müssen eine **NULL** Hintergrundpinsel und Fenster wird, wird standardmäßig nicht den Hintergrund während der Verarbeitung löschen [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055).  
  
 `hIcon`  
 Gibt ein Handle für die Symbolressource in jedem Fenster aus der Fensterklasse erstellt installiert werden. Wenn Sie die Standardeinstellung verwenden **0**, erhalten Sie die standardmäßige, Winkende Flag Windows Logo-Symbol.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine auf Null endende Zeichenfolge, die den Klassennamen enthält. Sie können diese Namen der Klasse, übergeben die **erstellen** -Memberfunktion `CWnd` oder andere **CWnd -**abgeleiteten Klassen zum Erstellen eines Fensters. Der Name wird von der Microsoft Foundation Class-Bibliothek generiert.  
  
> [!NOTE]
>  Der Rückgabewert ist ein Zeiger auf einen statischen Puffer. Wenn diese Zeichenfolge speichern möchten, weisen Sie ihn einer `CString` Variable.  
  
### <a name="remarks"></a>Hinweise  
 Die Microsoft Foundation Class-Bibliothek registriert, mehrere automatisch für Sie. Rufen Sie diese Funktion, wenn Sie Ihre eigenen Klassen registrieren möchten.  
  
 Registrierter Name für eine Klasse von `AfxRegisterWndClass` ausschließlich hängt von den Parametern. Wenn Sie aufrufen `AfxRegisterWndClass` mehrmals mit identischen Parametern registriert nur eine Klasse beim ersten Aufruf. Nachfolgende Aufrufe von `AfxRegisterWndClass` mit identischen Parametern einfach die bereits registrierten Classname zurückgeben.  
  
 Wenn Sie aufrufen `AfxRegisterWndClass` für mehrere CWnd abgeleitete Klassen mit identischen Parametern, anstatt eine separate Windows-Klasse für jede Klasse abrufen jedes gemeinsam dieselbe Fensterklasse. Dies kann Probleme verursachen, wenn die **CS_CLASSDC** Klassenstil verwendet wird. Anstatt mehrere **CS_CLASSDC** Fensterklassen, erhalten Sie eine **CS_CLASSDC** Window-Klasse, und alle C++-Fenster, in denen, die Klasse gemeinsam verwenden, derselbe Domänencontroller. Um dieses Problem zu vermeiden, rufen Sie [AfxRegisterClass](#afxregisterclass) zum Registrieren der Klasse.  
  
 Lesen Sie bitte zu technischen [TN001: Fensterklassenregistrierung](../../mfc/tn001-window-class-registration.md) Informationen zur Registrierung von Fensterklassen und die `AfxRegisterWndClass` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#134;](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxsetperuserregistrationa--afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration  
 Legt fest, ob die Anwendung Zugriff auf die Registrierung, leitet die **HKEY_CURRENT_USER** ( **HKCU**) Knoten.  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Gibt an, dass die Registrierungsinformationen geleitet wird die **HKCU** Knoten; `FALSE` gibt an, dass die Anwendung Informationen in der Registrierung auf dem Knoten schreibt. Der Standardknoten ist **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>Hinweise  
 Vor dem [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], Anwendungen, die in der Regel Zugriff auf die Registrierung der **HKEY_CLASSES_ROOT** Knoten. Allerdings können mit [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], müssen Sie eine Anwendung ausführen, im erweiterten Modus zum Schreiben in **HKCR**.  
  
 Diese Methode ermöglicht der Anwendung zu lesen und Schreiben in die Registrierung, ohne im erhöhten Modus ausführen, durch das Umleiten von Zugriff auf die Registrierung von **HKCR** auf **HKCU**. Weitere Informationen finden Sie unter [Linker-Eigenschaftenseiten](../../ide/linker-property-pages.md).  
  
 Wenn Sie den registrierungsumleitung aktivieren, leitet das Framework Zugriff auf **HKCR** auf **HKEY_CURRENT_USER\Software\Classes**. Die Umleitung sind nur die MFC- und ATL-Frameworks betroffen.  
  
 Die standardmäßige Implementierung greift auf die Registrierung unter **HKCR**.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxstat_.h    
  
##  <a name="a-nameafxsetresourcehandlea--afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>AfxSetResourceHandle  
 Verwenden Sie diese Funktion zum Festlegen der `HINSTANCE` -Handle, das bestimmt, wo die Ressourcen für die Anwendung geladen werden.  
  
```  
 
void  
AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>Parameter  
 `hInstResource`  
 Die Instanz oder ein Modul-Handle für ein. EXE oder DLL-Datei von der die Ressourcen der Anwendung geladen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#135;](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
  
##  <a name="a-nameafxsocketinita--afxsocketinit"></a><a name="afxsocketinit"></a>AfxSocketInit  
 Rufen Sie diese Funktion Ihrer `CWinApp::InitInstance` überschreiben, um die Windows Sockets nicht initialisieren.  
  
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
 Wenn Sie MFC-Sockets in sekundären Threads in einer statisch gebunden mit MFC_Anwendung verwenden zu können, müssen Sie aufrufen `AfxSocketInit` in jedem Thread, die Sockets verwendet, um die Socket-Bibliotheken zu initialisieren. In der Standardeinstellung `AfxSocketInit` wird nur im primären Thread aufgerufen.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** Datei afxsock.h  
  
##  <a name="a-nameafxwininita--afxwininit"></a><a name="afxwininit"></a>AfxWinInit  
 Diese Funktion wird aufgerufen, von der MFC bereitgestellten `WinMain` Funktion als Teil der [CWinApp](../../mfc/reference/cwinapp-class.md) Initialisierung einer GUI-basierte Anwendung, zum Initialisieren von MFC.  
  
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
 Ein Handle zu einer vorherigen Instanz der Anwendung. Für eine Win32-basierte Anwendung, ist dieser Parameter immer **NULL**.  
  
 `lpCmdLine`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die die Befehlszeile für die Anwendung angeben.  
  
 `nCmdShow`  
 Gibt an, wie das Hauptfenster der GUI-Anwendung angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Für eine Konsolenanwendung, die verwendet nicht die MFC bereitgestellte `WinMain` -Funktion, die Sie aufrufen müssen `AfxWinInit` direkt in MFC zu initialisieren.  
  
 Wenn Sie aufrufen `AfxWinInit` selbst durchführen, sollten Sie eine Instanz des Deklarieren einer `CWinApp` Klasse. Für eine Konsolenanwendung empfiehlt sich nicht, leiten Sie eine eigene Klasse von `CWinApp` und stattdessen eine Instanz der `CWinApp` direkt. Dieses Verfahren ist geeignet, wenn Sie sich entscheiden, lassen Sie alle Funktionen für die Anwendung in der Implementierung der **wichtigsten**.  
  
> [!NOTE]
>  Wenn es einen Aktivierungskontext für eine Assembly erstellt, verwendet MFC eine Manifestressource, die vom Benutzermodul bereitgestellt. Der Aktivierungskontext wird erstellt, `AfxWinInit`. Weitere Informationen finden Sie unter [Unterstützung für Aktivierungskontexte im MFC-Modulstatus](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_AfxWinInit&#1;](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxwin.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp-Klasse](../../mfc/reference/cwinapp-class.md)

