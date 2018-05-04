---
title: CAccessToken Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAccessToken class
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 407652cc5a5e300a2e5eb9d6a5a07dd29209ffef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="caccesstoken-class"></a>CAccessToken-Klasse
Diese Klasse ist ein Wrapper für ein Zugriffstoken an.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
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
|[CAccessToken::Attach](#attach)|Rufen Sie diese Methode, um der angegebenen Access-Tokenhandle Besitz zu nehmen.|  
|[CAccessToken::CheckTokenMembership](#checktokenmembership)|Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene SID, in aktiviert ist der `CAccessToken` Objekt.|  
|[CAccessToken::CreateImpersonationToken](#createimpersonationtoken)|Rufen Sie diese Methode, um ein neues Zugriffstoken für den Identitätswechsel zu erstellen.|  
|[CAccessToken::CreatePrimaryToken](#createprimarytoken)|Rufen Sie diese Methode zum Erstellen eines neuen primären Tokens.|  
|[CAccessToken::CreateProcessAsUser](#createprocessasuser)|Rufen Sie diese Methode zum Erstellen eines neuen Prozesses ausgeführt wird, im Sicherheitskontext des Benutzers, dargestellt durch die `CAccessToken` Objekt.|  
|[CAccessToken::CreateRestrictedToken](#createrestrictedtoken)|Rufen Sie diese Methode zum Erstellen einer neuen, eingeschränkten `CAccessToken` Objekt.|  
|[CAccessToken::Detach](#detach)|Rufen Sie diese Methode, um den Besitz des Zugriffstokens zu widerrufen.|  
|[CAccessToken::DisablePrivilege](#disableprivilege)|Rufen Sie diese Methode zum Deaktivieren einer Berechtigung in den `CAccessToken` Objekt.|  
|[CAccessToken::DisablePrivileges](#disableprivileges)|Rufen Sie diese Methode, um eine oder mehrere Berechtigungen in Deaktivieren der `CAccessToken` Objekt.|  
|[CAccessToken::EnablePrivilege](#enableprivilege)|Rufen Sie diese Methode zum Aktivieren einer Berechtigung in den `CAccessToken` Objekt.|  
|[CAccessToken::EnablePrivileges](#enableprivileges)|Rufen Sie diese Methode, um eine oder mehrere Berechtigungen in ermöglichen die `CAccessToken` Objekt.|  
|[CAccessToken::GetDefaultDacl](#getdefaultdacl)|Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` des Objekts Standard DACL.|  
|[CAccessToken::GetEffectiveToken](#geteffectivetoken)|Rufen Sie diese Methode zum Abrufen der `CAccessToken` -Objekt, in das Zugriffstoken für den aktuellen Thread praktisch identisch.|  
|[CAccessToken::GetGroups](#getgroups)|Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` token Objektgruppen.|  
|[CAccessToken::GetHandle](#gethandle)|Rufen Sie diese Methode, um ein Handle für das Zugriffstoken abzurufen.|  
|[CAccessToken::GetImpersonationLevel](#getimpersonationlevel)|Rufen Sie diese Methode, um die Ebene des Identitätswechsels aus dem Zugriffstoken zu erhalten.|  
|[CAccessToken::GetLogonSessionId](#getlogonsessionid)|Rufen Sie diese Methode, um die zugeordnete Anmeldung Sitzungs-ID Abrufen der `CAccessToken` Objekt.|  
|[CAccessToken::GetLogonSid](#getlogonsid)|Rufen Sie diese Methode, um die Anmelde-SID zugeordnet erhalten die `CAccessToken` Objekt.|  
|[CAccessToken::GetOwner](#getowner)|Rufen Sie diese Methode zum Abrufen der Benutzer mit der `CAccessToken` Objekt.|  
|[CAccessToken::GetPrimaryGroup](#getprimarygroup)|Rufen Sie diese Methode zum Abrufen der zugeordnete primären Gruppe der `CAccessToken` Objekt.|  
|[CAccessToken::GetPrivileges](#getprivileges)|Rufen Sie diese Methode, um die Berechtigungen des entsprechenden erhalten die `CAccessToken` Objekt.|  
|[CAccessToken::GetProcessToken](#getprocesstoken)|Rufen Sie diese Methode auf, um `CAccessToken` mit dem Zugriffstoken aus einem Prozess zu initialisieren.|  
|[CAccessToken::GetProfile](#getprofile)|Rufen Sie diese Methode, um das Handle auf das zugeordnete Benutzerprofil erhalten die `CAccessToken` Objekt.|  
|[CAccessToken::GetSource](#getsource)|Rufen Sie diese Methode, um die Quelle der erhalten die `CAccessToken` Objekt.|  
|[CAccessToken::GetStatistics](#getstatistics)|Rufen Sie diese Methode zum Abrufen von Informationen über die `CAccessToken` Objekt.|  
|[CAccessToken::GetTerminalServicesSessionId](#getterminalservicessessionid)|Rufen Sie diese Methode, um die Terminal Services-Sitzungs-ID zugeordneten erhalten die `CAccessToken` Objekt.|  
|[CAccessToken::GetThreadToken](#getthreadtoken)|Rufen Sie diese Methode zum Initialisieren der `CAccessToken` mit dem Token aus den angegebenen Thread.|  
|[CAccessToken::GetTokenId](#gettokenid)|Rufen Sie diese Methode zum Abrufen der Token-ID zugeordneten der `CAccessToken` Objekt.|  
|[CAccessToken::GetType](#gettype)|Rufen Sie diese Methode zum Abrufen des Tokentyp der der `CAccessToken` Objekt.|  
|[CAccessToken::GetUser](#getuser)|Rufen Sie diese Methode, um den zugeordneten Benutzer identifizieren die `CAccessToken` Objekt.|  
|[CAccessToken::HKeyCurrentUser](#hkeycurrentuser)|Rufen Sie diese Methode, um das Handle auf das zugeordnete Benutzerprofil erhalten die `CAccessToken` Objekt.|  
|[CAccessToken::Impersonate](#impersonate)|Rufen Sie diese Methode, um einen Identitätswechsel zuweisen `CAccessToken` an einen Thread.|  
|[CAccessToken::ImpersonateLoggedOnUser](#impersonateloggedonuser)|Rufen Sie diese Methode, um den aufrufenden Thread für den Sicherheitskontext des angemeldeten Benutzer Identitätswechsel zu ermöglichen.|  
|[CAccessToken::IsTokenRestricted](#istokenrestricted)|Rufen Sie diese Methode getestet, ob die `CAccessToken` Objekt enthält eine Liste der eingeschränkten SIDs.|  
|[CAccessToken::LoadUserProfile](#loaduserprofile)|Rufen Sie diese Methode, um das zugeordnete Benutzerprofil laden die `CAccessToken` Objekt.|  
|[CAccessToken::LogonUser](#logonuser)|Rufen Sie diese Methode zum Erstellen einer Sitzungs für den Benutzer, die die angegebenen Anmeldeinformationen zugeordnet.|  
|[CAccessToken::OpenCOMClientToken](#opencomclienttoken)|Rufen Sie diese Methode aus, in einen COM-Server, die Behandlung von einem Aufruf von einem Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus der COM-Client.|  
|[CAccessToken::OpenNamedPipeClientToken](#opennamedpipeclienttoken)|Rufen Sie diese Methode aus innerhalb eines Servers übernehmen Anforderungen über eine named Pipe zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.|  
|[CAccessToken::OpenRPCClientToken](#openrpcclienttoken)|Rufen Sie diese Methode aus innerhalb eines Servers, die Behandlung von einen Aufruf aus einem RPC-Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.|  
|[CAccessToken::OpenThreadToken](#openthreadtoken)|Rufen Sie diese Methode, um die Ebene des Identitätswechsels legen und initialisieren Sie dann die `CAccessToken` mit dem Token aus den angegebenen Thread.|  
|[CAccessToken::PrivilegeCheck](#privilegecheck)|Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene Gruppe von Berechtigungen in aktiviert sind die **CAccessToken** Objekt.|  
|[CAccessToken::Revert](#revert)|Rufen Sie diese Methode, um einen Thread zu beenden, der ein Identitätswechseltoken verwendet wird.|  
|[CAccessToken::SetDefaultDacl](#setdefaultdacl)|Rufen Sie diese Methode zum Festlegen des standardmäßigen DACL den `CAccessToken` Objekt.|  
|[CAccessToken::SetOwner](#setowner)|Rufen Sie diese Methode zum Festlegen des Besitzers der `CAccessToken` Objekt.|  
|[CAccessToken::SetPrimaryGroup](#setprimarygroup)|Rufen Sie diese Methode, um die primäre Gruppe der `CAccessToken` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ein Objekt, das den Sicherheitskontext für einen Prozess oder Thread beschreibt und erhält jeder Benutzer auf einem Windows-Betriebssystem angemeldet ist.  
  
 Eine Einführung in das Zugriffssteuerungsmodell in Windows erhalten finden Sie unter [Access Control](http://msdn.microsoft.com/library/windows/desktop/aa374860) im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h  
  
##  <a name="attach"></a>  CAccessToken::Attach  
 Rufen Sie diese Methode, um der angegebenen Access-Tokenhandle Besitz zu nehmen.  
  
```
void Attach(HANDLE hToken) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *hToken*  
 Ein Handle für das Zugriffstoken.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CAccessToken` Objekt besitzt bereits ein Zugriffstoken.  
  
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
 `rSid`  
 Ein Verweis auf eine [CSid Klasse](../../atl/reference/csid-class.md) Objekt.  
  
 `pbIsMember`  
 Ein Zeiger auf eine Variable, die Ergebnisse der Prüfung empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die `CheckTokenMembership` Methode überprüft das Vorhandensein der SID in der Benutzer und Gruppen-SIDs des Zugriffstokens. Wenn die SID vorhanden ist und das Attribut SE_GROUP_ENABLED *PbIsMember* ist festgelegt auf "true", andernfalls, sie auf "false" festgelegt ist.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pbIsMember` ist kein gültiger Zeiger.  
  
> [!NOTE]
>  Die `CAccessToken` Objekt muss ein Identitätswechseltoken und nicht um ein primäres Token.  
  
##  <a name="createimpersonationtoken"></a>  CAccessToken::CreateImpersonationToken  
 Rufen Sie diese Methode, um ein Zugriffstoken für den Identitätswechsel zu erstellen.  
  
```
bool CreateImpersonationToken(
    CAccessToken* pImp, 
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pImp`  
 Zeiger auf die neue `CAccessToken` Objekt.  
  
 `sil`  
 Gibt eine [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) Enumerationstyps, der die Ebene des Identitätswechsels für das neue Token bereitstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 `CreateImpersonationToken` Aufrufe [nicht dupliziert werden](http://msdn.microsoft.com/library/windows/desktop/aa446616) um ein neues Identitätswechseltoken zu erstellen.  
  
##  <a name="createprimarytoken"></a>  CAccessToken::CreatePrimaryToken  
 Rufen Sie diese Methode zum Erstellen eines neuen primären Tokens.  
  
```
bool CreatePrimaryToken(
    CAccessToken* pPri,
    DWORD dwDesiredAccess = MAXIMUM_ALLOWED,
    const CSecurityAttributes* pTokenAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pPri*  
 Zeiger auf die neue `CAccessToken` Objekt.  
  
 `dwDesiredAccess`  
 Gibt die angeforderte Zugriffsrechte für das neue Token an. Die Standardeinstellung, MAXIMUM_ALLOWED, fordert alle Zugriffsrechte, die für den Aufrufer gültig sind. Finden Sie unter [Zugriffsrechte und Zugriffsmasken](http://msdn.microsoft.com/library/windows/desktop/aa374902) für weitere on Zugriffsrechte.  
  
 *pTokenAttributes*  
 Zeiger auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die eine Sicherheitsbeschreibung für das neue Token gibt an, und bestimmt, ob das Token untergeordneten Prozessen geerbt werden können. Wenn *pTokenAttributes* NULL ist, das Token Ruft eine standardsicherheitsbeschreibung und das Handle kann nicht vererbt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 `CreatePrimaryToken` Aufrufe [DuplicateTokenEx](http://msdn.microsoft.com/library/windows/desktop/aa446617) um ein neues primäres Token zu erstellen.  
  
##  <a name="createprocessasuser"></a>  CAccessToken::CreateProcessAsUser  
 Rufen Sie diese Methode zum Erstellen eines neuen Prozesses ausgeführt wird, im Sicherheitskontext des Benutzers, dargestellt durch die `CAccessToken` Objekt.  
  
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
 *pApplicationName*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die das Modul auszuführende angibt. Dieser Parameter kann nicht NULL sein.  
  
 *pCommandLine*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die auszuführende Befehlszeile an.  
  
 *pProcessInformation*  
 Zeiger auf eine [PROCESS_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/ms684873) -Struktur, die ID-Informationen zu den neuen Prozess empfängt.  
  
 *pStartupInfo*  
 Zeiger auf eine [STARTUPINFO](http://msdn.microsoft.com/library/windows/desktop/ms686331) Struktur, die angibt, wie das Hauptfenster für den neuen Prozess angezeigt werden soll.  
  
 `dwCreationFlags`  
 Gibt zusätzliche Flags, die die Prioritätsklasse und die Erstellung des Prozesses zu steuern. Finden Sie im Win32-Funktion [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) für eine Liste von Flags.  
  
 *bLoadProfile*  
 Wenn "true", das Profil des Benutzers mit geladen wird [LoadUserProfile](http://msdn.microsoft.com/library/windows/desktop/bb762281).  
  
 *pProcessAttributes*  
 Zeiger auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die eine Sicherheitsbeschreibung für den neuen Prozess gibt an, und bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden können. Wenn *pProcessAttributes* NULL ist, der Prozess Ruft eine standardsicherheitsbeschreibung und das Handle kann nicht vererbt werden.  
  
 *pThreadAttributes*  
 Zeiger auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die eine Sicherheitsbeschreibung für den neuen Thread gibt an, und bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden können. Wenn *pThreadAttributes* NULL ist, der Thread Ruft eine standardsicherheitsbeschreibung und das Handle kann nicht vererbt werden.  
  
 *bInherit*  
 Gibt an, ob der neue Prozess Handles von der aufrufende Prozess erbt. Bei "true", wird jede vererbbare geöffnete Handle des aufrufenden Prozesses durch den neuen Prozess geerbt. Geerbte Handles haben die gleichen Wert und Berechtigungen wie die ursprünglichen Handles.  
  
 *pCurrentDirectory*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die das aktuelle Laufwerk und Verzeichnis für den neuen Prozess angibt. Die Zeichenfolge muss es sich um einen vollständigen Pfad befinden, der einen Laufwerksbuchstaben enthält. Wenn dieser Parameter NULL ist, müssen der neue Prozess die gleichen aktuelle Laufwerk und Verzeichnis als der aufrufende Prozess.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 **CreateProcessAsUser** verwendet die `CreateProcessAsUser` Win32-Funktion, um einen neuen Prozess zu erstellen, der im Sicherheitskontext des Benutzers dargestellte ausgeführt wird die `CAccessToken` Objekt. Siehe dazu die Beschreibung der [CreateProcessAsUser](http://msdn.microsoft.com/library/windows/desktop/ms682429) -Funktion für ausführliche Informationen zu den erforderlichen Parameter.  
  
 Für diese Methode erfolgreich ausgeführt werden kann die `CAccessToken` Objekt muss AssignPrimaryToken aufnehmen, (es sei denn, er keinem eingeschränkten Token befindet) und IncreaseQuota Berechtigungen.  
  
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
 *pRestrictedToken*  
 Die neuen, eingeschränkten `CAccessToken` Objekt.  
  
 `SidsToDisable`  
 Ein `CTokenGroups` Objekt, das die SIDs nur zum Ablehnen angibt.  
  
 *SidsToRestrict*  
 Ein `CTokenGroups` Objekt, das den eingeschränkten SIDs angibt.  
  
 `PrivilegesToDelete`  
 Ein `CTokenPrivileges` Objekt, das den zu löschenden Privilegien im eingeschränkten Token angibt. Die Standardeinstellung wird ein leeres Objekt erstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 `CreateRestrictedToken` verwendet die [CreateRestrictedToken](http://msdn.microsoft.com/library/windows/desktop/aa446583) Win32-Funktion zum Erstellen eines neuen `CAccessToken` Objekt, mit Einschränkungen.  
  
> [!IMPORTANT]
>  Bei Verwendung `CreateRestrictedToken`, überprüfen Sie Folgendes: das vorhandene Token gültig ist (und nicht vom Benutzer eingegebenen) und `SidsToDisable` und `PrivilegesToDelete` sind sowohl gültig (und nicht vom Benutzer eingegebenen). Wenn die Methode "false" zurückgibt, verweigern Sie Funktionalität.  
  
##  <a name="detach"></a>  CAccessToken::Detach  
 Rufen Sie diese Methode, um den Besitz des Zugriffstokens zu widerrufen.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Handle für die `CAccessToken` der wurde getrennt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sperrt die `CAccessToken`der Besitz des Zugriffstokens.  
  
##  <a name="disableprivilege"></a>  CAccessToken::DisablePrivilege  
 Rufen Sie diese Methode zum Deaktivieren einer Berechtigung in den `CAccessToken` Objekt.  
  
```
bool DisablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Zeiger auf eine Zeichenfolge, enthält die Berechtigung zum Deaktivieren der `CAccessToken` Objekt.  
  
 `pPreviousState`  
 Zeiger auf ein `CTokenPrivileges` Objekt, das den vorherigen Zustand der Berechtigungen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="disableprivileges"></a>  CAccessToken::DisablePrivileges  
 Rufen Sie diese Methode, um eine oder mehrere Berechtigungen in Deaktivieren der `CAccessToken` Objekt.  
  
```
bool DisablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rPrivileges`  
 Zeiger auf ein Array von Zeichenfolgen, die Rechte zum Deaktivieren der `CAccessToken` Objekt.  
  
 `pPreviousState`  
 Zeiger auf ein `CTokenPrivileges` Objekt, das den vorherigen Zustand der Berechtigungen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="enableprivilege"></a>  CAccessToken::EnablePrivilege  
 Rufen Sie diese Methode zum Aktivieren einer Berechtigung in den `CAccessToken` Objekt.  
  
```
bool EnablePrivilege(
    LPCTSTR pszPrivilege,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pszPrivilege`  
 Zeiger auf eine Zeichenfolge, enthält die Berechtigung zum Aktivieren von in der `CAccessToken` Objekt.  
  
 `pPreviousState`  
 Zeiger auf ein `CTokenPrivileges` Objekt, das den vorherigen Zustand der Berechtigungen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="enableprivileges"></a>  CAccessToken::EnablePrivileges  
 Rufen Sie diese Methode, um eine oder mehrere Berechtigungen in ermöglichen die `CAccessToken` Objekt.  
  
```
bool EnablePrivileges(
    const CAtlArray<LPCTSTR>& rPrivileges,
    CTokenPrivileges* pPreviousState = NULL) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rPrivileges`  
 Zeiger auf ein Array von Zeichenfolgen mit den Berechtigungen zum Aktivieren der `CAccessToken` Objekt.  
  
 `pPreviousState`  
 Zeiger auf ein `CTokenPrivileges` Objekt, das den vorherigen Zustand der Berechtigungen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getdefaultdacl"></a>  CAccessToken::GetDefaultDacl  
 Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` des Objekts Standard DACL.  
  
```
bool GetDefaultDacl(CDacl* pDacl) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pDacl`  
 Zeiger auf die [CDacl Klasse](../../atl/reference/cdacl-class.md) Objekt, das erhält die **CAccessToken** des Objekts Standard DACL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Standard-DACL in der wiederhergestellten, "false" andernfalls befunden hat.  
  
##  <a name="geteffectivetoken"></a>  CAccessToken::GetEffectiveToken  
 Rufen Sie diese Methode zum Abrufen der `CAccessToken` -Objekt, in das Zugriffstoken für den aktuellen Thread praktisch identisch.  
  
```
bool GetEffectiveToken(DWORD dwDesiredAccess) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getgroups"></a>  CAccessToken::GetGroups  
 Rufen Sie diese Methode zum Zurückgeben der `CAccessToken` token Objektgruppen.  
  
```
bool GetGroups(CTokenGroups* pGroups) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pGroups*  
 Zeiger auf die [CTokenGroups Klasse](../../atl/reference/ctokengroups-class.md) Objekt, das die Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
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
 *pImpersonationLevel*  
 Zeiger auf eine [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) Enumerationstyp, der die Ebene Identitätswechselinformationen empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getlogonsessionid"></a>  CAccessToken::GetLogonSessionId  
 Rufen Sie diese Methode, um die zugeordnete Anmeldung Sitzungs-ID Abrufen der `CAccessToken` Objekt.  
  
```
bool GetLogonSessionId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pluid`  
 Zeiger auf eine [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) der erhalten, dass die Anmeldung Sitzungs-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pluid` ist kein gültiger Wert.  
  
##  <a name="getlogonsid"></a>  CAccessToken::GetLogonSid  
 Rufen Sie diese Methode, um die Anmelde-SID zugeordnet erhalten die `CAccessToken` Objekt.  
  
```
bool GetLogonSid(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid Klasse](../../atl/reference/csid-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn *pSid* ist kein gültiger Wert.  
  
##  <a name="getowner"></a>  CAccessToken::GetOwner  
 Rufen Sie diese Methode zum Abrufen der Benutzer mit der `CAccessToken` Objekt.  
  
```
bool GetOwner(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid Klasse](../../atl/reference/csid-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Der Besitzer wird festgelegt, wird standardmäßig auf alle Objekte, die erstellt wurden, während das Zugriffstoken aktiviert ist.  
  
##  <a name="getprimarygroup"></a>  CAccessToken::GetPrimaryGroup  
 Rufen Sie diese Methode zum Abrufen der zugeordnete primären Gruppe der `CAccessToken` Objekt.  
  
```
bool GetPrimaryGroup(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid Klasse](../../atl/reference/csid-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die Gruppe festgelegt ist, wird standardmäßig auf alle Objekte, die erstellt wurden, während das Zugriffstoken aktiviert ist.  
  
##  <a name="getprivileges"></a>  CAccessToken::GetPrivileges  
 Rufen Sie diese Methode, um die Berechtigungen des entsprechenden erhalten die `CAccessToken` Objekt.  
  
```
bool GetPrivileges(CTokenPrivileges* pPrivileges) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pPrivileges`  
 Zeiger auf eine [CTokenPrivileges Klasse](../../atl/reference/ctokenprivileges-class.md) Objekt, das die Berechtigungen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getprocesstoken"></a>  CAccessToken::GetProcessToken  
 Rufen Sie diese Methode auf, um `CAccessToken` mit dem Zugriffstoken aus einem Prozess zu initialisieren.  
  
```
bool GetProcessToken(DWORD dwDesiredAccess, HANDLE hProcess = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
 *hProcess*  
 Handle an den Prozess, dessen Zugriffstoken geöffnet ist. Wenn der Standardwert von `NULL` verwendet wird, wird der aktuelle Prozess verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `true` bei Erfolg bzw. `false` bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die [OpenProcessToken](http://msdn.microsoft.com/library/aa379295\(vs.85\).aspx) Win32-Funktion.  
  
##  <a name="getprofile"></a>  CAccessToken::GetProfile  
 Rufen Sie diese Methode, um das Handle auf das zugeordnete Benutzerprofil erhalten die `CAccessToken` Objekt.  
  
```
HANDLE GetProfile() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle auf das Benutzerprofil oder NULL, wenn kein Profil vorhanden ist.  
  
##  <a name="getsource"></a>  CAccessToken::GetSource  
 Rufen Sie diese Methode, um die Quelle der erhalten die `CAccessToken` Objekt.  
  
```
bool GetSource(TOKEN_SOURCE* pSource) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pSource*  
 Zeiger auf eine [TOKEN_SOURCE](http://msdn.microsoft.com/library/windows/desktop/aa379631) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getstatistics"></a>  CAccessToken::GetStatistics  
 Rufen Sie diese Methode zum Abrufen von Informationen über die `CAccessToken` Objekt.  
  
```
bool GetStatistics(TOKEN_STATISTICS* pStatistics) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pStatistics*  
 Zeiger auf eine [TOKEN_STATISTICS](http://msdn.microsoft.com/library/windows/desktop/aa379632) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getterminalservicessessionid"></a>  CAccessToken::GetTerminalServicesSessionId  
 Rufen Sie diese Methode, um die Terminal Services-Sitzungs-ID zugeordneten erhalten die `CAccessToken` Objekt.  
  
```
bool GetTerminalServicesSessionId(DWORD* pdwSessionId) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *pdwSessionId*  
 Die Terminaldienste-Sitzungs-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="getthreadtoken"></a>  CAccessToken::GetThreadToken  
 Rufen Sie diese Methode zum Initialisieren der `CAccessToken` mit dem Token aus den angegebenen Thread.  
  
```
bool GetThreadToken(
    DWORD dwDesiredAccess,
    HANDLE hThread = NULL,
    bool bOpenAsSelf = true) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
 `hThread`  
 Handle für den Thread, dessen Zugriffstoken geöffnet ist.  
  
 `bOpenAsSelf`  
 Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Threads erfolgen die `GetThreadToken` Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.  
  
 Wenn dieser Parameter auf "false" festgelegt ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread den Identitätswechsel eines Clients ist, kann dieser Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter auf "true" festgelegt ist, erfolgt die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="gettokenid"></a>  CAccessToken::GetTokenId  
 Rufen Sie diese Methode zum Abrufen der Token-ID zugeordneten der `CAccessToken` Objekt.  
  
```
bool GetTokenId(LUID* pluid) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pluid`  
 Zeiger auf eine [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261) erhält die Token-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="gettype"></a>  CAccessToken::GetType  
 Rufen Sie diese Methode zum Abrufen des Tokentyp der der `CAccessToken` Objekt.  
  
```
bool GetType(TOKEN_TYPE* pType) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pType`  
 Der Adresse der [TOKEN_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379633) Variable, die bei Erfolg den Typ des Tokens empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die **TOKEN_TYPE** Enumerationstyp enthält Werte, die ein primäres Token und ein Identitätswechseltoken unterscheiden.  
  
##  <a name="getuser"></a>  CAccessToken::GetUser  
 Rufen Sie diese Methode, um den zugeordneten Benutzer identifizieren die `CAccessToken` Objekt.  
  
```
bool GetUser(CSid* pSid) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `pSid`  
 Zeiger auf eine [CSid Klasse](../../atl/reference/csid-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
##  <a name="hkeycurrentuser"></a>  CAccessToken::HKeyCurrentUser  
 Rufen Sie diese Methode, um das Handle auf das zugeordnete Benutzerprofil erhalten die `CAccessToken` Objekt.  
  
```
HKEY HKeyCurrentUser() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle auf das Benutzerprofil oder NULL, wenn kein Profil vorhanden ist.  
  
##  <a name="impersonate"></a>  CAccessToken::Impersonate  
 Rufen Sie diese Methode, um einen Identitätswechsel zuweisen `CAccessToken` an einen Thread.  
  
```
bool Impersonate(HANDLE hThread = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `hThread`  
 Handle für den Thread für das Zuweisen von Token für den Identitätswechsel zu. Dieses Handle muss mit Zugriffsrechten TOKEN_IMPERSONATE geöffnet worden sein. Wenn `hThread` NULL ist, die Methode bewirkt, dass der Thread nicht mehr verwenden ein Identitätswechseltoken.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `CAccessToken` verfügt nicht über ein gültiger Zeiger auf ein Token.  
  
 Die [CAutoRevertImpersonation Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken automatisch zurückgesetzt.  
  
##  <a name="impersonateloggedonuser"></a>  CAccessToken::ImpersonateLoggedOnUser  
 Rufen Sie diese Methode, um den aufrufenden Thread für den Sicherheitskontext des angemeldeten Benutzer Identitätswechsel zu ermöglichen.  
  
```
bool ImpersonateLoggedOnUser() const throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Wenn ein Aufruf einer Funktion Identitätswechsel aus irgendeinem Grund fehlschlägt, ist kein Clientidentitätswechsel durchgeführt und die Clientanforderung erfolgt im Sicherheitskontext des Prozesses, von dem der Aufruf erfolgte. Wenn der Prozess als ein Konto mit weit reichenden Berechtigungen ausgeführt wird, oder als Mitglied einer administrativen Gruppe der Benutzer möglicherweise Aktionen können ausgeführt würde er andernfalls unzulässig. Der Rückgabewert für diese Funktion sollte daher immer bestätigt werden.  
  
##  <a name="istokenrestricted"></a>  CAccessToken::IsTokenRestricted  
 Rufen Sie diese Methode getestet, ob die `CAccessToken` Objekt enthält eine Liste der eingeschränkten SIDs.  
  
```
bool IsTokenRestricted() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn das Objekt eine Liste enthält der SIDs, False, wenn es keine Beschränkung SIDs gibt einschränken, oder wenn die Methode fehlschlägt.  
  
##  <a name="loaduserprofile"></a>  CAccessToken::LoadUserProfile  
 Rufen Sie diese Methode, um das zugeordnete Benutzerprofil laden die `CAccessToken` Objekt.  
  
```
bool LoadUserProfile() throw(...);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CAccessToken` kein gültiges Token enthält, oder wenn ein bereits Benutzerprofil vorhanden ist.  
  
##  <a name="logonuser"></a>  CAccessToken::LogonUser  
 Rufen Sie diese Methode zum Erstellen einer Sitzungs für den Benutzer, die die angegebenen Anmeldeinformationen zugeordnet.  
  
```
bool LogonUser(
    LPCTSTR pszUserName,
    LPCTSTR pszDomain,
    LPCTSTR pszPassword,
    DWORD dwLogonType = LOGON32_LOGON_INTERACTIVE,
    DWORD dwLogonProvider = LOGON32_PROVIDER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszUserName`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Benutzernamen angibt. Dies ist der Name des Benutzerkontos für die Anmeldung.  
  
 *pszDomain*  
 Zeiger auf eine auf Null endende Zeichenfolge, die gibt den Namen der Domäne oder des Servers, dessen Kontodatenbank enthält, die `pszUserName` Konto.  
  
 `pszPassword`  
 Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Klartext-Kennwort für das Benutzerkonto, das vom angegebenen `pszUserName`.  
  
 *dwLogonType*  
 Gibt den Typ des Anmeldevorgangs ausführen. Finden Sie unter [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) Weitere Details.  
  
 *dwLogonProvider*  
 Gibt den Anmeldungsanbieter. Finden Sie unter [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) Weitere Details.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Der Zugriff token infolge der Anmeldung zugeordnet wird die `CAccessToken`. Für diese Methode erfolgreich ausgeführt werden kann die `CAccessToken` Objekt muss SE_TCB_NAME Privilegien, identifiziert den Inhaber der als Teil der vertrauenswürdige Computer Basis aufnehmen. Finden Sie unter [LogonUser](http://msdn.microsoft.com/library/windows/desktop/aa378184) Weitere Informationen über die erforderlichen Berechtigungen.  
  
##  <a name="opencomclienttoken"></a>  CAccessToken::OpenCOMClientToken  
 Rufen Sie diese Methode aus, in einen COM-Server, die Behandlung von einem Aufruf von einem Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus der COM-Client.  
  
```
bool OpenCOMClientToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
 `bImpersonate`  
 Bei "true", wird der aktuelle Thread die aufrufenden COM-Client Identität annehmen, wenn dieser Aufruf erfolgreich abgeschlossen wurde. Wenn "false", das Zugriffstoken wird geöffnet, aber der Thread hat kein Identitätswechseltoken Abschluss dieses Aufrufs.  
  
 `bOpenAsSelf`  
 Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Threads erfolgen die [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.  
  
 Wenn dieser Parameter auf "false" festgelegt ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread den Identitätswechsel eines Clients ist, kann dieser Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter auf "true" festgelegt ist, erfolgt die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die [CAutoRevertImpersonation Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch zurückgesetzt der `bImpersonate` flag *"true"*.  
  
##  <a name="opennamedpipeclienttoken"></a>  CAccessToken::OpenNamedPipeClientToken  
 Rufen Sie diese Methode aus innerhalb eines Servers übernehmen Anforderungen über eine named Pipe zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.  
  
```
bool OpenNamedPipeClientToken(
    HANDLE hPipe,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *hPipe*  
 Handle für eine named Pipe.  
  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
 `bImpersonate`  
 Bei "true", wird der aktuelle Thread des aufrufenden Clients für die Pipe Identität annehmen, wenn dieser Aufruf erfolgreich abgeschlossen wurde. Wenn "false", das Zugriffstoken wird geöffnet, aber der Thread hat kein Identitätswechseltoken Abschluss dieses Aufrufs.  
  
 `bOpenAsSelf`  
 Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Threads erfolgen die [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.  
  
 Wenn dieser Parameter auf "false" festgelegt ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread den Identitätswechsel eines Clients ist, kann dieser Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter auf "true" festgelegt ist, erfolgt die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die [CAutoRevertImpersonation Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch zurückgesetzt der `bImpersonate` flag *"true"*.  
  
##  <a name="openrpcclienttoken"></a>  CAccessToken::OpenRPCClientToken  
 Rufen Sie diese Methode aus innerhalb eines Servers, die Behandlung von einen Aufruf aus einem RPC-Client zum Initialisieren der `CAccessToken` mit dem Zugriffstoken aus dem Client.  
  
```
bool OpenRPCClientToken(
    RPC_BINDING_HANDLE BindingHandle,
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 *BindingHandle*  
 Handle der Bindung auf dem Server, der eine Bindung an einen Client darstellt.  
  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
 `bImpersonate`  
 Bei "true", wird die der aktuelle Thread des aufrufenden RPC-Clients angenommen, wenn dieser Aufruf erfolgreich ausgeführt wird. Wenn "false", das Zugriffstoken wird geöffnet, aber der Thread hat kein Identitätswechseltoken Abschluss dieses Aufrufs.  
  
 `bOpenAsSelf`  
 Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Threads erfolgen die [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.  
  
 Wenn dieser Parameter auf "false" festgelegt ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread den Identitätswechsel eines Clients ist, kann dieser Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter auf "true" festgelegt ist, erfolgt die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die [CAutoRevertImpersonation Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch zurückgesetzt der `bImpersonate` flag *"true"*.  
  
##  <a name="openthreadtoken"></a>  CAccessToken::OpenThreadToken  
 Rufen Sie diese Methode, um die Ebene des Identitätswechsels legen und initialisieren Sie dann die `CAccessToken` mit dem Token aus den angegebenen Thread.  
  
```
bool OpenThreadToken(
    DWORD dwDesiredAccess,
    bool bImpersonate = false,
    bool bOpenAsSelf = true,
    SECURITY_IMPERSONATION_LEVEL sil = SecurityImpersonation) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDesiredAccess`  
 Gibt eine Zugriffsmaske an, die die angeforderten Zugriffstypen für den Zugriff auf das Zugriffstoken identifiziert. Diese angeforderten Zugriffstypen werden mit der DACL des Tokens verglichen, um zu bestimmen, welche Zugriffe gewährt oder verweigert werden.  
  
 `bImpersonate`  
 Bei "true", wird der Thread nach Abschluss dieses Methode auf die angeforderte Identitätswechselebene belassen. Wenn "false" wird der Thread seine ursprünglichen Identitätswechselebene wiederhergestellt.  
  
 `bOpenAsSelf`  
 Gibt an, ob die zugriffsprüfung für den Sicherheitskontext des aufrufenden Threads erfolgen die [GetThreadToken](http://msdn.microsoft.com/library/windows/desktop/ms683182) Methode oder für den Sicherheitskontext des Prozesses für den aufrufenden Thread.  
  
 Wenn dieser Parameter auf "false" festgelegt ist, wird die zugriffsprüfung mithilfe des Sicherheitskontexts für den aufrufenden Thread ausgeführt. Wenn der Thread den Identitätswechsel eines Clients ist, kann dieser Sicherheitskontext, die von einem Clientprozess sein. Wenn dieser Parameter auf "true" festgelegt ist, erfolgt die zugriffsprüfung unter Verwendung des Sicherheitskontexts des Prozesses für den aufrufenden Thread.  
  
 `sil`  
 Gibt eine [SECURITY_IMPERSONATION_LEVEL](http://msdn.microsoft.com/library/windows/desktop/aa379572) Enumerationstyps, der die Ebene des Identitätswechsels des Tokens bereitstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 `OpenThreadToken` ähnelt dem [CAccessToken::GetThreadToken](#getthreadtoken), sondern legt die Ebene des Identitätswechsels vor dem Initialisieren der `CAccessToken` von Zugriffstoken für den Thread.  
  
 Die [CAutoRevertImpersonation Klasse](../../atl/reference/cautorevertimpersonation-class.md) können verwendet werden, um dessen Identität angenommen wurde Zugriffstoken erstellt, indem automatisch zurückgesetzt der `bImpersonate` flag *"true"*.  
  
##  <a name="privilegecheck"></a>  CAccessToken::PrivilegeCheck  
 Rufen Sie diese Methode, um zu bestimmen, ob eine angegebene Gruppe von Berechtigungen in aktiviert sind die **CAccessToken** Objekt.  
  
```
bool PrivilegeCheck(
    PPRIVILEGE_SET RequiredPrivileges,
     bool* pbResult) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *RequiredPrivileges*  
 Zeiger auf eine [PRIVILEGE_SET](http://msdn.microsoft.com/library/windows/desktop/aa379307) Struktur.  
  
 *pbResult*  
 Zeiger auf einen Wert von der-Methode wird, um anzugeben, ob einige oder alle der angegebenen Berechtigung, in aktiviert sind der `CAccessToken` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `PrivilegeCheck` zurückgibt, die **Attribute** Mitglied aller ["LUID_AND_ATTRIBUTES"](http://msdn.microsoft.com/library/windows/desktop/aa379263) Struktur auf SE_PRIVILEGE_USED_FOR_ACCESS festgelegt ist, wenn die entsprechende Berechtigung aktiviert ist. Diese Methode ruft die [PrivilegeCheck](http://msdn.microsoft.com/library/windows/desktop/aa379304) Win32-Funktion.  
  
##  <a name="revert"></a>  CAccessToken::Revert  
 Rufen Sie diese Methode, um einen Thread aus mit einem Identitätswechseltoken zu beenden.  
  
```
bool Revert(HANDLE hThread = NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hThread`  
 Handle für den Thread, aus der Identitätswechsel zurückzusetzen. Wenn *hThread* NULL ist, der aktuelle Thread wird angenommen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Das Zurücksetzen der Identitätswechseltoken kann automatisch ausgeführt werden, mit der [CAutoRevertImpersonation Klasse](../../atl/reference/cautorevertimpersonation-class.md).  
  
##  <a name="setdefaultdacl"></a>  CAccessToken::SetDefaultDacl  
 Rufen Sie diese Methode zum Festlegen des standardmäßigen DACL den `CAccessToken` Objekt.  
  
```
bool SetDefaultDacl(const CDacl& rDacl) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rDacl`  
 Der neue Standard [CDacl Klasse](../../atl/reference/cdacl-class.md) Informationen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert ist DACL die DACL, die standardmäßig verwendet wird, wenn neue Objekte faktisch mit diesem Zugriffstoken erstellt werden.  
  
##  <a name="setowner"></a>  CAccessToken::SetOwner  
 Rufen Sie diese Methode zum Festlegen des Besitzers der `CAccessToken` Objekt.  
  
```
bool SetOwner(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid Klasse](../../atl/reference/csid-class.md) Objekt, das die Informationen zum Besitzer enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Der Besitzer ist der Standardbesitzer, die verwendet wird, für neue Objekte erstellt, während das Zugriffstoken aktiviert ist.  
  
##  <a name="setprimarygroup"></a>  CAccessToken::SetPrimaryGroup  
 Rufen Sie diese Methode, um die primäre Gruppe der `CAccessToken` Objekt.  
  
```
bool SetPrimaryGroup(const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `rSid`  
 Die [CSid Klasse](../../atl/reference/csid-class.md) Objekt, das die primäre Gruppeninformationen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg true zurück, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Die primäre Gruppe ist die Standardgruppe für neue Objekte erstellt, während das Zugriffstoken aktiviert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [ATLSecurity-Beispiel](../../visual-cpp-samples.md)   
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
