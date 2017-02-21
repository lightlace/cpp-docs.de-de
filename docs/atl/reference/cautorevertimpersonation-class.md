---
title: "CAutoRevertImpersonation Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoRevertImpersonation"
  - "CAutoRevertImpersonation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoRevertImpersonation class"
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CAutoRevertImpersonation Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt [CAccessToken](../../atl/reference/caccesstoken-class.md)\-Objekte einem nonimpersonating Zustand zurück, wenn sie den Gültigkeitsbereich verlässt.  
  
## Syntax  
  
```  
  
class CAutoRevertImpersonation  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::CAutoRevertImpersonation.md)|Erstellt ein Objekt `CAutoRevertImpersonation`|  
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](../Topic/CAutoRevertImpersonation::~CAutoRevertImpersonation.md)|Zerstört das Objekt und stellt Zugriffstokenidentitätswechsel wiederher.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](../Topic/CAutoRevertImpersonation::Attach.md)|Automatisiert die Identitätswechselumkehrung eines Zugriffstoken.|  
|[CAutoRevertImpersonation::Detach](../Topic/CAutoRevertImpersonation::Detach.md)|Bricht die automatische Identitätswechselumkehrung ab.|  
|[CAutoRevertImpersonation::GetAccessToken](../Topic/CAutoRevertImpersonation::GetAccessToken.md)|Ruft den Zugriffstokenstrom ab, der diesem Objekt zugeordnet ist.|  
  
## Hinweise  
 [Zugriffstoken](http://msdn.microsoft.com/library/windows/desktop/aa374909) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und wird zu jedem Benutzer zugeordnet, der auf ein Windows NT\- oder Windows 2000system protokolliert wird.  Diese Zugriffstoken können mit der `CAccessToken`\-Klasse dargestellt werden.  
  
 Manchmal ist es notwendig, Zugriffstoken imitieren.  Diese Klasse wird als halber bereitgestellt, allerdings wird nicht den Identitätswechsel von Zugriffstoken aus; sie wird nur die automatische Umkehrung zu einem nonimpersonated Zustand aus.  Dies ist, da Scheinzugriffsidentitätswechsel ausgeführt werden kann mehrere verschiedene Möglichkeiten.  
  
 Eine Einführung in Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](http://msdn.microsoft.com/library/windows/desktop/aa374860) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atlsecurity.h  
  
## Siehe auch  
 [ATLSecurity\-Beispiel](../../top/visual-cpp-samples.md)   
 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Class Overview](../../atl/atl-class-overview.md)