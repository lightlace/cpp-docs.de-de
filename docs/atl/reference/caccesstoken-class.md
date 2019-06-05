---
title: CAccessToken-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAccessToken
- ATLSECURITY/ATL::CAccessToken
- ATLSECURITY/ATL::CAccessToken::Attach
- ATLSECURITY/ATL::CAccessToken::CheckTokenMembership
- ATLSECURITY/ATL::CAccessToken::CreateImpersonationToken
- ATLSECURITY/ATL::CAccessToken::CreatePrimaryToken
- ATLSECURITY/ATL::CAccessToken::CreateProcessAsUser
- ATLSECURITY/ATL::CAccessToken::CreateRestrictedToken
- ATLSECURITY/ATL::CAccessToken::Detach
- ATLSECURITY/ATL::CAccessToken::DisablePrivilege
- ATLSECURITY/ATL::CAccessToken::DisablePrivileges
- ATLSECURITY/ATL::CAccessToken::EnablePrivilege
- ATLSECURITY/ATL::CAccessToken::EnablePrivileges
- ATLSECURITY/ATL::CAccessToken::GetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::GetEffectiveToken
- ATLSECURITY/ATL::CAccessToken::GetGroups
- ATLSECURITY/ATL::CAccessToken::GetHandle
- ATLSECURITY/ATL::CAccessToken::GetImpersonationLevel
- ATLSECURITY/ATL::CAccessToken::GetLogonSessionId
- ATLSECURITY/ATL::CAccessToken::GetLogonSid
- ATLSECURITY/ATL::CAccessToken::GetOwner
- ATLSECURITY/ATL::CAccessToken::GetPrimaryGroup
- ATLSECURITY/ATL::CAccessToken::GetPrivileges
- ATLSECURITY/ATL::CAccessToken::GetProcessToken
- ATLSECURITY/ATL::CAccessToken::GetProfile
- ATLSECURITY/ATL::CAccessToken::GetSource
- ATLSECURITY/ATL::CAccessToken::GetStatistics
- ATLSECURITY/ATL::CAccessToken::GetTerminalServicesSessionId
- ATLSECURITY/ATL::CAccessToken::GetThreadToken
- ATLSECURITY/ATL::CAccessToken::GetTokenId
- ATLSECURITY/ATL::CAccessToken::GetType
- ATLSECURITY/ATL::CAccessToken::GetUser
- ATLSECURITY/ATL::CAccessToken::HKeyCurrentUser
- ATLSECURITY/ATL::CAccessToken::Impersonate
- ATLSECURITY/ATL::CAccessToken::ImpersonateLoggedOnUser
- ATLSECURITY/ATL::CAccessToken::IsTokenRestricted
- ATLSECURITY/ATL::CAccessToken::LoadUserProfile
- ATLSECURITY/ATL::CAccessToken::LogonUser
- ATLSECURITY/ATL::CAccessToken::OpenCOMClientToken
- ATLSECURITY/ATL::CAccessToken::OpenNamedPipeClientToken
- ATLSECURITY/ATL::CAccessToken::OpenRPCClientToken
- ATLSECURITY/ATL::CAccessToken::OpenThreadToken
- ATLSECURITY/ATL::CAccessToken::PrivilegeCheck
- ATLSECURITY/ATL::CAccessToken::Revert
- ATLSECURITY/ATL::CAccessToken::SetDefaultDacl
- ATLSECURITY/ATL::CAccessToken::SetOwner
- ATLSECURITY/ATL::CAccessToken::SetPrimaryGroup
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
ms.openlocfilehash: ce5c29c2399fd47bdb1ad0135257b41617094aa9
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503385"
---
# <a name="caccesstoken-class"></a>CAccessToken-Klasse

