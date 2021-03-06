---
title: CAccessToken-Klasse
ms.date: 07/02/2019
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
ms.openlocfilehash: 33fbaae5dafaccdf7f7e6880eaa42dd68352e840
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497917"
---
# <a name="caccesstoken-class"></a>CAccessToken-Klasse

Diese Klasse ist ein Wrapper für ein Zugriffs Token.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

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
|[CAccessToken::Attach](#attach)|Ruft diese Methode auf, um den Besitz des angegebenen Zugriffs Token-Handles zu übernehmen.|
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Ruft diese Methode auf, um zu bestimmen, ob eine angegebene sid `CAccessToken` im-Objekt aktiviert ist.|
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Rufen Sie diese Methode auf, um ein neues Identitätswechsel-Zugriffs Token zu erstellen.|
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Rufen Sie diese Methode auf, um ein neues primäres Token zu erstellen.|
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Rufen Sie diese Methode auf, um einen neuen Prozess zu erstellen, der im Sicherheitskontext des Benutzers `CAccessToken` ausgeführt wird, der vom-Objekt dargestellt wird.|
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Rufen Sie diese Methode auf, um ein neues `CAccessToken` , eingeschränktes Objekt zu erstellen.|
|[CAccessToken::Detach](#detach)|Rufen Sie diese Methode auf, um den Besitz des Zugriffs Tokens aufzuheben.|
|[CAccessToken::DisablePrivilege](#disableprivilege)|Mit dieser Methode können Sie eine Berechtigung im `CAccessToken` -Objekt deaktivieren.|
|[CAccessToken::DisablePrivileges](#disableprivileges)|Mit dieser Methode können Sie eine oder mehrere Berechtigungen im `CAccessToken` Objekt deaktivieren.|
|[CAccessToken::EnablePrivilege](#enableprivilege)|Diese Methode wird aufgerufen, um eine Berechtigung im `CAccessToken` -Objekt zu aktivieren.|
|[CAccessToken::EnablePrivileges](#enableprivileges)|Diese Methode wird aufgerufen, um eine oder mehrere Berechtigungen im `CAccessToken` Objekt zu aktivieren.|
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Ruft diese Methode auf, um `CAccessToken` die standarddacl des Objekts zurückzugeben.|
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Ruft diese Methode auf, um `CAccessToken` das Objekt zu erhalten, das dem Zugriffs Token entspricht, das für den aktuellen Thread wirksam ist.|
|[CAccessToken::GetGroups](#getgroups)|Ruft diese Methode auf, um `CAccessToken` die Tokengruppen des Objekts zurückzugeben.|
|[CAccessToken::GetHandle](#gethandle)|Rufen Sie diese Methode auf, um ein Handle für das Zugriffs Token abzurufen.|
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Aufrufen Sie diese Methode, um die Identitätswechsel Ebene aus dem Zugriffs Token abzurufen.|
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Ruft diese Methode auf, um die dem- `CAccessToken` Objekt zugeordnete Anmelde Sitzungs-ID abzurufen.|
|[CAccessToken::GetLogonSid](#getlogonsid)|Mit dieser Methode können Sie die dem- `CAccessToken` Objekt zugeordnete Anmelde-SID abrufen.|
|[CAccessToken::GetOwner](#getowner)|Mit dieser Methode können Sie den Besitzer abrufen, der `CAccessToken` dem Objekt zugeordnet ist.|
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Mit dieser Methode können Sie die primäre Gruppe abrufen, die `CAccessToken` dem Objekt zugeordnet ist.|
|[CAccessToken::GetPrivileges](#getprivileges)|Mit dieser Methode können Sie die Berechtigungen abrufen, die `CAccessToken` dem-Objekt zugeordnet sind.|
|[CAccessToken::GetProcessToken](#getprocesstoken)|Rufen Sie diese Methode auf, um `CAccessToken` mit dem Zugriffstoken aus einem Prozess zu initialisieren.|
|[CAccessToken::GetProfile](#getprofile)|Mit dieser Methode wird das Handle aufgerufen, das auf das Benutzerprofil verweist, `CAccessToken` das dem Objekt zugeordnet ist.|
|[CAccessToken::GetSource](#getsource)|Mit dieser Methode können Sie die Quelle des `CAccessToken` Objekts abrufen.|
|[CAccessToken::GetStatistics](#getstatistics)|Mit dieser Methode können Sie Informationen abrufen, die `CAccessToken` dem-Objekt zugeordnet sind.|
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Mit dieser Methode können Sie die Terminal Dienste-Sitzungs-ID abrufen `CAccessToken` , die dem Objekt zugeordnet ist.|
|[CAccessToken::GetThreadToken](#getthreadtoken)|Ruft diese Methode auf, um `CAccessToken` mit dem Token aus dem angegebenen Thread zu initialisieren.|
|[CAccessToken::GetTokenId](#gettokenid)|Mit dieser Methode können Sie die Token-ID abrufen, `CAccessToken` die dem Objekt zugeordnet ist.|
|[CAccessToken::GetType](#gettype)|Mit dieser Methode können Sie den Tokentyp des `CAccessToken` Objekts abrufen.|
|[CAccessToken::GetUser](#getuser)|Mit dieser Methode können Sie den Benutzer identifizieren, der `CAccessToken` dem Objekt zugeordnet ist.|
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Mit dieser Methode wird das Handle aufgerufen, das auf das Benutzerprofil verweist, `CAccessToken` das dem Objekt zugeordnet ist.|
|[CAccessToken:: Identitätswechsel](#impersonate)|Mit dieser Methode können `CAccessToken` Sie einem Thread einen Identitätswechsel zuweisen.|
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Rufen Sie diese Methode auf, um zuzulassen, dass der aufrufende Thread die Identität des Sicherheits Kontexts eines angemeldeten Benutzers annimmt.|
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Mit dieser Methode können Sie überprüfen `CAccessToken` , ob das Objekt eine Liste eingeschränkter SIDs enthält.|
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Ruft diese Methode auf, um das dem- `CAccessToken` Objekt zugeordnete Benutzerprofil zu laden.|
|[CAccessToken::LogonUser](#logonuser)|Rufen Sie diese Methode auf, um eine Anmelde Sitzung für den Benutzer zu erstellen, der den angegebenen Anmelde Informationen zugeordnet ist.|
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Aufrufen Sie diese Methode aus einem com-Server, der einen-Client aufruft, der `CAccessToken` einen-Client aufruft, um mit dem Zugriffs Token des com-Clients zu initialisieren.|
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Aufrufen Sie diese Methode aus einem Server, der Anforderungen über einen Named Pipe annimmt, um `CAccessToken` das mit dem Zugriffs Token vom Client zu initialisieren.|
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Aufrufen Sie diese Methode aus einem Server, der einen Aufruf von einem RPC-Client verarbeitet, `CAccessToken` um das mit dem Zugriffs Token vom Client zu initialisieren.|
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Ruft diese Methode auf, um die Identitätswechsel Ebene festzulegen, und `CAccessToken` initialisiert dann mit dem Token aus dem angegebenen Thread.|
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Ruft diese Methode auf, um zu bestimmen, ob ein angegebener Berechtigungs Satz im `CAccessToken` Objekt aktiviert ist.|
|[CAccessToken::Revert](#revert)|Mit dieser Methode können Sie einen Thread beenden, der ein Identitätswechsel Token verwendet.|
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Mit dieser Methode können Sie die standarddacl des `CAccessToken` Objekts festlegen.|
|[CAccessToken::SetOwner](#setowner)|Mit dieser Methode wird der Besitzer des `CAccessToken` Objekts festgelegt.|
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Mit dieser Methode wird die primäre Gruppe des `CAccessToken` -Objekts festgelegt.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffs Token](/windows/win32/SecAuthZ/access-tokens) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und jedem Benutzer zugeordnet ist, der bei einem Windows-System angemeldet ist.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/win32/SecAuthZ/access-control) in der Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="attach"></a>CAccessToken:: Attach

Ruft diese Methode auf, um den Besitz des angegebenen Zugriffs Token-Handles zu übernehmen.

```
void Attach(HANDLE hToken) throw();
```

### <a name="parameters"></a>Parameter

*hToken*<br/>
Ein Handle für das Zugriffs Token.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Fehler auf, wenn das `CAccessToken` Objekt bereits über einen Besitz eines Zugriffs Tokens verfügt.

##  <a name="dtor"></a>CAccessToken:: ~ CAccessToken

Der Destruktor.

```
virtual ~CAccessToken() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordneten Ressourcen frei.

##  <a name="checktokenmembership"></a>CAccessToken:: checktokenmembership

Ruft diese Methode auf, um zu bestimmen, ob eine angegebene sid `CAccessToken` im-Objekt aktiviert ist.

```
bool CheckTokenMembership(
    const CSid& rSid,
    bool* pbIsMember) const throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Verweis auf ein [CSID-Klassen](../../atl/reference/csid-class.md) Objekt.

*pbIsMember*<br/>
Ein Zeiger auf eine Variable, die die Ergebnisse der Überprüfung empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die `CheckTokenMembership` -Methode überprüft, ob die SID in den Benutzer-und Gruppen-SIDs des Zugriffs Tokens vorhanden ist. Wenn die SID vorhanden ist und über das SE_GROUP_ENABLED-Attribut verfügt, wird *pbismember* auf true festgelegt. Andernfalls wird Sie auf "false" festgelegt.

In Debugbuilds tritt ein Fehler auf, wenn *pbismember* kein gültiger Zeiger ist.

> [!NOTE]
>  Das `CAccessToken` Objekt muss ein Identitätswechsel Token und kein primäres Token sein.

##  <a name="createimpersonationtoken"></a>CAccessToken:: kreateimpersonationtoken

Rufen Sie diese Methode auf, um ein Identitätswechsel-Zugriffs Token zu erstellen.

```
bool CreateImpersonationToken(
    CAccessToken* pImp,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```

### <a name="parameters"></a>Parameter

*pImp*<br/>
Zeiger auf das neue `CAccessToken` -Objekt.

*sil*<br/>
Gibt einen [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) -enumerierten Typ an, der die Identitätswechsel Ebene des neuen Tokens bereitstellt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

`CreateImpersonationToken`Ruft [duplicatetoken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetoken) auf, um ein neues Identitätswechsel Token zu erstellen.

##  <a name="createprimarytoken"></a>CAccessToken:: kreateprimarytoken

Rufen Sie diese Methode auf, um ein neues primäres Token zu erstellen.

```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*pPri*<br/>
Zeiger auf das neue `CAccessToken` -Objekt.

*dwDesiredAccess*<br/>
Gibt die angeforderten Zugriffsrechte für das neue Token an. Der Standardwert, MAXIMUM_ALLOWED, fordert alle Zugriffsrechte an, die für den Aufrufer gültig sind. Weitere Informationen zu Zugriffsrechten finden Sie unter [Zugriffsrechte und Zugriffs Masken](/windows/win32/SecAuthZ/access-rights-and-access-masks) .

*pTokenAttributes*<br/>
Ein Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) -Struktur, die eine Sicherheits Beschreibung für das neue Token angibt und bestimmt, ob untergeordnete Prozesse das Token erben können. Wenn " *ptokenattribute* " den Wert NULL hat, erhält das Token eine Standard Sicherheits Beschreibung, und das Handle kann nicht geerbt werden.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

`CreatePrimaryToken`Ruft [duplicatcher etokenex](/windows/win32/api/securitybaseapi/nf-securitybaseapi-duplicatetokenex) auf, um ein neues primäres Token zu erstellen.

##  <a name="createprocessasuser"></a>CAccessToken:: Benutzer

Rufen Sie diese Methode auf, um einen neuen Prozess zu erstellen, der im Sicherheitskontext des Benutzers `CAccessToken` ausgeführt wird, der vom-Objekt dargestellt wird.

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
Zeiger auf eine mit NULL endenden Zeichenfolge, die das auszuführende Modul angibt. Dieser Parameter darf nicht NULL sein.

*pCommandLine*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die die auszuführende Befehlszeile angibt.

*pProcessInformation*<br/>
Zeiger auf eine [PROCESS_INFORMATION-Struktur](/windows/win32/api/processthreadsapi/ns-processthreadsapi-process_information) , die Identifikationsinformationen über den neuen Prozess empfängt.

*pStartupInfo*<br/>
Ein Zeiger auf eine [STARTUPINFO](/windows/win32/api/processthreadsapi/ns-processthreadsapi-startupinfow) -Struktur, die angibt, wie das Hauptfenster für den neuen Prozess angezeigt werden soll.

*dwCreationFlags*<br/>
Gibt zusätzliche Flags an, mit denen die Prioritäts Klasse und die Prozesserstellung gesteuert werden. Eine Liste der Flags finden Sie unter der Win32-Funktion " [kreateprocessasuser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw) ".

*bLoadProfile*<br/>
TRUE gibt an, dass das Profil des Benutzers mit [LoadUserProfile](/windows/win32/api/userenv/nf-userenv-loaduserprofilew)geladen wird.

*pProcessAttributes*<br/>
Ein Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) -Struktur, die eine Sicherheits Beschreibung für den neuen Prozess angibt und bestimmt, ob untergeordnete Prozesse das zurückgegebene Handle erben können. Wenn *pprocessattribute* den Wert NULL hat, erhält der Prozess eine Standard Sicherheits Beschreibung, und das Handle kann nicht geerbt werden.

*pThreadAttributes*<br/>
Ein Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) -Struktur, die eine Sicherheits Beschreibung für den neuen Thread angibt und bestimmt, ob untergeordnete Prozesse das zurückgegebene Handle erben können. Wenn *pthreadattribute* NULL ist, erhält der Thread eine Standard Sicherheits Beschreibung, und das Handle kann nicht geerbt werden.

*bInherit*<br/>
Gibt an, ob der neue Prozess Handles vom aufrufenden Prozess erbt. TRUE gibt an, dass jedes vererbbare geöffnete Handle im aufrufenden Prozess vom neuen Prozess geerbt wird. Geerbte Handles verfügen über dieselben Werte und Zugriffsberechtigungen wie die ursprünglichen Handles.

*pCurrentDirectory*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die das aktuelle Laufwerk und Verzeichnis für den neuen Prozess angibt. Die Zeichenfolge muss ein vollständiger Pfad sein, der einen Laufwerk Buchstaben enthält. Wenn dieser Parameter NULL ist, weist der neue Prozess dasselbe aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess auf.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

`CreateProcessAsUser`verwendet die `CreateProcessAsUser` Win32-Funktion, um einen neuen Prozess zu erstellen, der im Sicherheitskontext des Benutzers ausgeführt wird `CAccessToken` , der durch das-Objekt dargestellt wird. Eine vollständige Erläuterung der erforderlichen Parameter finden Sie in der Beschreibung der Funktion [CreateProcessAsUser](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createprocessasuserw).

Damit diese Methode erfolgreich ausgeführt werden kann `CAccessToken` , muss das Objekt zugriffprimarytoken (sofern es sich nicht um ein eingeschränktes Token handelt) und erstellungszugriffsberechtigungen enthalten.

##  <a name="createrestrictedtoken"></a>CAccessToken:: anaterestrictedtoken

Rufen Sie diese Methode auf, um ein neues `CAccessToken` , eingeschränktes Objekt zu erstellen.

```
bool CreateRestrictedToken(
    CAccessToken* pRestrictedToken,
    const CTokenGroups& SidsToDisable,
    const CTokenGroups& SidsToRestrict,
    const CTokenPrivileges& PrivilegesToDelete = CTokenPrivileges()) const throw(...);
```

### <a name="parameters"></a>Parameter

*pRestrictedToken*<br/>
Das neue, eingeschränkte `CAccessToken` Objekt.

*Sidstodeaktivieren*<br/>
Ein `CTokenGroups` -Objekt, das die nicht Verweigerungs-SIDs angibt.

*SidsToRestrict*<br/>
Ein `CTokenGroups` -Objekt, das die einschränkenden SIDs angibt.

*Privilegestodelete*<br/>
Ein `CTokenPrivileges` -Objekt, das die Berechtigungen angibt, die im eingeschränkten Token gelöscht werden sollen. Standardmäßig wird ein leeres-Objekt erstellt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

`CreateRestrictedToken`verwendet die Win32-Funktion von "| [aterestrictedtoken](/windows/win32/api/securitybaseapi/nf-securitybaseapi-createrestrictedtoken) " `CAccessToken` , um ein neues-Objekt mit Einschränkungen zu erstellen.

> [!IMPORTANT]
>  Wenn Sie `CreateRestrictedToken`verwenden, stellen Sie Folgendes sicher: das vorhandene Token ist gültig (und nicht vom Benutzer eingegeben), und " *sidstodeaktivieren* " und " *privilegestodelete* " sind sowohl gültig (nicht vom Benutzer eingegeben). Wenn die Methode false zurückgibt, verweigern Sie die Funktionalität.

##  <a name="detach"></a>CAccessToken::D Etach

Rufen Sie diese Methode auf, um den Besitz des Zugriffs Tokens aufzuheben.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Handle für das `CAccessToken` zurück, das getrennt wurde.

### <a name="remarks"></a>Hinweise

Diese Methode widerruft den `CAccessToken`Besitz des Zugriffs Tokens.

##  <a name="disableprivilege"></a>CAccessToken::D isableprivilege

Mit dieser Methode können Sie eine Berechtigung im `CAccessToken` -Objekt deaktivieren.

```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Ein Zeiger auf eine Zeichenfolge, die die im `CAccessToken` -Objekt zu deaktivierende Berechtigung enthält.

*pPreviousState*<br/>
Zeiger auf ein `CTokenPrivileges` -Objekt, das den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="disableprivileges"></a>CAccessToken::D isableprivileges

Mit dieser Methode können Sie eine oder mehrere Berechtigungen im `CAccessToken` Objekt deaktivieren.

```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*rprivileges*<br/>
Zeiger auf ein Array von Zeichen folgen, das die im `CAccessToken` -Objekt zu deaktivierenden Berechtigungen enthält.

*pPreviousState*<br/>
Zeiger auf ein `CTokenPrivileges` -Objekt, das den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="enableprivilege"></a>CAccessToken:: enableprivilege

Diese Methode wird aufgerufen, um eine Berechtigung im `CAccessToken` -Objekt zu aktivieren.

```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*pszPrivilege*<br/>
Zeiger auf eine Zeichenfolge, die die Berechtigung enthält, `CAccessToken` die im-Objekt aktiviert werden soll.

*pPreviousState*<br/>
Zeiger auf ein `CTokenPrivileges` -Objekt, das den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="enableprivileges"></a>CAccessToken:: enableprivileges

Diese Methode wird aufgerufen, um eine oder mehrere Berechtigungen im `CAccessToken` Objekt zu aktivieren.

```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```

### <a name="parameters"></a>Parameter

*rprivileges*<br/>
Zeiger auf ein Array von Zeichen folgen, das die im `CAccessToken` -Objekt zu aktivierenden Berechtigungen enthält.

*pPreviousState*<br/>
Zeiger auf ein `CTokenPrivileges` -Objekt, das den vorherigen Zustand der Berechtigungen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getdefaultdacl"></a>CAccessToken:: getdefaultdacl

Ruft diese Methode auf, um `CAccessToken` die standarddacl des Objekts zurückzugeben.

```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```

### <a name="parameters"></a>Parameter

*pDacl*<br/>
Ein Zeiger auf das [CDacl-Klassen](../../atl/reference/cdacl-class.md) Objekt, das `CAccessToken` die standarddacl des Objekts empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die DACL-Standard Wiederherstellung wieder hergestellt wurde, andernfalls false.

##  <a name="geteffectivetoken"></a>CAccessToken:: geteffectivetoken

Ruft diese Methode auf, um `CAccessToken` das Objekt zu erhalten, das dem Zugriffs Token entspricht, das für den aktuellen Thread wirksam ist.

```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getgroups"></a>CAccessToken:: GetGroups

Ruft diese Methode auf, um `CAccessToken` die Tokengruppen des Objekts zurückzugeben.

```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```

### <a name="parameters"></a>Parameter

*pGroups*<br/>
Zeiger auf das [cdekengroups-Klassen](../../atl/reference/ctokengroups-class.md) Objekt, das die Gruppeninformationen empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="gethandle"></a>CAccessToken:: GetHandle

Rufen Sie diese Methode auf, um ein Handle für das Zugriffs Token abzurufen.

```
HANDLE GetHandle() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle für das `CAccessToken` Zugriffs Token des-Objekts zurück.

##  <a name="getimpersonationlevel"></a>CAccessToken:: getimpersonationlevel

Aufrufen Sie diese Methode, um die Identitätswechsel Ebene aus dem Zugriffs Token abzurufen.

```
bool GetImpersonationLevel(
    SECURITY_IMPERSONATION_LEVEL* pImpersonationLevel) const throw(...);
```

### <a name="parameters"></a>Parameter

*pImpersonationLevel*<br/>
Zeiger auf einen [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) -Enumerationstyp, der die Informationen zur Identitätswechsel Ebene empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getlogonsessionid"></a>CAccessToken:: getlogonsessionid

Ruft diese Methode auf, um die dem- `CAccessToken` Objekt zugeordnete Anmelde Sitzungs-ID abzurufen.

```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pluid*<br/>
Zeiger auf eine [LUID](/windows/win32/api/winnt/ns-winnt-luid) , die die Anmelde Sitzungs-ID empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Fehler auf, wenn *pluid* ein ungültiger Wert ist.

##  <a name="getlogonsid"></a>CAccessToken:: getlogonsid

Mit dieser Methode können Sie die dem- `CAccessToken` Objekt zugeordnete Anmelde-SID abrufen.

```
bool GetLogonSid(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf ein [CSID-Klassen](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Fehler auf, wenn *PSID* ein ungültiger Wert ist.

##  <a name="getowner"></a>CAccessToken:: GetOwner

Mit dieser Methode können Sie den Besitzer abrufen, der `CAccessToken` dem Objekt zugeordnet ist.

```
bool GetOwner(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf ein [CSID-Klassen](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Der Besitzer wird standardmäßig für alle Objekte festgelegt, die erstellt werden, während dieses Zugriffs Token aktiviert ist.

##  <a name="getprimarygroup"></a>CAccessToken:: getprimarygroup

Mit dieser Methode können Sie die primäre Gruppe abrufen, die `CAccessToken` dem Objekt zugeordnet ist.

```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf ein [CSID-Klassen](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die Gruppe wird standardmäßig für alle Objekte festgelegt, die erstellt werden, während dieses Zugriffs Token aktiviert ist.

##  <a name="getprivileges"></a>CAccessToken:: getprivileges

Mit dieser Methode können Sie die Berechtigungen abrufen, die `CAccessToken` dem-Objekt zugeordnet sind.

```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```

### <a name="parameters"></a>Parameter

*pprivileges*<br/>
Zeiger auf ein [CTokenPrivileges-Klassen](../../atl/reference/ctokenprivileges-class.md) Objekt, das die Berechtigungen erhält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getprocesstoken"></a>CAccessToken:: getprocesstoken

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

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Ruft die [OpenProcessToken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-openprocesstoken) -Win32-Funktion auf.

##  <a name="getprofile"></a>CAccessToken:: GetProfile

Mit dieser Methode wird das Handle aufgerufen, das auf das Benutzerprofil verweist, `CAccessToken` das dem Objekt zugeordnet ist.

```
HANDLE GetProfile() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle zurück, das auf das Benutzerprofil verweist, oder NULL, wenn kein Profil vorhanden ist.

##  <a name="getsource"></a>CAccessToken:: GetSource

Mit dieser Methode können Sie die Quelle des `CAccessToken` Objekts abrufen.

```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSource*<br/>
Zeiger auf eine [TOKEN_SOURCE](/windows/win32/api/winnt/ns-winnt-token_source) -Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getstatistics"></a>CAccessToken:: getstatistics

Mit dieser Methode können Sie Informationen abrufen, die `CAccessToken` dem-Objekt zugeordnet sind.

```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```

### <a name="parameters"></a>Parameter

*pStatistics*<br/>
Zeiger auf eine [TOKEN_STATISTICS](/windows/win32/api/winnt/ns-winnt-token_statistics) -Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getterminalservicessessionid"></a>CAccessToken:: getterminalservicessessionid

Mit dieser Methode können Sie die Terminal Dienste-Sitzungs-ID abrufen `CAccessToken` , die dem Objekt zugeordnet ist.

```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```

### <a name="parameters"></a>Parameter

*pdwSessionId*<br/>
Die Terminal Dienste-Sitzungs-ID.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="getthreadtoken"></a>CAccessToken:: getthreadtoken

Ruft diese Methode auf, um `CAccessToken` mit dem Token aus dem angegebenen Thread zu initialisieren.

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
Handle für den Thread, dessen Zugriffs Token geöffnet wird.

*bOpenAsSelf*<br/>
Gibt an, ob die Zugriffs Überprüfung für den Sicherheitskontext des Threads, der die `GetThreadToken` Methode aufrufen, oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread durchgeführt werden soll.

Wenn dieser Parameter false ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread ausgeführt. Wenn der Thread die Identität eines Clients annimmt, kann dieser Sicherheitskontext der eines Client Prozesses sein. Wenn dieser Parameter true ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread durchgeführt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="gettokenid"></a>CAccessToken:: gettokenid

Mit dieser Methode können Sie die Token-ID abrufen, `CAccessToken` die dem Objekt zugeordnet ist.

```
bool GetTokenId(LUID* pluid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pluid*<br/>
Zeiger auf eine [LUID](/windows/win32/api/winnt/ns-winnt-luid) , von der die Token-ID empfangen wird.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="gettype"></a>CAccessToken:: GetType

Mit dieser Methode können Sie den Tokentyp des `CAccessToken` Objekts abrufen.

```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```

### <a name="parameters"></a>Parameter

*pType*<br/>
Adresse der [TOKEN_TYPE](/windows/win32/api/winnt/ne-winnt-token_type) -Variablen, die bei Erfolg den Typ des Tokens empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Der TOKEN_TYPE-Enumerationstyp enthält Werte, die zwischen einem primären Token und einem Identitätswechsel Token unterscheiden.

##  <a name="getuser"></a>CAccessToken:: GetUser

Mit dieser Methode können Sie den Benutzer identifizieren, der `CAccessToken` dem Objekt zugeordnet ist.

```
bool GetUser(CSid* pSid) const throw(...);
```

### <a name="parameters"></a>Parameter

*pSid*<br/>
Zeiger auf ein [CSID-Klassen](../../atl/reference/csid-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

##  <a name="hkeycurrentuser"></a>CAccessToken:: hkeycurrentuser

Mit dieser Methode wird das Handle aufgerufen, das auf das Benutzerprofil verweist, `CAccessToken` das dem Objekt zugeordnet ist.

```
HKEY HKeyCurrentUser() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle zurück, das auf das Benutzerprofil verweist, oder NULL, wenn kein Profil vorhanden ist.

##  <a name="impersonate"></a>CAccessToken:: Identitätswechsel

Mit dieser Methode können `CAccessToken` Sie einem Thread einen Identitätswechsel zuweisen.

```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```

### <a name="parameters"></a>Parameter

*hThread*<br/>
Handle für den Thread, dem das Identitätswechsel Token zugewiesen werden soll. Dieses Handle muss mit TOKEN_IMPERSONATE-Zugriffsrechten geöffnet worden sein. Wenn *hThread* NULL ist, bewirkt die-Methode, dass der Thread die Verwendung eines Identitätswechsel Tokens beendet.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Assertionsfehler `CAccessToken` auf, wenn keinen gültigen Zeiger auf ein Token hat.

Die [cautorevertimpersonations-Klasse](../../atl/reference/cautorevertimpersonation-class.md) kann verwendet werden, um die Identität der Zugriffs Token automatisch zurückzusetzen.

##  <a name="impersonateloggedonuser"></a>CAccessToken:: Identität ateloggedonuser

Rufen Sie diese Methode auf, um zuzulassen, dass der aufrufende Thread die Identität des Sicherheits Kontexts eines angemeldeten Benutzers annimmt.

```
bool ImpersonateLoggedOnUser() const throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

> [!IMPORTANT]
>  Wenn ein Aufrufe einer Identitätswechsel Funktion aus irgendeinem Grund fehlschlägt, wird für den Client kein Identitätswechsel durchgeführt, und die Client Anforderung wird im Sicherheitskontext des Prozesses vorgenommen, von dem aus der-Vorgang ausgeführt wurde. Wenn der Prozess als ein Konto mit hohen Berechtigungen oder als Mitglied einer administrativen Gruppe ausgeführt wird, kann der Benutzer möglicherweise Aktionen ausführen, die er andernfalls nicht zulässt. Daher sollte der Rückgabewert für diese Funktion immer bestätigt werden.

##  <a name="istokenrestricted"></a>CAccessToken:: istokenrestricted

Mit dieser Methode können Sie überprüfen `CAccessToken` , ob das Objekt eine Liste eingeschränkter SIDs enthält.

```
bool IsTokenRestricted() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das Objekt eine Liste mit einschränkenden SIDs enthält, false, wenn keine einschränkenden SIDs vorhanden sind oder wenn die Methode fehlschlägt.

##  <a name="loaduserprofile"></a>CAccessToken:: LoadUserProfile

Ruft diese Methode auf, um das dem- `CAccessToken` Objekt zugeordnete Benutzerprofil zu laden.

```
bool LoadUserProfile() throw(...);
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

In Debugbuilds tritt ein Fehler auf, wenn der `CAccessToken` kein gültiges Token enthält oder wenn bereits ein Benutzerprofil vorhanden ist.

##  <a name="logonuser"></a>CAccessToken:: LogonUser

Rufen Sie diese Methode auf, um eine Anmelde Sitzung für den Benutzer zu erstellen, der den angegebenen Anmelde Informationen zugeordnet ist.

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
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Benutzernamen angibt. Dies ist der Name des Benutzerkontos, bei dem Sie sich anmelden möchten.

*pszDomain*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen der Domäne oder des Servers angibt, deren Konto Datenbank das *pszusername* -Konto enthält.

*pszPassword*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die das klar Text Kennwort für das durch *pszusername*angegebene Benutzerkonto angibt.

*dwLogonType*<br/>
Gibt den Typ des auszuführenden Anmeldevorgangs an. Weitere Informationen finden Sie unter [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

*dwLogonProvider*<br/>
Gibt den Anmelde Anbieter an. Weitere Informationen finden Sie unter [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Das Zugriffs Token, das sich aus der Anmeldung ergibt, wird `CAccessToken`dem zugeordnet. Damit diese Methode erfolgreich ausgeführt werden kann `CAccessToken` , muss das Objekt über SE_TCB_NAME-Berechtigungen verfügen, und der Inhaber wird als Teil der vertrauenswürdigen Computer Basis identifiziert. Weitere Informationen zu den erforderlichen Berechtigungen finden Sie unter [LogonUser](/windows/win32/api/winbase/nf-winbase-logonuserw) .

##  <a name="opencomclienttoken"></a>CAccessToken:: opencomclienttoken

Aufrufen Sie diese Methode aus einem com-Server, der einen-Client aufruft, der `CAccessToken` einen-Client aufruft, um mit dem Zugriffs Token des com-Clients zu initialisieren.

```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parameter

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bimpersonate*<br/>
TRUE gibt an, dass der aktuelle Thread die Identität des aufrufenden com-Clients annimmt, wenn dieser Aufruf erfolgreich abgeschlossen wird. Wenn der Wert false ist, wird das Zugriffs Token geöffnet, aber der Thread besitzt kein Identitätswechsel Token, wenn dieser Vorgang abgeschlossen wird.

*bOpenAsSelf*<br/>
Gibt an, ob die Zugriffs Überprüfung für den Sicherheitskontext des Threads durchgeführt werden soll, der die [getthreadtoken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) -Methode aufrufen, oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter false ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread ausgeführt. Wenn der Thread die Identität eines Clients annimmt, kann dieser Sicherheitskontext der eines Client Prozesses sein. Wenn dieser Parameter true ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread durchgeführt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die [cautorevertimpersonations-Klasse](../../atl/reference/cautorevertimpersonation-class.md) kann verwendet werden, um Identitätswechsel-Zugriffs Token, die durch Festlegen des *bimpersonate* -Flags auf true erstellt wurden, automatisch wiederherzustellen.

##  <a name="opennamedpipeclienttoken"></a>CAccessToken:: opennamedpipeclienttoken

Aufrufen Sie diese Methode aus einem Server, der Anforderungen über einen Named Pipe annimmt, um `CAccessToken` das mit dem Zugriffs Token vom Client zu initialisieren.

```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parameter

*hPipe*<br/>
Handle für einen Named Pipe.

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bimpersonate*<br/>
TRUE gibt an, dass der aktuelle Thread die Identität des aufrufenden Pipe-Clients annimmt, wenn dieser Aufruf erfolgreich abgeschlossen wird. Wenn der Wert false ist, wird das Zugriffs Token geöffnet, aber der Thread besitzt kein Identitätswechsel Token, wenn dieser Vorgang abgeschlossen wird.

*bOpenAsSelf*<br/>
Gibt an, ob die Zugriffs Überprüfung für den Sicherheitskontext des Threads durchgeführt werden soll, der die [getthreadtoken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) -Methode aufrufen, oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter false ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread ausgeführt. Wenn der Thread die Identität eines Clients annimmt, kann dieser Sicherheitskontext der eines Client Prozesses sein. Wenn dieser Parameter true ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread durchgeführt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die [cautorevertimpersonations-Klasse](../../atl/reference/cautorevertimpersonation-class.md) kann verwendet werden, um Identitätswechsel-Zugriffs Token, die durch Festlegen des *bimpersonate* -Flags auf true erstellt wurden, automatisch wiederherzustellen.

##  <a name="openrpcclienttoken"></a>CAccessToken:: openrpcclienttoken

Aufrufen Sie diese Methode aus einem Server, der einen Aufruf von einem RPC-Client verarbeitet, `CAccessToken` um das mit dem Zugriffs Token vom Client zu initialisieren.

```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```

### <a name="parameters"></a>Parameter

*Bindinghandle*<br/>
Bindungs Handle auf dem Server, das eine Bindung an einen Client darstellt.

*dwDesiredAccess*<br/>
Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.

*bimpersonate*<br/>
TRUE gibt an, dass der aktuelle Thread die Identität des aufrufenden RPC-Clients annimmt, wenn dieser Aufruf erfolgreich abgeschlossen wird. Wenn der Wert false ist, wird das Zugriffs Token geöffnet, aber der Thread besitzt kein Identitätswechsel Token, wenn dieser Vorgang abgeschlossen wird.

*bOpenAsSelf*<br/>
Gibt an, ob die Zugriffs Überprüfung für den Sicherheitskontext des Threads durchgeführt werden soll, der die [getthreadtoken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) -Methode aufrufen, oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter false ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread ausgeführt. Wenn der Thread die Identität eines Clients annimmt, kann dieser Sicherheitskontext der eines Client Prozesses sein. Wenn dieser Parameter true ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread durchgeführt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die [cautorevertimpersonations-Klasse](../../atl/reference/cautorevertimpersonation-class.md) kann verwendet werden, um Identitätswechsel-Zugriffs Token, die durch Festlegen des *bimpersonate* -Flags auf true erstellt wurden, automatisch wiederherzustellen.

##  <a name="openthreadtoken"></a>CAccessToken:: openthumlestoken

Ruft diese Methode auf, um die Identitätswechsel Ebene festzulegen, und `CAccessToken` initialisiert dann mit dem Token aus dem angegebenen Thread.

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

*bimpersonate*<br/>
TRUE gibt an, dass der Thread auf der angeforderten Ebene des Identitäts Wechsels bleibt, nachdem diese Methode abgeschlossen wurde. Wenn der Wert false ist, wird der Thread auf seine ursprüngliche Identitätswechsel Ebene zurückgesetzt.

*bOpenAsSelf*<br/>
Gibt an, ob die Zugriffs Überprüfung für den Sicherheitskontext des Threads durchgeführt werden soll, der die [getthreadtoken](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getcurrentthread) -Methode aufrufen, oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.

Wenn dieser Parameter false ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread ausgeführt. Wenn der Thread die Identität eines Clients annimmt, kann dieser Sicherheitskontext der eines Client Prozesses sein. Wenn dieser Parameter true ist, wird die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread durchgeführt.

*sil*<br/>
Gibt einen [SECURITY_IMPERSONATION_LEVEL](/windows/win32/api/winnt/ne-winnt-security_impersonation_level) -enumerierten Typ an, der die Identitätswechsel Ebene des Tokens bereitstellt.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

`OpenThreadToken`ähnelt [CAccessToken:: getthreadtoken](#getthreadtoken), legt jedoch die Identitätswechsel Ebene vor dem Initialisieren der `CAccessToken` aus dem Zugriffs Token des Threads fest.

Die [cautorevertimpersonations-Klasse](../../atl/reference/cautorevertimpersonation-class.md) kann verwendet werden, um Identitätswechsel-Zugriffs Token, die durch Festlegen des *bimpersonate* -Flags auf true erstellt wurden, automatisch wiederherzustellen.

##  <a name="privilegecheck"></a>CAccessToken::P rivilegecheck

Ruft diese Methode auf, um zu bestimmen, ob ein angegebener Berechtigungs Satz im `CAccessToken` Objekt aktiviert ist.

```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
    bool* pbResult) const throw();
```

### <a name="parameters"></a>Parameter

*RequiredPrivileges*<br/>
Zeiger auf eine [PRIVILEGE_SET](/windows/win32/api/winnt/ns-winnt-privilege_set) -Struktur.

*pbResult*<br/>
Ein Zeiger auf einen Wert, der von der-Methode festgelegt wird, um anzugeben, ob eine oder `CAccessToken` alle der angegebenen Berechtigungen im-Objekt aktiviert sind.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Wenn `PrivilegeCheck` zurückgibt, `Attributes` wird der Member jeder [LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes) -Struktur auf SE_PRIVILEGE_USED_FOR_ACCESS festgelegt, wenn die entsprechende Berechtigung aktiviert ist. Diese Methode ruft die " [privilegecheck](/windows/win32/api/securitybaseapi/nf-securitybaseapi-privilegecheck) "-Win32-Funktion auf.

##  <a name="revert"></a>CAccessToken:: Revert

Mit dieser Methode können Sie verhindern, dass ein Thread ein Identitätswechsel Token verwendet.

```
bool Revert(HANDLE hThread = NULL) const throw();
```

### <a name="parameters"></a>Parameter

*hThread*<br/>
Handle für den Thread, der aus dem Identitätswechsel wieder hergestellt werden soll. Wenn *hThread* NULL ist, wird der aktuelle Thread angenommen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die Neuversion der Identitätswechsel Token kann automatisch mit der [cautorevertimpersonations-Klasse](../../atl/reference/cautorevertimpersonation-class.md)ausgeführt werden.

##  <a name="setdefaultdacl"></a>CAccessToken:: setdefaultdacl

Mit dieser Methode können Sie die standarddacl des `CAccessToken` Objekts festlegen.

```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```

### <a name="parameters"></a>Parameter

*rDacl*<br/>
Die neuen [CDacl](../../atl/reference/cdacl-class.md) -Standardklassen Informationen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die Standard-DACL ist die DACL, die standardmäßig verwendet wird, wenn neue Objekte mit diesem Zugriffs Token erstellt werden.

##  <a name="setowner"></a>CAccessToken:: seetowner

Mit dieser Methode wird der Besitzer des `CAccessToken` Objekts festgelegt.

```
bool SetOwner(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Das [CSID-Klassen](../../atl/reference/csid-class.md) Objekt, das die Besitzer Informationen enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Der Besitzer ist der Standard Besitzer, der für neu erstellte Objekte verwendet wird, während dieses Zugriffs Token aktiviert ist.

##  <a name="setprimarygroup"></a>CAccessToken:: setprimarygroup

Mit dieser Methode wird die primäre Gruppe des `CAccessToken` -Objekts festgelegt.

```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```

### <a name="parameters"></a>Parameter

*rSid*<br/>
Das [CSID-Klassen](../../atl/reference/csid-class.md) Objekt, das die Informationen zur primären Gruppe enthält.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg TRUE zurück, false bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die primäre Gruppe ist die Standardgruppe für neue Objekte, die erstellt werden, während dieses Zugriffs Token aktiviert ist.

## <a name="see-also"></a>Siehe auch

[Beispiel für ATLSecurity](../../overview/visual-cpp-samples.md)<br/>
[Zugriffs Token](/windows/win32/SecAuthZ/access-tokens)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
