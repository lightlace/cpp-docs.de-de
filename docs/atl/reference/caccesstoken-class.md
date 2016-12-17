---
title: "CAccessToken Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATLSECURITY/CAccessToken"
  - "ATL.CAccessToken"
  - "CAccessToken"
  - "ATL::CAccessToken"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessToken class"
ms.assetid: bb5c5945-56a5-4083-b442-76573cee83ab
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessToken Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für ein Zugriffstoken.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CAccessToken  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAccessToken::~CAccessToken](../Topic/CAccessToken::~CAccessToken.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAccessToken::Attach](../Topic/CAccessToken::Attach.md)|Rufen Sie diese Methode auf, um den Besitz des angegebenen Zugriffstokenhandles zu akzeptieren.|  
|[CAccessToken::CheckTokenMembership](../Topic/CAccessToken::CheckTokenMembership.md)|Rufen Sie diese Methode auf, um zu bestimmen, ob ein angegebenes SID im `CAccessToken`\-Objekt aktiviert ist.|  
|[CAccessToken::CreateImpersonationToken](../Topic/CAccessToken::CreateImpersonationToken.md)|Rufen Sie diese Methode auf, um ein neues Identitätswechselzugriffstoken zu erstellen.|  
|[CAccessToken::CreatePrimaryToken](../Topic/CAccessToken::CreatePrimaryToken.md)|Rufen Sie diese Methode auf, um ein neues primäres Token zu erstellen.|  
|[CAccessToken::CreateProcessAsUser](../Topic/CAccessToken::CreateProcessAsUser.md)|Rufen Sie diese Methode auf, um einen neuen Prozess zu erstellen, der in den Sicherheitskontext des Benutzers ausgeführt, der durch das `CAccessToken`\-Objekt dargestellt wird.|  
|[CAccessToken::CreateRestrictedToken](../Topic/CAccessToken::CreateRestrictedToken.md)|Rufen Sie diese Methode auf, um ein neues, eingeschränktes `CAccessToken`\-Objekt zu erstellen.|  
|[CAccessToken::Detach](../Topic/CAccessToken::Detach.md)|Rufen Sie diese Methode auf, um den Besitz des Zugriffstoken zu widerrufen.|  
|[CAccessToken::DisablePrivilege](../Topic/CAccessToken::DisablePrivilege.md)|Rufen Sie diese Methode auf, um ein rechts im `CAccessToken`\-Objekt zu deaktivieren.|  
|[CAccessToken::DisablePrivileges](../Topic/CAccessToken::DisablePrivileges.md)|Rufen Sie diese Methode auf, um eine oder mehrere Berechtigungen im `CAccessToken`\-Objekt zu deaktivieren.|  
|[CAccessToken::EnablePrivilege](../Topic/CAccessToken::EnablePrivilege.md)|Rufen Sie diese Methode auf, um ein rechts im `CAccessToken`\-Objekt zu aktivieren.|  
|[CAccessToken::EnablePrivileges](../Topic/CAccessToken::EnablePrivileges.md)|Rufen Sie diese Methode auf, um eine oder mehrere Berechtigungen im `CAccessToken`\-Objekt zu aktivieren.|  
|[CAccessToken::GetDefaultDacl](../Topic/CAccessToken::GetDefaultDacl.md)|Rufen Sie diese Methode auf, um den standardmäßigen DACL zurückzugeben `CAccessToken` des Objekts.|  
|[CAccessToken::GetEffectiveToken](../Topic/CAccessToken::GetEffectiveToken.md)|Rufen Sie diese Methode auf, um das `CAccessToken`\-Objekt gleich das Zugriffstoken für den aktuellen Thread aktiv abzurufen.|  
|[CAccessToken::GetGroups](../Topic/CAccessToken::GetGroups.md)|Rufen Sie diese Methode auf, um die Scheingruppen des Objekts `CAccessToken` zurückzugeben.|  
|[CAccessToken::GetHandle](../Topic/CAccessToken::GetHandle.md)|Rufen Sie diese Methode auf, um ein Handle für das Zugriffstoken abzurufen.|  
|[CAccessToken::GetImpersonationLevel](../Topic/CAccessToken::GetImpersonationLevel.md)|Rufen Sie diese Methode auf, um den Identitätswechsel abzurufen, der vom Zugriffstoken einstellen.|  
|[CAccessToken::GetLogonSessionId](../Topic/CAccessToken::GetLogonSessionId.md)|Rufen Sie diese Methode auf, um die Anmeldung Sitzungs\-ID abzurufen, die mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetLogonSid](../Topic/CAccessToken::GetLogonSid.md)|Rufen Sie diese Methode auf, um die Anmeldung SID abzurufen, die mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetOwner](../Topic/CAccessToken::GetOwner.md)|Rufen Sie diese Methode auf, um den Besitzer abzurufen, der mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetPrimaryGroup](../Topic/CAccessToken::GetPrimaryGroup.md)|Rufen Sie diese Methode auf, um die primäre Gruppe abzurufen, die mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetPrivileges](../Topic/CAccessToken::GetPrivileges.md)|Rufen Sie diese Methode auf, um die Berechtigungen zu erhalten, die mit dem `CAccessToken`\-Objekt zugeordnet werden.|  
|[CAccessToken::GetProcessToken](../Topic/CAccessToken::GetProcessToken.md)|Rufen Sie diese Methode auf, um `CAccessToken` mit dem Zugriffstoken zum angegebenen Prozess zu initialisieren.|  
|[CAccessToken::GetProfile](../Topic/CAccessToken::GetProfile.md)|Rufen Sie diese Methode auf, um das Handle abzurufen, das dem Benutzerprofil zeigt, das mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetSource](../Topic/CAccessToken::GetSource.md)|Rufen Sie diese Methode auf, um die Quelle des `CAccessToken`\-Objekts abzurufen.|  
|[CAccessToken::GetStatistics](../Topic/CAccessToken::GetStatistics.md)|Rufen Sie diese Methode auf, um die Informationen abzurufen, die mit dem `CAccessToken`\-Objekt zugeordnet werden.|  
|[CAccessToken::GetTerminalServicesSessionId](../Topic/CAccessToken::GetTerminalServicesSessionId.md)|Rufen Sie diese Methode auf, um die Terminaldienstsitzung ID abzurufen, die mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetThreadToken](../Topic/CAccessToken::GetThreadToken.md)|Rufen Sie diese Methode auf, um `CAccessToken` mit dem Token vom angegebenen Thread zu initialisieren.|  
|[CAccessToken::GetTokenId](../Topic/CAccessToken::GetTokenId.md)|Rufen Sie diese Methode auf, um die Schein\-ID abzurufen, die mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::GetType](../Topic/CAccessToken::GetType.md)|Rufen Sie diese Methode auf, um den Tokentyp `CAccessToken` des Objekts abzurufen.|  
|[CAccessToken::GetUser](../Topic/CAccessToken::GetUser.md)|Rufen Sie diese Methode auf, um den Benutzer zu identifizieren, der mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::HKeyCurrentUser](../Topic/CAccessToken::HKeyCurrentUser.md)|Rufen Sie diese Methode auf, um das Handle abzurufen, das dem Benutzerprofil zeigt, das mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::Impersonate](../Topic/CAccessToken::Impersonate.md)|Rufen Sie diese Methode auf, um einen Identitätswechsel `CAccessToken` zu einem zuweisen.|  
|[CAccessToken::ImpersonateLoggedOnUser](../Topic/CAccessToken::ImpersonateLoggedOnUser.md)|Rufen Sie diese Methode auf, um den aufrufenden Thread zu ermöglichen, den Sicherheitskontext eines angemeldeten Benutzers imitieren.|  
|[CAccessToken::IsTokenRestricted](../Topic/CAccessToken::IsTokenRestricted.md)|Rufen Sie diese Methode auf, um zu testen, wenn das Objekt `CAccessToken` eine Liste eingeschränkten SID enthält.|  
|[CAccessToken::LoadUserProfile](../Topic/CAccessToken::LoadUserProfile.md)|Rufen Sie diese Methode auf, um das Benutzerprofil zu laden, das mit dem `CAccessToken`\-Objekt zugeordnet ist.|  
|[CAccessToken::LogonUser](../Topic/CAccessToken::LogonUser.md)|Rufen Sie diese Methode auf, um eine Sitzung Anmeldung für den Benutzer zu erstellen, der mit den angegebenen Anmeldeinformationen zugeordnet ist.|  
|[CAccessToken::OpenCOMClientToken](../Topic/CAccessToken::OpenCOMClientToken.md)|Rufen Sie diese Methode aus einem COM\-Server auf, der einen Aufruf von einem Client behandelt, um `CAccessToken` mit dem Zugriffstoken vom COM\-Clients zu initialisieren.|  
|[CAccessToken::OpenNamedPipeClientToken](../Topic/CAccessToken::OpenNamedPipeClientToken.md)|Rufen Sie diese Methode aus einem Server, der auf Anforderungen über eine Pipe akzeptiert, `CAccessToken` mit dem Zugriffstoken vom Client zu initialisieren.|  
|[CAccessToken::OpenRPCClientToken](../Topic/CAccessToken::OpenRPCClientToken.md)|Rufen Sie diese Methode aus einem Server, der auf einen Aufruf von einem RPC\-Clienten behandelt, um `CAccessToken` mit dem Zugriffstoken vom Client zu initialisieren.|  
|[CAccessToken::OpenThreadToken](../Topic/CAccessToken::OpenThreadToken.md)|Rufen Sie diese Methode auf, um die Identitätswechselebene festzulegen und `CAccessToken` mit dem Token vom angegebenen Thread dann zu initialisieren.|  
|[CAccessToken::PrivilegeCheck](../Topic/CAccessToken::PrivilegeCheck.md)|Rufen Sie diese Methode auf, um zu ermitteln, ob ein bestimmter Satz von Berechtigungen im **CAccessToken** \-Objekt aktiviert werden.|  
|[CAccessToken::Revert](../Topic/CAccessToken::Revert.md)|Rufen Sie diese Methode auf, um einen Thread zu beenden, der ein Identitätstoken verwendet.|  
|[CAccessToken::SetDefaultDacl](../Topic/CAccessToken::SetDefaultDacl.md)|Rufen Sie diese Methode auf, um den standardmäßigen DACL des `CAccessToken`\-Objekts festzulegen.|  
|[CAccessToken::SetOwner](../Topic/CAccessToken::SetOwner.md)|Rufen Sie diese Methode auf, um den Besitzer des `CAccessToken`\-Objekts festzulegen.|  
|[CAccessToken::SetPrimaryGroup](../Topic/CAccessToken::SetPrimaryGroup.md)|Rufen Sie diese Methode auf, um die primäre Gruppe des `CAccessToken`\-Objekts festzulegen.|  
  
## Hinweise  
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und wird zu jedem Benutzer zugeordnet, der auf ein Windows NT\- oder Windows 2000system protokolliert wird.  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [ATLSecurity\-Beispiel](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)