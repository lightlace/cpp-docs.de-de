---
title: Klasse CAtlServiceModuleT | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlServiceModuleT
- ATL.CAtlServiceModuleT
- CAtlServiceModuleT
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
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
ms.openlocfilehash: c8fcadca667b618d9e5f112d7910c8e6e6f6c65d
ms.lasthandoff: 02/24/2017

---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT-Klasse
Diese Klasse implementiert einen Dienst.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 Der Ressourcenbezeichner des Diensts.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|Die Ereignishandler-Routine für den Dienst.|  
|[CAtlServiceModuleT:: InitializeSecurity](#initializesecurity)|Stellt die Sicherheitseinstellungen für den Dienst.|  
|[CAtlServiceModuleT::Install](#install)|Installiert und den Dienst erstellt.|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Bestätigt, dass der Dienst installiert wurde.|  
|[CAtlServiceModuleT::LogEvent](#logevent)|In das Ereignisprotokoll geschrieben.|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Überschreiben Sie diese Methode, um den Dienst fortzusetzen.|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Überschreiben Sie diese Methode, um den Dienst abzufragen.|  
|[CAtlServiceModuleT::OnPause](#onpause)|Überschreiben Sie diese Methode, um den Dienst anzuhalten.|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Überschreiben Sie diese Methode, um den Dienst beenden|  
|[CAtlServiceModuleT::OnStop](#onstop)|Überschreiben Sie diese Methode zum Beenden des Dienstes|  
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Überschreiben Sie diese Methode zum Behandeln der Unbekannter Anforderungen an den Dienst|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Analysiert die Befehlszeile, und führt die Registrierung bei Bedarf.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Der Dienst registriert in der Registrierung.|  
|[CServiceModule:: Run](#run)|Der Dienst wird ausgeführt.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Die Methode aufgerufen, indem der Dienstkontroll-Manager.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Aktualisiert den Dienststatus.|  
|[CServiceModule:: Start](#start)|Aufgerufen von `CAtlServiceModuleT::WinMain` Wenn der Dienst gestartet wird.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|Beendet, und den Dienst entfernt.|  
|[CAtlServiceModuleT::Unlock](#unlock)|Verringert die Sperrenanzahl des Diensts.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Entfernt den Dienst aus der Registrierung.|  
|[CAtlServiceModuleT::WinMain](#winmain)|Diese Methode implementiert den Code zum Ausführen des Dienstes erforderlich ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|Ein Flag, der angibt, dass die Anwendung als Dienst ausgeführt wird.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Membervariable, die die Thread-ID gespeichert.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Membervariable, die ein Handle für die Struktur der Status für den aktuellen Dienst speichern.|  
|[CAtlServiceModuleT::m_status](#m_status)|Membervariable, speichern die Struktur der Status für den aktuellen Dienst.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Der Name des Dienstes registriert wird.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlServiceModuleT`, von abgeleiteten [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), ein Modul ATL-Dienst implementiert. `CAtlServiceModuleT`Stellt Methoden zum befehlszeilenverarbeitung, Installation, registrieren und entfernen. Wenn zusätzlicher Funktionalität erforderlich ist, können diese und andere Methoden überschrieben werden.  
  
 Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) verwendet, die in früheren Versionen von ATL Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-namecatlservicemoduleta--catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 Der Konstruktor.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Datenmember initialisiert, und setzt den Status des ersten Service.  
  
##  <a name="a-namehandlera--catlservicemodulethandler"></a><a name="handler"></a>CAtlServiceModuleT::Handler  
 Die Ereignishandler-Routine für den Dienst.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwOpcode*  
 Ein Schalter, der den handlervorgang definiert. Weitere Informationen finden Sie unter den Hinweisen.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist der Code, den der Service Control Manager (SCM) aufruft, zum Abrufen des Status der Dienst "und" Problem Anweisungen wie z. B. beenden oder anhalten. Die SCM übergibt einen Vorgang, der folgende Code, zu `Handler` an, was der Dienst ausführen sollte.  
  
|Vorgangscode|Bedeutung|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|Beendet den Dienst. Überschreiben Sie die Methode [CAtlServiceModuleT::OnStop](#onstop) in atlbase.h, um das Verhalten zu ändern.|  
|SERVICE_CONTROL_PAUSE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnPause](#onpause) in atlbase.h, den Dienst anzuhalten.|  
|SERVICE_CONTROL_CONTINUE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnContinue](#oncontinue) in atlbase.h zum Fortsetzen des Dienstes.|  
|SERVICE_CONTROL_INTERROGATE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnInterrogate](#oninterrogate) in atlbase.h untersucht den Dienst.|  
|SERVICE_CONTROL_SHUTDOWN|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnShutdown](#onshutdown) in atlbase.h zum Herunterfahren des Diensts.|  
  
 Wenn der Vorgang Code erkannt wird, die Methode [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) aufgerufen wird.  
  
 Ein standardmäßige ATL-generierter Dienst verarbeitet nur die Stop-Anweisung. Wenn der SCM die Stop-Anweisung erfolgreich ist, weist den Dienst dem SCM, dass das Programm wird beendet. Der Dienst ruft dann `PostThreadMessage` eine Beenden-Meldung an sich selbst zu veröffentlichen. Dadurch wird die Meldungsschleife beendet und der Dienst schließlich beendet.  
  
##  <a name="a-nameinitializesecuritya--catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a>CAtlServiceModuleT:: InitializeSecurity  
 Stellt die Sicherheitseinstellungen für den Dienst.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 In Visual Studio .NET 2003 ist diese Methode nicht in der Basisklasse implementiert. Der Visual Studio-Projekt-Assistent enthält diese Methode im generierten Code tritt ein Kompilierungsfehler auf, wenn ein Projekt in einer früheren Version von Visual C++ erstellt mithilfe von ATL 7.1 kompiliert wird. Jede Klasse, die von abgeleitet ist `CAtlServiceModuleT` müssen diese Methode in der abgeleiteten Klasse implementieren.  
  
 Verwenden Sie PKT-Authentifizierung, Identitätswechselebene RPC_C_IMP_LEVEL_IDENTIFY und eine entsprechende ungleich Null Sicherheitsdeskriptor im Aufruf von **CoInitializeSecurity**.  
  
 Für nicht attributierte-Assistenten generierte Dienstprojekte wäre in dies  
  
 [!code-cpp[NVC_ATL_Service&#1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 Für attributierte-Dienstprojekte wäre in dies  
  
 [!code-cpp[NVC_ATL_ServiceAttrib&#1;](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="a-nameinstalla--catlservicemoduletinstall"></a><a name="install"></a>CAtlServiceModuleT::Install  
 Installiert und den Dienst erstellt.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Der Dienst in die Datenbank (Service Control Manager, SCM) installiert, und erstellt dann das Dienstobjekt. Wenn der Dienst nicht erstellt werden konnte, ein Meldungsfeld wird angezeigt, und die Methode gibt FALSE zurück.  
  
##  <a name="a-nameisinstalleda--catlservicemoduletisinstalled"></a><a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 Bestätigt, dass der Dienst installiert wurde.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn der Dienst installiert, andernfalls FALSE ist.  
  
##  <a name="a-namelogeventa--catlservicemoduletlogevent"></a><a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 In das Ereignisprotokoll geschrieben.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Die in das Ereignisprotokoll zu schreibende Zeichenfolge.  
  
 ...  
 Optionale zusätzliche Zeichenfolgen in das Ereignisprotokoll geschrieben werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schreibt Informationen in ein Ereignisprotokoll mithilfe der Funktion [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679). Wenn kein Dienst ausgeführt wird, wird die Zeichenfolge an die Konsole gesendet.  
  
##  <a name="a-namembservicea--catlservicemoduletmbservice"></a><a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 Ein Flag, der angibt, dass die Anwendung als Dienst ausgeführt wird.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendet, um eine EXE-Anwendung eine EXE-Dienst unterscheiden.  
  
##  <a name="a-namemdwthreadida--catlservicemoduletmdwthreadid"></a><a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 Membervariable, die den Threadbezeichner des Diensts zu speichern.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable speichert den Threadbezeichner des aktuellen Threads.  
  
##  <a name="a-namemhservicestatusa--catlservicemoduletmhservicestatus"></a><a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 Membervariable, die ein Handle für die Struktur der Status für den aktuellen Dienst speichern.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>Hinweise  
 Die [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) Struktur enthält Informationen über einen Dienst.  
  
##  <a name="a-namemstatusa--catlservicemoduletmstatus"></a><a name="m_status"></a>CAtlServiceModuleT::m_status  
 Membervariable, speichern die Struktur der Status für den aktuellen Dienst.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>Hinweise  
 Die [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) Struktur enthält Informationen über einen Dienst.  
  
##  <a name="a-namemszservicenamea--catlservicemoduletmszservicename"></a><a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 Der Name des Dienstes registriert wird.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>Hinweise  
 Eine auf Null endende Zeichenfolge den Namen des Diensts gespeichert.  
  
##  <a name="a-nameoncontinuea--catlservicemoduletoncontinue"></a><a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 Überschreiben Sie diese Methode, um den Dienst fortzusetzen.  
  
```
void OnContinue() throw();
```  
  
##  <a name="a-nameoninterrogatea--catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 Überschreiben Sie diese Methode, um den Dienst abzufragen.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="a-nameonpausea--catlservicemoduletonpause"></a><a name="onpause"></a>CAtlServiceModuleT::OnPause  
 Überschreiben Sie diese Methode, um den Dienst anzuhalten.  
  
```
void OnPause() throw();
```  
  
##  <a name="a-nameonshutdowna--catlservicemoduletonshutdown"></a><a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 Überschreiben Sie diese Methode, um den Dienst zu schließen.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="a-nameonstopa--catlservicemoduletonstop"></a><a name="onstop"></a>CAtlServiceModuleT::OnStop  
 Überschreiben Sie diese Methode, um den Dienst zu beenden.  
  
```
void OnStop() throw();
```  
  
##  <a name="a-nameonunknownrequesta--catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest  
 Überschreiben Sie diese Methode zum Behandeln der Unbekannter Anforderungen an den Dienst.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>Parameter  
 */\*dwOpcode\*/*  
 Reserviert.  
  
##  <a name="a-nameparsecommandlinea--catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
 Analysiert die Befehlszeile, und führt die Registrierung bei Bedarf.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpCmdLine`  
 Die Befehlszeile.  
  
 `pnRetCode`  
 Das HRESULT der Registrierung (wenn es stattgefunden hat).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True bei Erfolg oder False, wenn die in der Befehlszeile angegebenen RGS-Datei konnte nicht registriert werden.  
  
### <a name="remarks"></a>Hinweise  
 Analysiert die Befehlszeile und registriert, oder hebt die Registrierung der angegebenen RGS-Datei bei Bedarf. Diese Methode ruft [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) Prüfung **/RegServer** und **/Unregserver**. Das Argument hinzufügen **- / Service** wird den Dienst registriert.  
  
##  <a name="a-namepremessageloopa--catlservicemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Dieser Parameter wird zum übergeben [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die benutzerdefinierten Initialisierungscode für den Dienst hinzuzufügen.  
  
##  <a name="a-nameregisterappida--catlservicemoduletregisterappid"></a><a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 Der Dienst registriert in der Registrierung.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *bService*  
 Muss "true", die als Dienst registrieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-nameruna--catlservicemoduletrun"></a><a name="run"></a>CServiceModule:: Run  
 Der Dienst wird ausgeführt.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte in erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt. Der Standardwert ist SW_HIDE.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem aufrufen, **ausführen** Aufrufe [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), und [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).  
  
##  <a name="a-nameservicemaina--catlservicemoduletservicemain"></a><a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
 Diese Methode wird von der Dienstkontroll-Manager aufgerufen.  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwArgc*  
 Argc-Argument.  
  
 *lpszArgv*  
 Das Argv-Argument.  
  
### <a name="remarks"></a>Hinweise  
 Der Service Control Manager (SCM) Ruft `ServiceMain` Wenn Sie die Anwendung Dienste in der Systemsteuerung öffnen, wählen Sie den Dienst, und klicken Sie auf Start.  
  
 Nach dem SCM ruft `ServiceMain`, ein Dienst muss dem SCM eine Handlerfunktion erteilen. Mit dieser Funktion können die SCM der Status des Dienstes zu erhalten, und übergeben Sie spezifische Informationen (z. B. Anhalten oder Beenden). Anschließend [CServiceModule:: Run](#run) aufgerufen, um die eigentliche Arbeit des Diensts durchzuführen. **Führen Sie** weiterhin ausgeführt, bis der Dienst beendet wird.  
  
##  <a name="a-namesetservicestatusa--catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 Diese Methode aktualisiert den Dienststatus.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwState`  
 Der neue Status. Finden Sie unter [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert die Statusinformationen für den Service Control Manager für den Dienst. Wird aufgerufen, indem [CServiceModule:: Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) und andere Handlermethoden. Der Status wird auch in der Membervariablen gespeichert [CAtlServiceModuleT::m_status](#m_status).  
  
##  <a name="a-namestarta--catlservicemoduletstart"></a><a name="start"></a>CServiceModule:: Start  
 Aufgerufen von `CAtlServiceModuleT::WinMain` Wenn der Dienst gestartet wird.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte in erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die [CAtlServiceModuleT::WinMain](#winmain) Methode behandelt, Registrierung und Installation als auch Aufgaben beteiligt Registrierungseinträge werden entfernt, und das Modul zu deinstallieren. Wenn der Dienst ausgeführt wird, `WinMain` Aufrufe **Start**.  
  
##  <a name="a-nameuninstalla--catlservicemoduletuninstall"></a><a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 Beendet, und den Dienst entfernt.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Beendet den Dienst ausgeführt wird, und entfernt sie aus der Dienstkontroll-Manager-Datenbank.  
  
##  <a name="a-nameunlocka--catlservicemoduletunlock"></a><a name="unlock"></a>CAtlServiceModuleT::Unlock  
 Verringert die Sperrenanzahl des Diensts.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sperren, die möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="a-nameunregisterappida--catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 Entfernt den Dienst aus der Registrierung.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="a-namewinmaina--catlservicemoduletwinmain"></a><a name="winmain"></a>CAtlServiceModuleT::WinMain  
 Diese Methode implementiert den Code zum Starten des Diensts erforderlich.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte in erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Dienst Rückgabewert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verarbeitet von der Befehlszeile aus (mit [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) und startet dann den Dienst (mit [CServiceModule:: Start](#start)).  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

