---
title: "CSecurityDesc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSecurityDesc"
  - "ATL.CSecurityDesc"
  - "CSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityDesc class"
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CSecurityDesc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse ist ein Wrapper für die **SECURITY\_DESCRIPTOR**\-Struktur.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CSecurityDesc  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](../Topic/CSecurityDesc::CSecurityDesc.md)|Der \-Konstruktor.|  
|[CSecurityDesc::~CSecurityDesc](../Topic/CSecurityDesc::~CSecurityDesc.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSecurityDesc::FromString](../Topic/CSecurityDesc::FromString.md)|Konvertiert eine Zeichenkettenformatsicherheitsbeschreibung in eine gültige, funktionale Sicherheitsbeschreibung.|  
|[CSecurityDesc::GetControl](../Topic/CSecurityDesc::GetControl.md)|Ruft Steuerelementinformationen aus der Sicherheitsbeschreibung ab.|  
|[CSecurityDesc::GetDacl](../Topic/CSecurityDesc::GetDacl.md)|Ruft Informationen der besitzerverwalteten Zugriffssteuerungsliste \(DACLs\) aus der Sicherheitsbeschreibung ab.|  
|[CSecurityDesc::GetGroup](../Topic/CSecurityDesc::GetGroup.md)|Ruft die primären Gruppeninformationen aus der Sicherheitsbeschreibung ab.|  
|[CSecurityDesc::GetOwner](../Topic/CSecurityDesc::GetOwner.md)|Ruft informaton Besitzer von der Sicherheitsbeschreibung ab.|  
|[CSecurityDesc::GetPSECURITY\_DESCRIPTOR](../Topic/CSecurityDesc::GetPSECURITY_DESCRIPTOR.md)|Gibt einen Zeiger auf die **SECURITY\_DESCRIPTOR**\-Struktur zurück.|  
|[CSecurityDesc::GetSacl](../Topic/CSecurityDesc::GetSacl.md)|Ruft Informationen der Systemzugriffssteuerungsliste \(SACL\) aus der Sicherheitsbeschreibung ab.|  
|[CSecurityDesc::IsDaclAutoInherited](../Topic/CSecurityDesc::IsDaclAutoInherited.md)|Bestimmt, ob das DACL konfiguriert wird, um die automatische Weitergabe zu unterstützen.|  
|[CSecurityDesc::IsDaclDefaulted](../Topic/CSecurityDesc::IsDaclDefaulted.md)|Bestimmt, ob die Sicherheitsbeschreibung mit einem Standard DACL konfiguriert ist.|  
|[CSecurityDesc::IsDaclPresent](../Topic/CSecurityDesc::IsDaclPresent.md)|Bestimmt, ob die Sicherheitsbeschreibung DACL enthält.|  
|[CSecurityDesc::IsDaclProtected](../Topic/CSecurityDesc::IsDaclProtected.md)|Bestimmt, ob das DACL konfiguriert wird, um Änderungen zu verhindern.|  
|[CSecurityDesc::IsGroupDefaulted](../Topic/CSecurityDesc::IsGroupDefaulted.md)|Bestimmt, ob die Gruppensicherheits\-id der Sicherheitsbeschreibung \(SID\) standardmäßig festgelegt wurde.|  
|[CSecurityDesc::IsOwnerDefaulted](../Topic/CSecurityDesc::IsOwnerDefaulted.md)|Bestimmt, ob der Besitzer SID der Sicherheitsbeschreibung standardmäßig festgelegt wurde.|  
|[CSecurityDesc::IsSaclAutoInherited](../Topic/CSecurityDesc::IsSaclAutoInherited.md)|Bestimmt, ob das SACLs konfiguriert wird, um die automatische Weitergabe zu unterstützen.|  
|[CSecurityDesc::IsSaclDefaulted](../Topic/CSecurityDesc::IsSaclDefaulted.md)|Bestimmt, ob die Sicherheitsbeschreibung mit einem Standard SACLs konfiguriert ist.|  
|[CSecurityDesc::IsSaclPresent](../Topic/CSecurityDesc::IsSaclPresent.md)|Bestimmt, ob die Sicherheitsbeschreibung ein SACLs enthält.|  
|[CSecurityDesc::IsSaclProtected](../Topic/CSecurityDesc::IsSaclProtected.md)|Bestimmt, ob das SACLs konfiguriert wird, um Änderungen zu verhindern.|  
|[CSecurityDesc::IsSelfRelative](../Topic/CSecurityDesc::IsSelfRelative.md)|Bestimmt, ob die Sicherheitsbeschreibung im selbstrelativen Format ist.|  
|[CSecurityDesc::MakeAbsolute](../Topic/CSecurityDesc::MakeAbsolute.md)|Rufen Sie diese Methode auf, um die Sicherheitsbeschreibung auf die absolute Format zu konvertieren.|  
|[CSecurityDesc::MakeSelfRelative](../Topic/CSecurityDesc::MakeSelfRelative.md)|Rufen Sie diese Methode auf, um die Sicherheitsbeschreibung zum selbstrelativen Format zu konvertieren.|  
|[CSecurityDesc::SetControl](../Topic/CSecurityDesc::SetControl.md)|Legt die Steuerbite einer Sicherheitsbeschreibung fest.|  
|[CSecurityDesc::SetDacl](../Topic/CSecurityDesc::SetDacl.md)|Enthält Informationen in einem DACL fest.  Wenn DACL bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.|  
|[CSecurityDesc::SetGroup](../Topic/CSecurityDesc::SetGroup.md)|Legt die primären Gruppeninformationen einer absoluten Formatsicherheitsbeschreibung fest und bereits ersetzt jedes primäre der Gruppeninformationen vorhanden.|  
|[CSecurityDesc::SetOwner](../Topic/CSecurityDesc::SetOwner.md)|Legt die Besitzersinformationen einer absoluten Formatsicherheitsbeschreibung fest und bereits ersetzt jedes der Besitzersinformationen vorhanden.|  
|[CSecurityDesc::SetSacl](../Topic/CSecurityDesc::SetSacl.md)|Enthält Informationen in einem SACLs fest.  Wenn ein SACLs bereits in der Sicherheitsbeschreibung vorhanden ist, wird es ersetzt.|  
|[CSecurityDesc::ToString](../Topic/CSecurityDesc::ToString.md)|Konvertiert eine Sicherheitsbeschreibung zu einem Zeichenfolgenformat.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSecurityDesc::operator const SECURITY\_DESCRIPTOR \*](../Topic/CSecurityDesc::operator%20const%20SECURITY_DESCRIPTOR%20*.md)|Gibt einen Zeiger auf die **SECURITY\_DESCRIPTOR**\-Struktur zurück.|  
|[CSecurityDesc::operator \=](../Topic/CSecurityDesc::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 Die **SECURITY\_DESCRIPTOR**\-Struktur enthält die Sicherheitsinformationen, die einem Objekt zugeordnet werden.  Anwendungen verwenden diese Struktur, um Sicherheitsstatus eines Objekts festzulegen und abzufragen.  Siehe auch [AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md).  
  
 Anwendungen müssen die **SECURITY\_DESCRIPTOR**\-Struktur nicht direkt ändern, und sollten die bereitgestellten Klassenmethoden stattdessen verwenden.  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [Beispiel für die Sicherheit](../../top/visual-cpp-samples.md)   
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)