Diese Klasse ist ein Wrapper für ein Zugriffstoken an.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CAccessToken
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAccessToken::~CAccessToken](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAccessToken::Attach](#attach)|Rufen Sie diese Methode, um das Tokenhandle Zugriff den Besitz übernehmen.|
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene SID, in aktiviert ist der `CAccessToken` Objekt.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Rufen Sie diese Methode, um ein neues Zugriffstoken für den Identitätswechsel zu erstellen.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Rufen Sie diese Methode zum Erstellen eines neuen primären Tokens.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Rufen Sie diese Methode zum Erstellen eines neuen Prozesses, der im Sicherheitskontext des Benutzers dargestellt werden, indem Sie Ausführung der `CAccessToken` Objekt.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Rufen Sie diese Methode zum Erstellen einer neuen, eingeschränkten `CAccessToken` Objekt.|
|[CAccessToken::Detach](#detach)|Rufen Sie diese Methode, um den Besitz des Zugriffstokens zu widerrufen.|
|[CAccessToken::DisablePrivilege](#disableprivilege)|Rufen Sie diese Methode zum Deaktivieren einer Berechtigung in den `CAccessToken` Objekt.|
|[CAccessToken::DisablePrivileges](#disableprivileges)|Rufen Sie diese Methode zum Deaktivieren von ein oder mehrere Berechtigungen in der `CAccessToken` Objekt.|
|[CAccessToken::EnablePrivilege](#enableprivilege)|Rufen Sie diese Methode zum Aktivieren einer Berechtigung in den `CAccessToken` Objekt.|
|[CAccessToken::EnablePrivileges](#enableprivileges)|Rufen Sie diese Methode zum Aktivieren von ein oder mehrere Berechtigungen in der `CAccessToken` Objekt.|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` des Objekts default DACL.|
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Rufen Sie diese Methode zum Abrufen der `CAccessToken` Objekt gleich dem Zugriffstoken für den aktuellen Thread.|
|[CAccessToken::GetGroups](#getgroups)|Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` token Gruppen des Objekts.|
|[CAccessToken::GetHandle](#gethandle)|Rufen Sie diese Methode, um ein Handle für das Zugriffstoken abzurufen.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Rufen Sie diese Methode, um die Ebene des Identitätswechsels aus dem Zugriffstoken zu erhalten.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Rufen Sie diese Methode rufen Sie die zugeordnete Anmeldung Sitzungs-ID der `CAccessToken` Objekt.|
|[CAccessToken::GetLogonSid](#getlogonsid)|Rufen Sie diese Methode zum Abrufen der SID der Anmeldung zugeordnete der `CAccessToken` Objekt.|
|[CAccessToken::GetOwner](#getowner)|Rufen Sie diese Methode zum Abrufen der Benutzer mit der `CAccessToken` Objekt.|
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Rufen Sie diese Methode, um die zugeordnete primäre Gruppe erhalten die `CAccessToken` Objekt.|
|[CAccessToken::GetPrivileges](#getprivileges)|Rufen Sie diese Methode rufen Sie die Berechtigungen des entsprechenden die `CAccessToken` Objekt.|
|[CAccessToken::GetProcessToken](#getprocesstoken)|Rufen Sie diese Methode auf, um `CAccessToken` mit dem Zugriffstoken aus einem Prozess zu initialisieren.|
|[CAccessToken::GetProfile](#getprofile)|Rufen Sie diese Methode, um das Handle verweist auf das zugeordnete Benutzerprofil Abrufen der `CAccessToken` Objekt.|
|[CAccessToken::GetSource](#getsource)|Rufen Sie diese Methode rufen Sie die Quelle des der `CAccessToken` Objekt.|
|[CAccessToken::GetStatistics](#getstatistics)|Rufen Sie diese Methode zum Abrufen von Informationen im Zusammenhang mit der `CAccessToken` Objekt.|
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Rufen Sie diese Methode rufen Sie die Terminal Services Sitzungs-ID zugeordneten der `CAccessToken` Objekt.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|Rufen Sie diese Methode zum Initialisieren der `CAccessToken` mit dem Token aus dem angegebenen Thread.|
|[CAccessToken::GetTokenId](#gettokenid)|Rufen Sie diese Methode zum Abrufen der Token-ID zugeordneten der `CAccessToken` Objekt.|
|[CAccessToken::GetType](#gettype)|Rufen Sie diese Methode, um den Tokentyp des erhalten die `CAccessToken` Objekt.|
|[CAccessToken::GetUser](#getuser)|Rufen Sie diese Methode, um den zugeordneten Benutzer identifizieren die `CAccessToken` Objekt.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Rufen Sie diese Methode, um das Handle verweist auf das zugeordnete Benutzerprofil Abrufen der `CAccessToken` Objekt.|
|[CAccessToken::Impersonate](#impersonate)|Rufen Sie diese Methode, um die Zuweisung von eines Identitätswechsels `CAccessToken` an einen Thread.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Rufen Sie diese Methode aus, damit den aufrufenden Thread den Sicherheitskontext eines angemeldeten Benutzers annehmen kann.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Rufen Sie diese Methode getestet, ob die `CAccessToken` Objekt enthält eine Liste der eingeschränkten SIDs.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Rufen Sie diese Methode zum Laden des Benutzerprofils zugeordneten der `CAccessToken` Objekt.|
|[CAccessToken::LogonUser](#logonuser)|Rufen Sie diese Methode zum Erstellen einer Sitzungs für den Benutzer, die den angegebenen Anmeldeinformationen zugeordnet.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Rufen Sie diese Methode aus, in einen COM-Server, die Behandlung von eines Aufrufs von einem Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus der COM-Client.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Rufen Sie diese Methode von innerhalb eines Servers übernehmen Anforderungen über eine named Pipe zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Rufen Sie diese Methode aus, auf einem Server, die Behandlung von eines Aufrufs aus einem RPC-Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Rufen Sie diese Methode, um die Ebene des Identitätswechsels festgelegt, und initialisieren Sie die `CAccessToken` mit dem Token aus dem angegebenen Thread.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene Gruppe von Berechtigungen aktiviert sind, der `CAccessToken` Objekt.|
|[CAccessToken::Revert](#revert)|Rufen Sie diese Methode, um einen Thread zu beenden, der ein Identitätstoken verwendet wird.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Rufen Sie diese Methode zum Festlegen der standardmäßigen DACL den `CAccessToken` Objekt.|
|[CAccessToken::SetOwner](#setowner)|Rufen Sie diese Methode zum Festlegen des Besitzers der `CAccessToken` Objekt.|
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Rufen Sie diese Methode, um die primäre Gruppe des Festlegen der `CAccessToken` Objekt.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffstoken](/windows/desktop/SecAuthZ/access-tokens) ist ein Objekt, das beschreibt den Sicherheitskontext eines Prozesses oder Threads. zudem ist jeder Benutzer, die auf einem Windows-System protokolliert zugeordnet ist.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="attach"></a>  CAccessToken::Attach

Rufen Sie diese Methode, um das Tokenhandle Zugriff den Besitz übernehmen.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Parameter

*hToken*<br/>
Ein Handle für das Zugriffstoken.

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler auftreten, wenn die `CAccessToken` Objekt eines Zugriffstokens bereits besitzt.

##  <a name="dtor"></a>  CAccessToken:: ~ CAccessToken

Der Destruktor.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="checktokenmembership"></a>  CAccessToken::CheckTokenMembership

Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene SID, in aktiviert ist der `CAccessToken` Objekt.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Ein Verweis auf eine [CSid-Klasse](../../atl/reference/csid-class.md) Objekt.

*pbIsMember*<br/>
Zeiger auf eine Variable, die Ergebnisse der Überprüfung empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die `CheckTokenMembership` Methode prüft, ob der SID in der Benutzer und Gruppen-SIDs des Zugriffstokens. Wenn die SID vorhanden ist und das Attribut SE_GROUP_ENABLED *PbIsMember* ist festgelegt auf "true", andernfalls, wird er auf "false" festgelegt.

In Debugbuilds wird ein Assertionsfehler auftreten, wenn *PbIsMember* ist kein gültiger Zeiger.

> [!NOTE]
>  Die `CAccessToken` Objekt muss ein Identitätswechseltoken und nicht über ein primäres Token sein.

##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken

Rufen Sie diese Methode, um ein Zugriffstoken für den Identitätswechsel zu erstellen.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Parameter

*pImp*<br/>
Zeiger auf den neuen `CAccessToken` Objekt.

*sil*<br/>
Gibt an, eine [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) Enumerationstyps, der die Ebene des Identitätswechsels von das neue Token bereitstellt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

`CreateImpersonationToken` Aufrufe [nicht dupliziert werden](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) um ein neues Identitätswechseltoken zu erstellen.

##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken

Rufen Sie diese Methode zum Erstellen eines neuen primären Tokens.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pPri*<br/>
Zeiger auf den neuen `CAccessToken` Objekt.

*dwDesiredAccess*<br/>
Gibt die angeforderte Zugriffsrechte für das neue Token an. Der Standardwert, MAXIMUM_ALLOWED, fordert alle Zugriffsrechte, die für den Aufrufer gültig sind. Finden Sie unter [Zugriffsrechte und Zugriffsmasken](/windows/desktop/SecAuthZ/access-rights-and-access-masks) für weitere auf Zugriffsrechte.

*pTokenAttributes*<br/>
Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) Struktur, die eine Sicherheitsbeschreibung für das neue Token gibt an, und bestimmt, ob untergeordnete Prozesse, das Token erben können. Wenn *pTokenAttributes* NULL ist, das Token Ruft eine standardmäßige Sicherheitsbeschreibung aus, und das Handle nicht geerbt werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

`CreatePrimaryToken` Aufrufe [DuplicateTokenEx](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) zum Erstellen eines neuen primären Tokens.

##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser

Rufen Sie diese Methode zum Erstellen eines neuen Prozesses, der im Sicherheitskontext des Benutzers dargestellt werden, indem Sie Ausführung der `CAccessToken` Objekt.

```
bool CreateProcessAsUser(
    LPCTSTR pApplicationName,
    LPTSTR pCommandLine,
    LPPROCESS_INFORMATION pProcessInformation,
    LPSTARTUPINFO pStartupInfo,
    DWORD dwCreationFlags = NORMAL_PRIORITY_CLASS,
    bool bLoadProfile = false,
    const CSecurityAttributes* pProcessAttributes = NULL,
    const CSecurityAttributes* pThreadAttributes = NULL,
    bool bInherit = false,
    LPCTSTR pCurrentDirectory = NULL) throw();
```

### <a name="parameters"></a>Parameter

*pApplicationName*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul ausgeführt. Dieser Parameter kann nicht NULL sein.

*pCommandLine*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die auszuführende Befehlszeile.

*pProcessInformation*<br/>
Zeiger auf eine [PROCESS_INFORMATION](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_process_information) Struktur, die ID-Informationen zu den neuen Prozess empfängt.

*pStartupInfo*<br/>
Zeiger auf eine [STARTUPINFO](/windows/desktop/api/processthreadsapi/ns-processthreadsapi-_startupinfoa) Struktur, die angibt, wie das Hauptfenster für den neuen Prozess angezeigt werden soll.

*dwCreationFlags*<br/>
Gibt zusätzliche Flags, die die Prioritätsklasse und die Erstellung des Prozesses steuern. Finden Sie im Win32-Funktion [CreateProcessAsUser](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessasusera) für eine Liste von Flags.

*bLoadProfile*<br/>
Wenn TRUE, wird das Profil des Benutzers mit geladen [LoadUserProfile](/windows/desktop/api/userenv/nf-userenv-loaduserprofilea).

*pProcessAttributes*<br/>
Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) Struktur, die eine Sicherheitsbeschreibung für den neuen Prozess gibt an, und bestimmt, ob untergeordnete Prozesse, das zurückgegebene Handle erben können. Wenn *pProcessAttributes* NULL ist, der Prozess Ruft eine standardmäßige Sicherheitsbeschreibung aus, und das Handle nicht geerbt werden.

*pThreadAttributes*<br/>
Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) Struktur, die eine Sicherheitsbeschreibung für den neuen Thread gibt an, und bestimmt, ob untergeordnete Prozesse, das zurückgegebene Handle erben können. Wenn *pThreadAttributes* NULL ist, der Thread Ruft eine standardmäßige Sicherheitsbeschreibung aus, und das Handle nicht geerbt werden.

*bInherit*<br/>
Gibt an, ob der neue Prozess den aufrufenden Prozess Handles erbt. Bei "true", wird jede vererbbar geöffnetes Handle des aufrufenden Prozesses durch den neuen Prozess geerbt. Geerbte Handles haben die gleichen Wert und Access-Berechtigungen wie die ursprünglichen Handles.

*pCurrentDirectory*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die das aktuelle Laufwerk und Verzeichnis für den neuen Prozess angibt. Die Zeichenfolge muss es sich um einen vollständigen Pfad sein, der einen bestimmten Laufwerkbuchstaben enthält. Wenn dieser Parameter NULL ist, wird der neue Prozess das gleiche aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess haben.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

`CreateProcessAsUser` verwendet die `CreateProcessAsUser` Win32-Funktion, um einen neuen Prozess zu erstellen, der im Sicherheitskontext des Benutzers durch dargestellt ausgeführt wird. die `CAccessToken` Objekt. Siehe dazu die Beschreibung der [CreateProcessAsUser](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessasusera) -Funktion für eine umfassende Erläuterung der erforderlichen Parameter.

Für diese Methode erfolgreich ausgeführt werden kann die `CAccessToken` Objekt obligatorisch AssignPrimaryToken (sei es ein eingeschränktes Token) und IncreaseQuota Berechtigungen.

##  <a name="createrestrictedtoken"></a>  CAccessToken::CreateRestrictedToken

Rufen Sie diese Methode zum Erstellen einer neuen, eingeschränkten `CAccessToken` Objekt.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Parameter

*pRestrictedToken*<br/>
Die neuen eingeschränkten `CAccessToken` Objekt.

*SidsToDisable*<br/>
Ein `CTokenGroups` Objekt, das die SIDs nur zum Ablehnen angibt.

*SidsToRestrict*<br/>
Ein `CTokenGroups` Objekt, das den eingeschränkten SIDs angibt.

*PrivilegesToDelete*<br/>
Ein `CTokenPrivileges` -Objekt, das den zu löschenden Privilegien in der eingeschränkten Token angibt. Standardmäßig wird ein leeres Objekt erstellt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

`CreateRestrictedToken` verwendet die [CreateRestrictedToken](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) Win32-Funktion zum Erstellen eines neuen `CAccessToken` -Objekt, mit Einschränkungen.

> [!IMPORTANT]
>  Bei Verwendung `CreateRestrictedToken`, stellen Sie Folgendes sicher: das vorhandene Token gültig ist (und nicht vom Benutzer eingegebenen) und *SidsToDisable* und *PrivilegesToDelete* sind ungültig (und nicht vom Benutzer eingegebenen). Wenn die Methode "false" zurückgibt, verweigern Sie Funktionalität.

##  <a name="detach"></a>  CAccessToken::Detach

Rufen Sie diese Methode, um den Besitz des Zugriffstokens zu widerrufen.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Handle für die `CAccessToken` wurde die getrennt wurden.

### <a name="remarks"></a>Hinweise

Diese Methode sperrt die `CAccessToken`den Besitz des Zugriffstokens.

##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege

Rufen Sie diese Methode zum Deaktivieren einer Berechtigung in den `CAccessToken` Objekt.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine Zeichenfolge mit der Berechtigung zum Deaktivieren von in die `CAccessToken` Objekt.

*pPreviousState*<br/>
Zeiger auf eine `CTokenPrivileges` Objekt, das in den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges

Rufen Sie diese Methode zum Deaktivieren von ein oder mehrere Berechtigungen in der `CAccessToken` Objekt.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*rPrivileges*<br/>
Zeiger auf ein Array von Zeichenfolgen mit den Berechtigungen zum Deaktivieren von in die `CAccessToken` Objekt.

*pPreviousState*<br/>
Zeiger auf eine `CTokenPrivileges` Objekt, das in den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege

Rufen Sie diese Methode zum Aktivieren einer Berechtigung in den `CAccessToken` Objekt.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine Zeichenfolge mit der Berechtigung zum Aktivieren von in die `CAccessToken` Objekt.

*pPreviousState*<br/>
Zeiger auf eine `CTokenPrivileges` Objekt, das in den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges

Rufen Sie diese Methode zum Aktivieren von ein oder mehrere Berechtigungen in der `CAccessToken` Objekt.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*rPrivileges*<br/>
Zeiger auf ein Array von Zeichenfolgen mit den Berechtigungen zum Aktivieren von in die `CAccessToken` Objekt.

*pPreviousState*<br/>
Zeiger auf eine `CTokenPrivileges` Objekt, das in den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl

Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` des Objekts default DACL.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Parameter

*pDacl*<br/>
Zeiger auf die [CDacl-Klasse](../../atl/reference/cdacl-class.md) Objekt, das erhält die `CAccessToken` des Objekts default DACL.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Standard-DACL wiederhergestellten "false" andernfalls wurde.

##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken

Rufen Sie diese Methode zum Abrufen der `CAccessToken` Objekt gleich dem Zugriffstoken für den aktuellen Thread.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getgroups"></a>  CAccessToken::GetGroups

Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` token Gruppen des Objekts.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Parameter

*pGroups*<br/>
Zeiger auf die [CTokenGroups-Klasse](../../atl/reference/ctokengroups-class.md) Objekt, das die Informationen erhält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="gethandle"></a>  CAccessToken::GetHandle

Rufen Sie diese Methode, um ein Handle für das Zugriffstoken abzurufen.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für die `CAccessToken` Zugriffstoken des Objekts.

##  <a name="getimpersonationlevel"></a>  CAccessToken::GetImpersonationLevel

Rufen Sie diese Methode, um die Ebene des Identitätswechsels aus dem Zugriffstoken zu erhalten.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Parameter

*pImpersonationLevel*<br/>
Zeiger auf eine [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) Enumerationstyp, der die Ebene Identitätswechselinformationen empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId

Rufen Sie diese Methode rufen Sie die zugeordnete Anmeldung Sitzungs-ID der `CAccessToken` Objekt.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pluid*<br/>
Zeiger auf eine [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) der erhalten, dass die Anmeldung Sitzungs-ID.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler auftreten, wenn *Pluid* ist ein ungültiger Wert.

##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid

Rufen Sie diese Methode zum Abrufen der SID der Anmeldung zugeordnete der `CAccessToken` Objekt.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf eine [CSid-Klasse](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler auftreten, wenn *pSid* ist ein ungültiger Wert.

##  <a name="getowner"></a>  CAccessToken::GetOwner

Rufen Sie diese Methode zum Abrufen der Benutzer mit der `CAccessToken` Objekt.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf eine [CSid-Klasse](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Der Besitzer wird festgelegt, wird standardmäßig auf alle Objekte erstellt, während das Zugriffstoken gültig ist.

##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup

Rufen Sie diese Methode, um die zugeordnete primäre Gruppe erhalten die `CAccessToken` Objekt.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf eine [CSid-Klasse](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die Gruppe festgelegt ist, wird standardmäßig auf alle Objekte erstellt, während das Zugriffstoken gültig ist.

##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges

Rufen Sie diese Methode rufen Sie die Berechtigungen des entsprechenden die `CAccessToken` Objekt.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Parameter

*pPrivileges*<br/>
Zeiger auf eine [CTokenPrivileges-Klasse](../../atl/reference/ctokenprivileges-class.md) Objekt, das die Berechtigungen erhält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken

Rufen Sie diese Methode auf, um `CAccessToken` mit dem Zugriffstoken aus einem Prozess zu initialisieren.

```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*hProcess*<br/>
Handle an den Prozess, dessen Zugriffstoken geöffnet ist. Wenn der Standardwert NULL verwendet wird, wird der aktuelle Prozess verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Ruft die [OpenProcessToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) Win32-Funktion.

##  <a name="getprofile"></a>  CAccessToken::GetProfile

Rufen Sie diese Methode, um das Handle verweist auf das zugeordnete Benutzerprofil Abrufen der `CAccessToken` Objekt.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle auf das Benutzerprofil oder NULL, wenn kein Profil vorhanden ist.

##  <a name="getsource"></a>  CAccessToken::GetSource

Rufen Sie diese Methode rufen Sie die Quelle des der `CAccessToken` Objekt.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSource*<br/>
Zeiger auf eine [TOKEN_SOURCE](/windows/desktop/api/winnt/ns-winnt-_token_source) Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getstatistics"></a>  CAccessToken::GetStatistics

Rufen Sie diese Methode zum Abrufen von Informationen im Zusammenhang mit der `CAccessToken` Objekt.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Parameter

*pStatistics*<br/>
Zeiger auf eine [TOKEN_STATISTICS](/windows/desktop/api/winnt/ns-winnt-_token_statistics) Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId

Rufen Sie diese Methode rufen Sie die Terminal Services Sitzungs-ID zugeordneten der `CAccessToken` Objekt.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Parameter

*pdwSessionId*<br/>
Der Terminaldienste-Sitzungs-ID.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken

Rufen Sie diese Methode zum Initialisieren der `CAccessToken` mit dem Token aus dem angegebenen Thread.

```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*hThread*<br/>
Handle für den Thread, dessen Zugriffstoken geöffnet ist.

*bOpenAsSelf*<br/>
Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Thread erfolgen die `GetThreadToken` Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter auf "false" ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread einen Client einen Identitätswechsel ausführt, kann in folgendem Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter TRUE ist, ist die zugriffsprüfung erfolgt mit den Sicherheitskontext des Prozesses für den aufrufenden Thread.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="gettokenid"></a>  CAccessToken::GetTokenId

Rufen Sie diese Methode zum Abrufen der Token-ID zugeordneten der `CAccessToken` Objekt.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pluid*<br/>
Zeiger auf eine [LUID](/windows/desktop/api/winnt/ns-winnt-_luid) erhalten die, die Token-ID.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="gettype"></a>  CAccessToken::GetType

Rufen Sie diese Methode, um den Tokentyp des erhalten die `CAccessToken` Objekt.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Parameter

*pType*<br/>
Adresse von der [TOKEN_TYPE](/windows/desktop/api/winnt/ne-winnt-_token_type) Variable, die bei Erfolg, den Typ des Tokens erhält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Der Enumerationstyp TOKEN_TYPE enthält Werte, die ein primäres Token und ein Identitätswechseltoken unterscheiden.

##  <a name="getuser"></a>  CAccessToken::GetUser

Rufen Sie diese Methode, um den zugeordneten Benutzer identifizieren die `CAccessToken` Objekt.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf eine [CSid-Klasse](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser

Rufen Sie diese Methode, um das Handle verweist auf das zugeordnete Benutzerprofil Abrufen der `CAccessToken` Objekt.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle auf das Benutzerprofil oder NULL, wenn kein Profil vorhanden ist.

##  <a name="impersonate"></a>  CAccessToken::Impersonate

Rufen Sie diese Methode, um die Zuweisung von eines Identitätswechsels `CAccessToken` an einen Thread.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*hThread*<br/>
Handle für den Thread für das Zuweisen von Token für den Identitätswechsel zu. Dieses Handle muss mit Zugriffsrechten TOKEN_IMPERSONATE geöffnet worden sein. Wenn *hThread* NULL ist, die Methode führt dazu, dass den Thread nicht mehr mit einem Identitätswechseltoken.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler auftreten, wenn `CAccessToken` verfügt nicht über einen gültigen Zeiger auf ein Token.

Die [CAutoRevertImpersonation-Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken automatisch zurückgesetzt.

##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser

Rufen Sie diese Methode aus, damit den aufrufenden Thread den Sicherheitskontext eines angemeldeten Benutzers annehmen kann.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

> [!IMPORTANT]
>  Wenn ein Aufruf an ein Identitätswechsel-Funktion aus irgendeinem Grund fehlschlägt, der Client kein Identitätswechsel und die Client-Anforderung erfolgt im Sicherheitskontext des Prozesses aus dem der Aufruf erfolgt ist. Wenn der Prozess als ein Konto mit weit reichenden Berechtigungen ausgeführt wird, oder als Mitglied einer administrativen Gruppe der Benutzer möglicherweise Aktionen wäre er oder sie andernfalls nicht zulässig. Aus diesem Grund sollte der Rückgabewert für diese Funktion immer bestätigt werden.

##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted

Rufen Sie diese Methode getestet, ob die `CAccessToken` Objekt enthält eine Liste der eingeschränkten SIDs.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das Objekt eine Liste enthält der SIDs, "false" einschränken, wenn keine eingeschränkten SIDs vorhanden sind oder wenn die Methode fehlschlägt.

##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile

Rufen Sie diese Methode zum Laden des Benutzerprofils zugeordneten der `CAccessToken` Objekt.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler auftreten, wenn die `CAccessToken` enthält kein gültiges Token, oder wenn ein Benutzer bereits ein Profil vorhanden ist.

##  <a name="logonuser"></a>  CAccessToken::LogonUser

Rufen Sie diese Methode zum Erstellen einer Sitzungs für den Benutzer, die den angegebenen Anmeldeinformationen zugeordnet.

```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```

### <a name="parameters"></a>Parameter

*pszUserName*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die den Benutzernamen angibt. Dies ist der Name des Benutzerkontos anzumelden.

*pszDomain*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, der angibt, den Namen der Domäne oder des Servers, dessen Datenbank enthält, die *PszUserName* Konto.

*pszPassword*<br/>
Zeiger auf eine Null-terminierte Zeichenfolge, der angibt, das Klartext-Kennwort für das Benutzerkonto an, die anhand des *PszUserName*.

*dwLogonType*<br/>
Gibt den Typ des Anmeldevorgangs ausführen. Finden Sie unter [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) Weitere Details.

*dwLogonProvider*<br/>
Gibt den Anmeldungsanbieter. Finden Sie unter [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Der Zugriff mit dem token aufgrund der Anmeldung zugeordnet wird die `CAccessToken`. Für diese Methode erfolgreich ausgeführt werden kann die `CAccessToken` Objekt obligatorisch SE_TCB_NAME verfügt, den Inhaber der als Teil der vertrauenswürdige Computer Basis identifiziert. Finden Sie unter [LogonUser](/windows/desktop/api/winbase/nf-winbase-logonusera) Informationen in Bezug auf die erforderlichen Berechtigungen.

##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken

Rufen Sie diese Methode aus, in einen COM-Server, die Behandlung von eines Aufrufs von einem Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus der COM-Client.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bImpersonate*<br/>
Bei "true", wird der aktuelle Thread die aufrufenden COM-Client imitieren, wenn dieser Aufruf erfolgreich ausgeführt wird. False gibt an, das Zugriffstoken wird geöffnet, aber der Thread haben kein Identitätswechseltoken, wenn dieser Aufruf abgeschlossen ist.

*bOpenAsSelf*<br/>
Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Thread erfolgen die [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter auf "false" ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread einen Client einen Identitätswechsel ausführt, kann in folgendem Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter TRUE ist, ist die zugriffsprüfung erfolgt mit den Sicherheitskontext des Prozesses für den aufrufenden Thread.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die [CAutoRevertImpersonation-Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch Wiederherstellen der *bImpersonate* Flag auf "true".

##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken

Rufen Sie diese Methode von innerhalb eines Servers übernehmen Anforderungen über eine named Pipe zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parameter

*hPipe*<br/>
Handle für eine named Pipe.

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bImpersonate*<br/>
Bei "true", wird der aktuelle Thread den aufrufenden Pipeclient imitieren, wenn dieser Aufruf erfolgreich ausgeführt wird. False gibt an, das Zugriffstoken wird geöffnet, aber der Thread haben kein Identitätswechseltoken, wenn dieser Aufruf abgeschlossen ist.

*bOpenAsSelf*<br/>
Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Thread erfolgen die [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter auf "false" ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread einen Client einen Identitätswechsel ausführt, kann in folgendem Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter TRUE ist, ist die zugriffsprüfung erfolgt mit den Sicherheitskontext des Prozesses für den aufrufenden Thread.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die [CAutoRevertImpersonation-Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch Wiederherstellen der *bImpersonate* Flag auf "true".

##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken

Rufen Sie diese Methode aus, auf einem Server, die Behandlung von eines Aufrufs aus einem RPC-Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parameter

*BindingHandle*<br/>
Handle der Bindung auf dem Server, der eine Bindung an einen Client darstellt.

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bImpersonate*<br/>
Bei "true", wird der aktuelle Thread des aufrufenden RPC-Clients imitieren, wenn dieser Aufruf erfolgreich ausgeführt wird. False gibt an, das Zugriffstoken wird geöffnet, aber der Thread haben kein Identitätswechseltoken, wenn dieser Aufruf abgeschlossen ist.

*bOpenAsSelf*<br/>
Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Thread erfolgen die [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter auf "false" ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread einen Client einen Identitätswechsel ausführt, kann in folgendem Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter TRUE ist, ist die zugriffsprüfung erfolgt mit den Sicherheitskontext des Prozesses für den aufrufenden Thread.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die [CAutoRevertImpersonation-Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch Wiederherstellen der *bImpersonate* Flag auf "true".

##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken

Rufen Sie diese Methode, um die Ebene des Identitätswechsels festgelegt, und initialisieren Sie die `CAccessToken` mit dem Token aus dem angegebenen Thread.

```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bImpersonate*<br/>
Wenn "true", wird der Thread nach dem Abschluss dieser Methode auf die angeforderte Identitätswechselebene bleiben. False gibt an, wird der Thread auf die ursprüngliche Ebene des Identitätswechsels zurückgesetzt.

*bOpenAsSelf*<br/>
Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Thread erfolgen die [GetThreadToken](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter auf "false" ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread einen Client einen Identitätswechsel ausführt, kann in folgendem Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter TRUE ist, ist die zugriffsprüfung erfolgt mit den Sicherheitskontext des Prozesses für den aufrufenden Thread.

*sil*<br/>
Gibt an, eine [SECURITY_IMPERSONATION_LEVEL](/windows/desktop/api/winnt/ne-winnt-_security_impersonation_level) Enumerationstyp, die die Ebene des Identitätswechsels des Tokens angibt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

`OpenThreadToken` ist vergleichbar mit [CAccessToken::GetThreadToken](#getthreadtoken), sondern legt die Identitätswechselebene fest, vor der Initialisierung der `CAccessToken` von Zugriffstoken des Threads.

Die [CAutoRevertImpersonation-Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch Wiederherstellen der *bImpersonate* Flag auf "true".

##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck

Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene Gruppe von Berechtigungen aktiviert sind, der `CAccessToken` Objekt.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Parameter

*RequiredPrivileges*<br/>
Zeiger auf eine [PRIVILEGE_SET](/windows/desktop/api/winnt/ns-winnt-_privilege_set) Struktur.

*pbResult*<br/>
Zeiger auf einen Wert die-Methode legt fest, um anzugeben, ob einige oder alle der angegebenen Berechtigung, in aktiviert sind der `CAccessToken` Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Wenn `PrivilegeCheck` zurückgegeben wird, die `Attributes` Mitglied aller ["LUID_AND_ATTRIBUTES"](/windows/desktop/api/winnt/ns-winnt-_luid_and_attributes) Struktur auf SE_PRIVILEGE_USED_FOR_ACCESS festgelegt ist, wenn die entsprechende Berechtigung aktiviert ist. Diese Methode ruft die [PrivilegeCheck](/windows/desktop/api/securitybaseapi/nf-securitybaseapi-privilegecheck) Win32-Funktion.

##  <a name="revert"></a>  CAccessToken::Revert

Rufen Sie diese Methode, um einen Thread aus mit einem Identitätswechseltoken zu beenden.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Parameter

*hThread*<br/>
Handle für den Thread zum Identitätswechsel zurückgesetzt. Wenn *hThread* NULL ist, wird der aktuelle Thread angenommen.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die Zurücksetzung von Identitätswechseltoken kann automatisch ausgeführt werden, mit der [CAutoRevertImpersonation-Klasse](../../atl/reference/cautorevertimpersonation-class.md).

##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl

Rufen Sie diese Methode zum Festlegen der standardmäßigen DACL den `CAccessToken` Objekt.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Parameter

*rDacl*<br/>
Der neue Standard [CDacl-Klasse](../../atl/reference/cdacl-class.md) Informationen.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Der Standardwert ist die DACL der DACL, die standardmäßig verwendet wird, wenn neue Objekte faktisch mit dieser Zugangs-Token erstellt werden.

##  <a name="setowner"></a>  CAccessToken::SetOwner

Rufen Sie diese Methode zum Festlegen des Besitzers der `CAccessToken` Objekt.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Die [CSid-Klasse](../../atl/reference/csid-class.md) -Objekt, das die Informationen zum Besitzer enthält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Der Besitzer ist der Standardbesitzer, die verwendet wird, für neue Objekte erstellt, während das Zugriffstoken gültig ist.

##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup

Rufen Sie diese Methode, um die primäre Gruppe des Festlegen der `CAccessToken` Objekt.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Die [CSid-Klasse](../../atl/reference/csid-class.md) -Objekt, das die primäre Gruppeninformationen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die primäre Gruppe ist die Standardgruppe für neue Objekte erstellt, während das Zugriffstoken gültig ist.

## <a name="see-also"></a>Siehe auch

[ATLSecurity-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Zugriffstoken](/windows/desktop/SecAuthZ/access-tokens)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
