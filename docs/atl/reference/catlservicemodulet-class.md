---
title: CAtlServiceModuleT Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2d059a990b9b01cdfc959284d9fe20f3dfd12af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT-Klasse
Diese Klasse implementiert einen Dienst.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 Der Ressourcenbezeichner des Diensts.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|Die Handlerroutine für den Dienst.|  
|[CAtlServiceModuleT:: InitializeSecurity](#initializesecurity)|Stellt die Sicherheitseinstellungen für den Dienst.|  
|[CAtlServiceModuleT::Install](#install)|Installiert und den Dienst erstellt.|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Bestätigt, dass der Dienst installiert wurde.|  
|[CAtlServiceModuleT::LogEvent](#logevent)|Schreibt in das Ereignisprotokoll geschrieben.|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Überschreiben Sie diese Methode, um den Dienst zu fortfahren.|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Überschreiben Sie diese Methode, um den Dienst abzufragen.|  
|[CAtlServiceModuleT::OnPause](#onpause)|Überschreiben Sie diese Methode, um den Dienst anzuhalten.|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Überschreiben Sie diese Methode beim Herunterfahren des Diensts|  
|[CAtlServiceModuleT::OnStop](#onstop)|Überschreiben Sie diese Methode, um den Dienst beenden|  
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Überschreiben Sie diese Methode zum Behandeln der Unbekannter Anforderungen an den Dienst|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Registriert den Dienst in der Registrierung.|  
|[CServiceModule:: Run](#run)|Der Dienst ausgeführt.|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Die Methode wird aufgerufen, indem der Dienstkontroll-Manager.|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Aktualisiert den Status des Diensts an.|  
|[CServiceModule:: Start](#start)|Wird aufgerufen, indem `CAtlServiceModuleT::WinMain` beim Starten des Diensts.|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|Beendet und entfernt den Dienst.|  
|[CAtlServiceModuleT::Unlock](#unlock)|Verringert die Sperrenanzahl des Diensts.|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Entfernt den Dienst aus der Registrierung.|  
|[CAtlServiceModuleT::WinMain](#winmain)|Diese Methode implementiert den Code zum Ausführen des Diensts erforderlich.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|Ein Flag, der angibt, ob das Programm als Dienst ausgeführt wird.|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Membervariablen gespeichert, die Speichern des Threadbezeichners.|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Die Membervariable ein Handle für die Struktur der Status für den aktuellen Dienst speichern.|  
|[CAtlServiceModuleT::m_status](#m_status)|Speichern die Struktur der Status für den aktuellen Dienst Membervariable.|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Der Name des Diensts, die registriert wird.|  
  
## <a name="remarks"></a>Hinweise  
 `CAtlServiceModuleT`, abgeleitet [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), eine ATL-Dienstmodul implementiert. `CAtlServiceModuleT`Stellt Methoden zum befehlszeilenverarbeitung, Installation, registrieren und entfernen. Wenn zusätzlicher Funktionalität erforderlich ist, können diese und andere Methoden überschrieben werden.  
  
 Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) verwendet, die in früheren Versionen von ATL Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="catlservicemodulet"></a>CAtlServiceModuleT::CAtlServiceModuleT  
 Der Konstruktor.  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert den Datenmember und legt den Status des ursprünglichen Diensts.  
  
##  <a name="handler"></a>CAtlServiceModuleT::Handler  
 Die Handlerroutine für den Dienst.  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dwOpcode*  
 Einem Switch, der der handlervorgang definiert. Weitere Informationen finden Sie unter den Hinweisen.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist der Code, den den Dienststeuerungs-Manager (SCM) aufruft, zum Abrufen des Status für den Dienst und Problem-Anweisungen, wie z. B. beenden oder anhalten. SCM übergibt ein Vorgangscode zu weiter unten gezeigte `Handler` , um anzugeben, wie der Dienst vorgegangen.  
  
|Vorgangscode|Bedeutung|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|Beendet den Dienst. Überschreiben Sie die Methode [CAtlServiceModuleT::OnStop](#onstop) in atlbase.h, um das Verhalten zu ändern.|  
|SERVICE_CONTROL_PAUSE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnPause](#onpause) in atlbase.h, den Dienst anzuhalten.|  
|SERVICE_CONTROL_CONTINUE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnContinue](#oncontinue) in atlbase.h, um den Dienst weiterhin.|  
|SERVICE_CONTROL_INTERROGATE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnInterrogate](#oninterrogate) in atlbase.h, um den Dienst abzufragen.|  
|SERVICE_CONTROL_SHUTDOWN|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnShutdown](#onshutdown) in atlbase.h zum Herunterfahren des Diensts.|  
  
 Wenn der Vorgang Code erkannt wird, die Methode [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) aufgerufen wird.  
  
 Eine ATL generierte Standarddienst verarbeitet nur die Stop-Anweisung. Wenn die SCM Stop-Anweisung übergibt, weist den Dienst dem SCM, dass das Programm beendet. Der Dienst ruft dann `PostThreadMessage` zum Beenden-Meldung mit sich selbst bereitstellen. Die Nachrichtenschleife wird beendet, und der Dienst wird letztendlich geschlossen.  
  
##  <a name="initializesecurity"></a>CAtlServiceModuleT:: InitializeSecurity  
 Stellt die Sicherheitseinstellungen für den Dienst.  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 In Visual Studio .NET 2003 wird diese Methode nicht in der Basisklasse implementiert. Der Visual Studio-Projekt-Assistent bietet diese Methode im generierten Code, jedoch tritt ein Kompilierungsfehler auf, wenn ein Projekt erstellt, die in einer früheren Version von Visual C++ mit ATL 7.1 kompiliert wird. Jede Klasse, die abgeleitet `CAtlServiceModuleT` müssen diese Methode in der abgeleiteten Klasse implementieren.  
  
 Verwenden Sie PKT Anwendungsebene Authentifizierung, Ebene des Identitätswechsels des RPC_C_IMP_LEVEL_IDENTIFY und eine entsprechende ungleich Null Sicherheitsbeschreibung im Aufruf von **CoInitializeSecurity**.  
  
 Für nicht attributierte-Assistenten generierte-Dienstprojekte dazu gehören in der Daten  
  
 [!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 Für die attributierte Dienstprojekte dazu gehören in der Daten  
  
 [!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>CAtlServiceModuleT::Install  
 Installiert und den Dienst erstellt.  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Installiert den Dienst in der Datenbank (Service Control Manager, SCM), und klicken Sie dann das Dienstobjekt erstellt. Wenn der Dienst nicht erstellt werden konnte, wird ein Meldungsfeld wird angezeigt, und gibt die Methode "false" zurück.  
  
##  <a name="isinstalled"></a>CAtlServiceModuleT::IsInstalled  
 Bestätigt, dass der Dienst installiert wurde.  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Dienst installiert, andernfalls FALSE ist.  
  
##  <a name="logevent"></a>CAtlServiceModuleT::LogEvent  
 Schreibt in das Ereignisprotokoll geschrieben.  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Die in das Ereignisprotokoll zu schreibende Zeichenfolge.  
  
 ...  
 Optionale zusätzliche Zeichenfolgen, in das Ereignisprotokoll geschrieben werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schreibt Informationen in ein Ereignisprotokoll mithilfe der Funktion [ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679). Wenn kein Dienst ausgeführt wird, wird die Zeichenfolge an die Konsole gesendet.  
  
##  <a name="m_bservice"></a>CAtlServiceModuleT::m_bService  
 Ein Flag, der angibt, ob das Programm als Dienst ausgeführt wird.  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendet, um eine EXE-Dienst von einer Anwendung exe-Datei zu unterscheiden.  
  
##  <a name="m_dwthreadid"></a>CAtlServiceModuleT::m_dwThreadID  
 Membervariablen gespeichert, die den Threadbezeichner des Diensts zu speichern.  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable speichert den Threadbezeichner des aktuellen Threads.  
  
##  <a name="m_hservicestatus"></a>CAtlServiceModuleT::m_hServiceStatus  
 Die Membervariable ein Handle für die Struktur der Status für den aktuellen Dienst speichern.  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>Hinweise  
 Die [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) Struktur enthält Informationen über einen Dienst.  
  
##  <a name="m_status"></a>CAtlServiceModuleT::m_status  
 Speichern die Struktur der Status für den aktuellen Dienst Membervariable.  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>Hinweise  
 Die [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996) Struktur enthält Informationen über einen Dienst.  
  
##  <a name="m_szservicename"></a>CAtlServiceModuleT::m_szServiceName  
 Der Name des Diensts, die registriert wird.  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Null-terminierte Zeichenfolge den Namen des Diensts gespeichert.  
  
##  <a name="oncontinue"></a>CAtlServiceModuleT::OnContinue  
 Überschreiben Sie diese Methode, um den Dienst zu fortfahren.  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>CAtlServiceModuleT::OnInterrogate  
 Überschreiben Sie diese Methode, um den Dienst abzufragen.  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>CAtlServiceModuleT::OnPause  
 Überschreiben Sie diese Methode, um den Dienst anzuhalten.  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>CAtlServiceModuleT::OnShutdown  
 Überschreiben Sie diese Methode, um den Dienst zu schließen.  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>CAtlServiceModuleT::OnStop  
 Überschreiben Sie diese Methode, um den Dienst zu beenden.  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>CAtlServiceModuleT::OnUnknownRequest  
 Überschreiben Sie diese Methode zum Behandeln der Unbekannter Anforderungen an den Dienst.  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>Parameter  
 */\*dwOpcode\*/*  
 Reserviert.  
  
##  <a name="parsecommandline"></a>CAtlServiceModuleT::ParseCommandLine  
 Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpCmdLine`  
 Die Befehlszeile.  
  
 `pnRetCode`  
 Die Registrierung (falls es stattgefunden hat) entsprechende HRESULT.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg oder "false", wenn die in der Befehlszeile angegebene RGS-Datei konnte nicht registriert werden.  
  
### <a name="remarks"></a>Hinweise  
 Analysiert die Befehlszeile und registriert, oder hebt die Registrierung der angegebenen RGS-Datei bei Bedarf. Diese Methode ruft [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) zu suchende **/RegServer** und **/Unregserver**. Das Argument hinzufügen **- / Service** wird den Dienst registriert.  
  
##  <a name="premessageloop"></a>CAtlServiceModuleT::PreMessageLoop  
 Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Dieser Parameter wird übergeben, um [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die angepasste Initialisierung von Code für den Dienst hinzufügen.  
  
##  <a name="registerappid"></a>CAtlServiceModuleT::RegisterAppId  
 Registriert den Dienst in der Registrierung.  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *bService*  
 Muss "true", die als Dienst registrieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="run"></a>CServiceModule:: Run  
 Der Dienst ausgeführt.  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte im erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt. Der Standardwert ist SW_HIDE.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem aufgerufenen, **ausführen** Aufrufe [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), und [CAtlExeModuleT:: PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).  
  
##  <a name="servicemain"></a>CAtlServiceModuleT::ServiceMain  
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
 Ruft die Dienststeuerungs-Manager (SCM) `ServiceMain` Wenn Sie die Anwendung Dienste in der Systemsteuerung öffnen, wählen Sie den Dienst, und klicken Sie auf Start.  
  
 Ruft nach dem SCM `ServiceMain`, ein Dienst muss dem SCM eine Handlerfunktion erteilen. Diese Funktion ermöglicht den SCM, der Status des Dienstes zu erhalten und übergeben Sie spezifische Anweisungen (z. B. durch das Anhalten oder Beenden). Anschließend [CServiceModule:: Run](#run) aufgerufen, um die Hauptarbeit des Dienstes vorzunehmen. **Führen Sie** wird weiterhin ausgeführt, bis der Dienst beendet wird.  
  
##  <a name="setservicestatus"></a>CAtlServiceModuleT::SetServiceStatus  
 Diese Methode wird den Status aktualisiert.  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwState`  
 Der neue Status. Finden Sie unter [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241) mögliche Werte.  
  
### <a name="remarks"></a>Hinweise  
 Aktualisiert den Service Control Manager Statusinformationen für den Dienst an. Wird aufgerufen, indem [CServiceModule:: Run](#run), [CAtlServiceModuleT::ServiceMain](#servicemain) und andere Handlermethoden. Der Status wird auch gespeichert, in die Membervariable [CAtlServiceModuleT::m_status](#m_status).  
  
##  <a name="start"></a>CServiceModule:: Start  
 Wird aufgerufen, indem `CAtlServiceModuleT::WinMain` beim Starten des Diensts.  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte im erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die [CAtlServiceModuleT::WinMain](#winmain) Methode behandelt, Registrierung und Installation als auch Aufgaben Registrierungseinträge werden entfernt, und deinstallieren das Modul beteiligt. Wenn der Dienst ausgeführt wird, `WinMain` Aufrufe **starten**.  
  
##  <a name="uninstall"></a>CAtlServiceModuleT::Uninstall  
 Beendet und entfernt den Dienst.  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Beendet den Dienst ausgeführt wird, und entfernt sie aus der Dienstkontroll-Manager-Datenbank.  
  
##  <a name="unlock"></a>CAtlServiceModuleT::Unlock  
 Verringert die Sperrenanzahl des Diensts.  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sperren, die möglicherweise hilfreich für die Diagnose und Debuggen.  
  
##  <a name="unregisterappid"></a>CAtlServiceModuleT::UnregisterAppId  
 Entfernt den Dienst aus der Registrierung.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
##  <a name="winmain"></a>CAtlServiceModuleT::WinMain  
 Diese Methode implementiert den Code zum Starten des Diensts erforderlich.  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nShowCmd`  
 Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann einen der Werte im erläutert die [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559) Abschnitt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Dienst-Rückgabewert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verarbeitet von der Befehlszeile aus (mit [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) und startet dann den Dienst (mit [CServiceModule:: Start](#start)).  
  
## <a name="see-also"></a>Siehe auch  
 [CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
