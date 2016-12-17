---
title: "CPrivateObjectSecurityDesc Class"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPrivateObjectSecurityDesc"
  - "ATL::CPrivateObjectSecurityDesc"
  - "CPrivateObjectSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPrivateObjectSecurityDesc class"
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CPrivateObjectSecurityDesc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt ein privates Objektschutzdeskriptorobjekt dar.  
  
## Syntax  
  
```  
  
class CPrivateObjectSecurityDesc : public CSecurityDesc  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](../Topic/CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc.md)|Der \-Konstruktor.|  
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](../Topic/CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](../Topic/CPrivateObjectSecurityDesc::ConvertToAutoInherit.md)|Rufen Sie diese Methode auf, um eine Sicherheitsbeschreibung und die Zugriffssteuerungslisten \(ACLs\) in ein Format konvertiert, das automatische Weitergabe von vererbbaren Zugriffssteuerungseinträgen \(ACEs\) unterstützt.|  
|[CPrivateObjectSecurityDesc::Create](../Topic/CPrivateObjectSecurityDesc::Create.md)|Rufen Sie diese Methode auf, um eine selbstrelative Sicherheitsbeschreibung für das private Objekt reserviert und zu initialisieren, das vom aufrufenden Ressourcen\-Manager erstellt wird.|  
|[CPrivateObjectSecurityDesc::Get](../Topic/CPrivateObjectSecurityDesc::Get.md)|Rufen Sie diese Methode auf, um Informationen aus der Sicherheitsbeschreibung eines privaten Objekts abzurufen.|  
|[CPrivateObjectSecurityDesc::Set](../Topic/CPrivateObjectSecurityDesc::Set.md)|Rufen Sie diese Methode auf, um die Sicherheitsbeschreibung eines privaten Objekts zu ändern.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \=](../Topic/CPrivateObjectSecurityDesc::operator%20=.md)|Zuweisungsoperator|  
  
## Hinweise  
 Diese Klasse, die von [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) abgeleitet ist, stellt Methoden zum Erstellen und Verwalten der Sicherheitsbeschreibung eines privaten Objekts bereit.  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc Class](../../atl/reference/csecuritydesc-class.md)