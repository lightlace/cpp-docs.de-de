---
title: Globaler Bezeichner Sicherheitsfunktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9e51fe30b0519514df34f1a77b1e731f51047520
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="security-identifier-global-functions"></a>Globaler Bezeichner Sicherheitsfunktionen
Diese Funktionen geben allgemeine bekannte SID Objekte zurück.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[SIDs::AccountOps](#accountops)|Gibt die DOMAIN_ALIAS_RID_ACCOUNT_OPS-SID zurück.|  
|[SIDs::Admins](#admins)|Gibt die DOMAIN_ALIAS_RID_ADMINS-SID zurück.|  
|[SIDs::AnonymousLogon](#anonymouslogon)|Gibt die SECURITY_ANONYMOUS_LOGON_RID-SID zurück.|  
|[SIDs::AuthenticatedUser](#authenticateduser)|Gibt die SECURITY_AUTHENTICATED_USER_RID-SID zurück.|  
|[SIDs::BackupOps](#backupops)|Gibt die DOMAIN_ALIAS_RID_BACKUP_OPS-SID zurück.|  
|[SIDs::Batch](#batch)|Gibt die SECURITY_BATCH_RID-SID zurück.|  
|[SIDs::CreatorGroup](#creatorgroup)|Gibt die SECURITY_CREATOR_GROUP_RID-SID zurück.|  
|[SIDs::CreatorGroupServer](#creatorgroupserver)|Gibt die SECURITY_CREATOR_GROUP_SERVER_RID-SID zurück.|  
|[SIDs::CreatorOwner](#creatorowner)|Gibt die SECURITY_CREATOR_OWNER_RID-SID zurück.|  
|[SIDs::CreatorOwnerServer](#creatorownerserver)|Gibt die SECURITY_CREATOR_OWNER_SERVER_RID-SID zurück.|  
|[SIDs::Dialup](#dialup)|Gibt die SECURITY_DIALUP_RID-SID zurück.|  
|[SIDs::Guests](#guests)|Gibt die DOMAIN_ALIAS_RID_GUESTS-SID zurück.|  
|[SIDs::Interactive](#interactive)|Gibt die SECURITY_INTERACTIVE_RID-SID zurück.|  
|[SIDs::Local](#local)|Gibt die SECURITY_LOCAL_RID-SID zurück.|  
|[SIDs::Network](#network)|Gibt die SECURITY_NETWORK_RID-SID zurück.|  
|[SIDs::NetworkService](#networkservice)|Gibt die SECURITY_NETWORK_SERVICE_RID-SID zurück.|  
|[SIDs::NULL](#null)|Gibt die SECURITY_NULL_RID-SID zurück.|  
|[SIDs::PreW2KAccess](#prew2kaccess)|Gibt die DOMAIN_ALIAS_RID_PREW2KCOMPACCESS-SID zurück.|  
|[SIDs::PowerUsers](#powerusers)|Gibt die DOMAIN_ALIAS_RID_POWER_USERS-SID zurück.|  
|[SIDs::PrintOps](#printops)|Gibt die DOMAIN_ALIAS_RID_PRINT_OPS-SID zurück.|  
|[SIDs::Proxy](#proxy)|Gibt die SECURITY_PROXY_RID-SID zurück.|  
|[SIDs::RasServers](#rasservers)|Gibt die DOMAIN_ALIAS_RID_RAS_SERVERS-SID zurück.|  
|[SIDs::Replicator](#replicator)|Gibt die DOMAIN_ALIAS_RID_REPLICATOR-SID zurück.|  
|[SIDs::RestrictedCode](#restrictedcode)|Gibt die SECURITY_RESTRICTED_CODE_RID-SID zurück.|  
|[SIDs::Self](#self)|Gibt die SECURITY_PRINCIPAL_SELF_RID-SID zurück.|  
|[SIDs::ServerLogon](#serverlogon)|Gibt die SECURITY_SERVER_LOGON_RID-SID zurück.|  
|[SIDs::Service](#service)|Gibt die SECURITY_SERVICE_RID-SID zurück.|  
|[SIDs::System](#system)|Gibt die SECURITY_LOCAL_SYSTEM_RID-SID zurück.|  
|[SIDs::SystemOps](#systemops)|Gibt die DOMAIN_ALIAS_RID_SYSTEM_OPS-SID zurück.|  
|[SIDs::Terminalserver](#terminalserver)|Gibt die SECURITY_TERMINAL_SERVER_RID-SID zurück.|  
|[SIDs::Users](#users)|Gibt die DOMAIN_ALIAS_RID_USERS-SID zurück.|  
|[SIDs::World](#world)|Gibt die SECURITY_WORLD_RID-SID zurück.|  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlsecurity.h 

##  <a name="accountops"></a>SIDs::AccountOps  
 Gibt die DOMAIN_ALIAS_RID_ACCOUNT_OPS-SID zurück.    
  
```
CSid AccountOps() throw(...);
```  
  
##  <a name="admins"></a>SIDs::Admins  
 Gibt die DOMAIN_ALIAS_RID_ADMINS-SID zurück.  
```
CSid Admins() throw(...);
```  
  
##  <a name="anonymouslogon"></a>SIDs::AnonymousLogon  
 Gibt die SECURITY_ANONYMOUS_LOGON_RID-SID zurück.  
```
CSid AnonymousLogon() throw(...);
```  
  
##  <a name="authenticateduser"></a>SIDs::AuthenticatedUser  
 Gibt die SECURITY_AUTHENTICATED_USER_RID-SID zurück.  
```
CSid AuthenticatedUser() throw(...);
```  
  
##  <a name="backupops"></a>SIDs::BackupOps  
 Gibt die DOMAIN_ALIAS_RID_BACKUP_OPS-SID zurück.  
```
CSid BackupOps() throw(...);
```  
  
##  <a name="batch"></a>SIDs::Batch  
 Gibt die SECURITY_BATCH_RID-SID zurück.  
```
CSid Batch() throw(...);
```  
  
##  <a name="creatorgroup"></a>SIDs::CreatorGroup  
 Gibt die SECURITY_CREATOR_GROUP_RID-SID zurück.  
```
CSid CreatorGroup() throw(...);
```  
  
##  <a name="creatorgroupserver"></a>SIDs::CreatorGroupServer  
 Gibt die SECURITY_CREATOR_GROUP_SERVER_RID-SID zurück.  
```
CSid CreatorGroupServer() throw(...);
```  
  
##  <a name="creatorowner"></a>SIDs::CreatorOwner  
 Gibt die SECURITY_CREATOR_OWNER_RID-SID zurück.  
```
CSid CreatorOwner() throw(...);
```  
  
##  <a name="creatorownerserver"></a>SIDs::CreatorOwnerServer  
 Gibt die SECURITY_CREATOR_OWNER_SERVER_RID-SID zurück.  
```
CSid CreatorOwnerServer() throw(...);
```  
  
##  <a name="dialup"></a>SIDs::Dialup  
 Gibt die SECURITY_DIALUP_RID-SID zurück.  
```
CSid Dialup() throw(...);
```  
  
##  <a name="guests"></a>SIDs::Guests  
 Gibt die DOMAIN_ALIAS_RID_GUESTS-SID zurück.  
```
CSid Guests() throw(...);
```  
  
##  <a name="interactive"></a>SIDs::Interactive  
 Gibt die SECURITY_INTERACTIVE_RID-SID zurück.  
```
CSid Interactive() throw(...);
```  
  
##  <a name="local"></a>SIDs::Local  
 Gibt die SECURITY_LOCAL_RID-SID zurück.  
```
CSid Local() throw(...);
```  
  
##  <a name="network"></a>SIDs::Network  
 Gibt die SECURITY_NETWORK_RID-SID zurück.  
```
CSid Network() throw(...);
```  
  
##  <a name="networkservice"></a>SIDs::NetworkService  
 Gibt die SECURITY_NETWORK_SERVICE_RID-SID zurück.  
```
CSid NetworkService() throw(...);
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie "NetworkService", um Benutzer NT AUTHORITY\NetworkService ein Sicherheitsobjekt CPerfMon lesen können. NetworkService der ATLServer-Code, die DLL unter dem NetworkService-Konto anmelden kann, ein SecurityAttribute hinzugefügt [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] und mehr.  
  
 Bei der Erstellung von benutzerdefinierten Protokoll Leistungsindikatoren mit ATLServer CPerfMon-Klasse in der Perfmon-MMC können die Leistungsindikatoren nicht angezeigt, wenn die Protokolldatei anzeigen, obwohl sie in der Ansicht Echtzeit ordnungsgemäß angezeigt werden. Benutzerdefinierte Leistungsindikatoren CPerfMon nicht die erforderlichen Berechtigungen für den Dienst "Performance-Protokolle und Warnungen" (smlogsvc.exe) ausgeführt haben, auf [!INCLUDE[WinXpFamily](../../atl/reference/includes/winxpfamily_md.md)] (oder höher) Betriebssysteme. Dieser Dienst wird unter dem Konto "NT-Autorität\Netzwerkdienst" ausgeführt.  
  
##  <a name="null"></a>SIDs::NULL  
 Gibt die SECURITY_NULL_RID-SID zurück.  
```
CSid Null() throw(...);
```  
  
##  <a name="prew2kaccess"></a>SIDs::PreW2KAccess  
 Gibt die DOMAIN_ALIAS_RID_PREW2KCOMPACCESS-SID zurück.  
```
CSid PreW2KAccess() throw(...);
```  
  
##  <a name="powerusers"></a>SIDs::PowerUsers  
 Gibt die DOMAIN_ALIAS_RID_POWER_USERS-SID zurück.  
```
CSid PowerUsers() throw(...);
```  
  
##  <a name="printops"></a>SIDs::PrintOps  
 Gibt die DOMAIN_ALIAS_RID_PRINT_OPS-SID zurück.  
```
CSid PrintOps() throw(...);
```  
  
##  <a name="proxy"></a>SIDs::Proxy  
 Gibt die SECURITY_PROXY_RID-SID zurück.  
```
CSid Proxy() throw(...);
```  
  
##  <a name="rasservers"></a>SIDs::RasServers  
 Gibt die DOMAIN_ALIAS_RID_RAS_SERVERS-SID zurück.  
```
CSid RasServers() throw(...);
```  
  
##  <a name="replicator"></a>SIDs::Replicator  
 Gibt die DOMAIN_ALIAS_RID_REPLICATOR-SID zurück.  
```
CSid Replicator() throw(...);
```  
  
##  <a name="restrictedcode"></a>SIDs::RestrictedCode  
 Gibt die SECURITY_RESTRICTED_CODE_RID-SID zurück.  
```
CSid RestrictedCode() throw(...);
```  
  
##  <a name="self"></a>SIDs::Self  
 Gibt die SECURITY_PRINCIPAL_SELF_RID-SID zurück.  
```
CSid Self() throw(...);
```  
  
##  <a name="serverlogon"></a>SIDs::ServerLogon  
 Gibt die SECURITY_SERVER_LOGON_RID-SID zurück.  
```
CSid ServerLogon() throw(...);
```  
  
##  <a name="service"></a>SIDs::Service  
 Gibt die SECURITY_SERVICE_RID-SID zurück.  
```
CSid Service() throw(...);
```  
  
##  <a name="system"></a>SIDs::System  
 Gibt die SECURITY_LOCAL_SYSTEM_RID-SID zurück.  
```
CSid System() throw(...);
```  
  
##  <a name="systemops"></a>SIDs::SystemOps  
 Gibt die DOMAIN_ALIAS_RID_SYSTEM_OPS-SID zurück.  
```
CSid SystemOps() throw(...);
```  
  
##  <a name="terminalserver"></a>SIDs::Terminalserver  
 Gibt die SECURITY_TERMINAL_SERVER_RID-SID zurück.  
```
CSid TerminalServer() throw(...);
```  
  
##  <a name="users"></a>SIDs::Users  
 Gibt die DOMAIN_ALIAS_RID_USERS-SID zurück.  
```
CSid Users() throw(...);
```  
  
##  <a name="world"></a>SIDs::World  
 Gibt die SECURITY_WORLD_RID-SID zurück.  
```
CSid World() throw(...);
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

