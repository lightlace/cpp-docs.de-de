---
title: CAtlServiceModuleT-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
ms.openlocfilehash: ad682980fbc885d79598b41a5dcc094bb65db8cf
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893534"
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT-Klasse

Diese Klasse implementiert, einen Dienst.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse abgeleitet `CAtlServiceModuleT`.

*nServiceNameID*<br/>
Der Ressourcenbezeichner des Diensts.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlServiceModuleT::Handler](#handler)|Der Handlerroutine für den Dienst.|
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|Stellt die Sicherheitseinstellungen für den Dienst.|
|[CAtlServiceModuleT::Install](#install)|Installiert und den Dienst erstellt.|
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|Bestätigt, dass der Dienst installiert wurde.|
|[CAtlServiceModuleT::LogEvent](#logevent)|Schreibt in das Ereignisprotokoll geschrieben.|
|[CAtlServiceModuleT::OnContinue](#oncontinue)|Überschreiben Sie diese Methode, um den Dienst fortzusetzen.|
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|Überschreiben Sie diese Methode, um den Dienst abzufragen.|
|[CAtlServiceModuleT::OnPause](#onpause)|Überschreiben Sie diese Methode, um den Dienst anzuhalten.|
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|Überschreiben Sie diese Methode, um den Dienst beenden|
|[CAtlServiceModuleT::OnStop](#onstop)|Überschreiben Sie diese Methode, um den Dienst beenden|
|[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)|Überschreiben Sie diese Methode zum Behandeln der Unbekannter Anforderungen an den Dienst|
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.|
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.|
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|Registriert den Dienst in der Registrierung.|
|[CAtlServiceModuleT::Run](#run)|Der Dienst ausgeführt.|
|[CAtlServiceModuleT::ServiceMain](#servicemain)|Die Methode wird aufgerufen, durch den Dienststeuerungs-Manager.|
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|Aktualisiert den Dienststatus.|
|[CAtlServiceModuleT::Start](#start)|Wird aufgerufen, indem `CAtlServiceModuleT::WinMain` Wenn der Dienst gestartet wird.|
|[CAtlServiceModuleT::Uninstall](#uninstall)|Beendet und entfernt den Dienst.|
|[CAtlServiceModuleT::Unlock](#unlock)|Verringert die Sperrenanzahl des Diensts.|
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|Entfernt den Dienst aus der Registrierung.|
|[CAtlServiceModuleT::WinMain](#winmain)|Diese Methode implementiert den erforderlichen Code für den Dienst ausführen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAtlServiceModuleT::m_bService](#m_bservice)|Flag zum angeben, ob das Programm als Dienst ausgeführt wird.|
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|Membervariable, die Speichern des Threadbezeichners.|
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|Membervariable, die ein Handle für das die Struktur der Status für den aktuellen Dienst speichern.|
|[CAtlServiceModuleT::m_status](#m_status)|Membervariable, die die Struktur der Status für den aktuellen Dienst speichern.|
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|Der Name des Diensts registriert wird.|

## <a name="remarks"></a>Hinweise

`CAtlServiceModuleT`, abgeleitet [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), implementiert eine ATL-Service-Moduls. `CAtlServiceModuleT` Stellt Methoden zum befehlszeilenverarbeitung, Installation, Registrierung und entfernen. Wenn zusätzliche Funktionalität erforderlich ist, können diese und andere Methoden überschrieben werden.

Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) verwendet, die in früheren Versionen von ATL Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="catlservicemodulet"></a>  CAtlServiceModuleT::CAtlServiceModuleT

Der Konstruktor.

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert die Datenmember und legt den Status des ersten Dienstes.

##  <a name="handler"></a>  CAtlServiceModuleT:: Handler

Der Handlerroutine für den Dienst.

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>Parameter

*dwOpcode*<br/>
Ein Schalter, der den handlervorgang definiert. Weitere Informationen finden Sie unter den Hinweisen.

### <a name="remarks"></a>Hinweise

Dies ist der Code, den Service Control Manager (SCM) aufruft, zum Abrufen des Status der Dienst und zum Übermitteln Anweisungen wie z. B. beenden oder anhalten. Dienststeuerungs-Manager übergibt ein Vorgangscode, wie unten beschrieben, zu `Handler` , um anzugeben, welche Aktion der Dienst ausführen soll.

|Vorgangscode|Bedeutung|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|Beendet den Dienst. Überschreiben Sie die Methode [CAtlServiceModuleT::OnStop](#onstop) in atlbase.h, um das Verhalten zu ändern.|
|SERVICE_CONTROL_PAUSE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnPause](#onpause) in atlbase.h, den Dienst anzuhalten.|
|SERVICE_CONTROL_CONTINUE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnContinue](#oncontinue) in atlbase.h, den Dienst fortzuführen.|
|SERVICE_CONTROL_INTERROGATE|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnInterrogate](#oninterrogate) in atlbase.h, den Dienst abzufragen.|
|SERVICE_CONTROL_SHUTDOWN|Benutzer, die implementiert werden. Überschreiben Sie die leere Methode [CAtlServiceModuleT::OnShutdown](#onshutdown) in atlbase.h zum Herunterfahren des Diensts.|

Wenn Sie den Vorgangscode nicht erkannt wird, die Methode [CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest) aufgerufen wird.

Ein Standarddienst in ATL generierte verarbeitet nur die Stop-Anweisung. Wenn der dienststeuerungs-Manager die Stop-Anweisung erfolgreich ist, weist den Dienst dienststeuerungs-Manager, dass das Programm wird beendet. Der Dienst ruft dann `PostThreadMessage` Beenden-Meldung an sich selbst zu veröffentlichen. Dies beendet die Nachrichtenschleife aus, und der Dienst wird letztendlich geschlossen.

##  <a name="initializesecurity"></a>  CAtlServiceModuleT:: InitializeSecurity

Stellt die Sicherheitseinstellungen für den Dienst.

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

In Visual Studio .NET 2003 wird diese Methode nicht in der Basisklasse implementiert. Der Visual Studio-Projekt-Assistent enthält diese Methode im generierten Code tritt ein Kompilierungsfehler auf, wenn ein Projekt erstellt wurde, in einer früheren Version von Visual C++ ATL 7.1 mit kompiliert wird. Jede abgeleitete Klasse `CAtlServiceModuleT` müssen diese Methode in der abgeleiteten Klasse implementieren.

Verwenden Sie im Aufruf von PKT-Ebene von Authentifizierung, Identitätswechselebene RPC_C_IMP_LEVEL_IDENTIFY und eine entsprechende ungleich Null-Sicherheitsdeskriptor `CoInitializeSecurity`.

Für die vom Assistenten generierte nicht attributierte Service-Projekte wäre in

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

Für die attributierte Service-Projekte wäre in

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

##  <a name="install"></a>  CAtlServiceModuleT::Install

Installiert und den Dienst erstellt.

```
BOOL Install() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Installiert den Dienst in der Datenbank des Dienststeuerungs-Manager (SCM) aus, und erstellt dann das Dienstobjekt. Wenn der Dienst nicht erstellt werden konnte, wird ein Meldungsfeld wird angezeigt, und gibt die Methode "false" zurück.

##  <a name="isinstalled"></a>  CAtlServiceModuleT::IsInstalled

Bestätigt, dass der Dienst installiert wurde.

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Dienst installiert, andernfalls FALSE ist.

##  <a name="logevent"></a>  CAtlServiceModuleT::LogEvent

Schreibt in das Ereignisprotokoll geschrieben.

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>Parameter

*pszFormat*<br/>
Die in das Ereignisprotokoll zu schreibende Zeichenfolge.

*...*<br/>
Optionale zusätzliche Zeichenfolgen, in das Ereignisprotokoll geschrieben werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode schreibt Informationen in ein Ereignisprotokoll, die mit der Funktion [ReportEvent](/windows/desktop/api/winbase/nf-winbase-reporteventa). Wenn kein Dienst ausgeführt wird, wird die Zeichenfolge an die Konsole gesendet.

##  <a name="m_bservice"></a>  CAtlServiceModuleT::m_bService

Flag zum angeben, ob das Programm als Dienst ausgeführt wird.

```
BOOL m_bService;
```

### <a name="remarks"></a>Hinweise

Wird verwendet, um eine Dienst-exe-Datei von einer EXE-Anwendung zu unterscheiden.

##  <a name="m_dwthreadid"></a>  CAtlServiceModuleT::m_dwThreadID

Membervariable, die den Threadbezeichner des Diensts zu speichern.

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>Hinweise

Diese Variable speichert den Threadbezeichner des aktuellen Threads.

##  <a name="m_hservicestatus"></a>  CAtlServiceModuleT::m_hServiceStatus

Membervariable, die ein Handle für das die Struktur der Status für den aktuellen Dienst speichern.

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>Hinweise

Die [SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) Struktur enthält Informationen zu einem Dienst.

##  <a name="m_status"></a>  CAtlServiceModuleT::m_status

Membervariable, die die Struktur der Status für den aktuellen Dienst speichern.

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>Hinweise

Die [SERVICE_STATUS](/windows/desktop/api/winsvc/ns-winsvc-_service_status) Struktur enthält Informationen zu einem Dienst.

##  <a name="m_szservicename"></a>  CAtlServiceModuleT::m_szServiceName

Der Name des Diensts registriert wird.

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>Hinweise

Eine Null-terminierte Zeichenfolge, die den Namen des Diensts gespeichert.

##  <a name="oncontinue"></a>  CAtlServiceModuleT::OnContinue

Überschreiben Sie diese Methode, um den Dienst fortzusetzen.

```
void OnContinue() throw();
```

##  <a name="oninterrogate"></a>  CAtlServiceModuleT::OnInterrogate

Überschreiben Sie diese Methode, um den Dienst abzufragen.

```
void OnInterrogate() throw();
```

##  <a name="onpause"></a>  CAtlServiceModuleT::OnPause

Überschreiben Sie diese Methode, um den Dienst anzuhalten.

```
void OnPause() throw();
```

##  <a name="onshutdown"></a>  CAtlServiceModuleT::OnShutdown

Überschreiben Sie diese Methode, um den Dienst beenden.

```
void OnShutdown() throw();
```

##  <a name="onstop"></a>  CAtlServiceModuleT::OnStop

Überschreiben Sie diese Methode, um den Dienst zu beenden.

```
void OnStop() throw();
```

##  <a name="onunknownrequest"></a>  CAtlServiceModuleT::OnUnknownRequest

Überschreiben Sie diese Methode zum Behandeln der Unbekannter Anforderungen an den Dienst.

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>Parameter

*dwOpcode*<br/>
Reserviert.

##  <a name="parsecommandline"></a>  CAtlServiceModuleT::ParseCommandLine

Analysiert die Befehlszeile und führt die Registrierung bei Bedarf.

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>Parameter

*lpCmdLine*<br/>
Die Befehlszeile.

*pnRetCode*<br/>
Das HRESULT der Registrierung (wenn es stattgefunden hat).

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg oder "false", wenn die RGS-Datei, die in der Befehlszeile angegebenen konnte nicht registriert werden.

### <a name="remarks"></a>Hinweise

Analysiert die Befehlszeile und registriert, oder hebt die Registrierung für der angegebenen RGS-Datei bei Bedarf. Diese Methode ruft [CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline) zu suchende **/RegServer** und **/Unregserver**. Das Argument hinzufügen **- / Service** wird den Dienst registriert.

##  <a name="premessageloop"></a>  CAtlServiceModuleT::PreMessageLoop

Diese Methode wird aufgerufen, unmittelbar vor die Nachrichtenschleife eingeben.

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*<br/>
Dieser Parameter wird übergeben, um [CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop).

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die benutzerdefinierten Initialisierungscode für den Dienst hinzuzufügen.

##  <a name="registerappid"></a>  CAtlServiceModuleT::RegisterAppId

Registriert den Dienst in der Registrierung.

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>Parameter

*bService*<br/>
Muss "true", die als Dienst zu registrieren.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="run"></a>  CAtlServiceModuleT:: Start

Der Dienst ausgeführt.

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*<br/>
Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann sein, einen der Werte in erläutert die [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) Abschnitt. Der Standardwert ist SW_HIDE.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Nach dem aufrufen, `Run` Aufrufe [CAtlServiceModuleT::PreMessageLoop](#premessageloop), [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop), und [CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop).

##  <a name="servicemain"></a>  CAtlServiceModuleT:: ServiceMain

Diese Methode wird durch den Dienststeuerungs-Manager aufgerufen.

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>Parameter

*dwArgc*<br/>
Das Argc-Argument.

*lpszArgv*<br/>
Das Argv-Argument.

### <a name="remarks"></a>Hinweise

Der Dienststeuerungs-Manager (SCM) Ruft `ServiceMain` Wenn Sie die Anwendung Dienste in der Systemsteuerung öffnen, wählen Sie den Dienst, und klicken Sie auf Start.

Nach dem dienststeuerungs-Manager ruft `ServiceMain`, ein Dienst muss dienststeuerungs-Manager eine Handlerfunktion erteilen. Mithilfe dieser Funktion können den SCM-Status des Diensts zu erhalten und übergeben Sie spezifische Anweisungen (z. B. durch das Anhalten oder Beenden). Anschließend [CAtlServiceModuleT:: Start](#run) wird aufgerufen, um die eigentliche Arbeit des Diensts führen. `Run` wird weiterhin ausgeführt, bis der Dienst beendet wird.

##  <a name="setservicestatus"></a>  CAtlServiceModuleT::SetServiceStatus

Diese Methode wird den Status aktualisiert.

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>Parameter

*dwState*<br/>
Der neue Status. Finden Sie unter [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) mögliche Werte.

### <a name="remarks"></a>Hinweise

Aktualisiert den Dienststeuerungs-Manager die Statusinformationen für den Dienst an. Durch Aufruf von [CAtlServiceModuleT:: Start](#run), [CAtlServiceModuleT:: ServiceMain](#servicemain) und andere Handlermethoden. Der Status wird auch gespeichert, in der Membervariablen [CAtlServiceModuleT::m_status](#m_status).

##  <a name="start"></a>  CAtlServiceModuleT:: Start

Wird aufgerufen, indem `CAtlServiceModuleT::WinMain` Wenn der Dienst gestartet wird.

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*<br/>
Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann sein, einen der Werte in erläutert die [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) Abschnitt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Die [CAtlServiceModuleT::WinMain](#winmain) Methode behandelt sowohl die Registrierung als auch die Installation als auch Aufgaben Registrierungseinträge werden entfernt, und deinstallieren das Modul beteiligt. Wenn der Dienst ausgeführt wird, `WinMain` Aufrufe `Start`.

##  <a name="uninstall"></a>  CAtlServiceModuleT::Uninstall

Beendet und entfernt den Dienst.

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Beendet den Dienst ausgeführt wird, und entfernt sie aus der Dienststeuerungs-Manager-Datenbank.

##  <a name="unlock"></a>  CAtlServiceModuleT::Unlock

Verringert die Sperrenanzahl des Diensts.

```
LONG Unlock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Sperren, die möglicherweise hilfreich für die Diagnose und Debuggen.

##  <a name="unregisterappid"></a>  CAtlServiceModuleT::UnregisterAppId

Entfernt den Dienst aus der Registrierung.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="winmain"></a>  CAtlServiceModuleT::WinMain

Diese Methode implementiert den erforderlichen Code für den Dienst zu starten.

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>Parameter

*nShowCmd*<br/>
Gibt an, wie das Fenster angezeigt werden. Dieser Parameter kann sein, einen der Werte in erläutert die [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain) Abschnitt.

### <a name="return-value"></a>Rückgabewert

Gibt den Dienst-Rückgabewert zurück.

### <a name="remarks"></a>Hinweise

Diese Methode verarbeitet von der Befehlszeile aus (mit [CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) und startet dann den Dienst (mit [CAtlServiceModuleT:: Start](#start)).

## <a name="see-also"></a>Siehe auch

[CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
