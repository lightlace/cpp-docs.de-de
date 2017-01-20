---
title: "Security Global Functions"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACL object global functions"
  - "security IDs [C++]"
  - "SIDs [C++], modifying SID objects"
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Security Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen bieten Unterstützung für das Ändern von SID\- und ACL\-Objekten.  
  
> [!IMPORTANT]
>  Die Funktionen, die in der folgenden Tabelle aufgeführt sind, können nicht in Anwendungen verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
|||  
|-|-|  
|[AtlGetDacl](../Topic/AtlGetDacl.md)|Rufen Sie diese Funktion, um die Informationen der besitzerverwalteten Zugriffssteuerungsliste \(DACLs\) eines angegebenen Objekts abzurufen.|  
|[AtlSetDacl](../Topic/AtlSetDacl.md)|Rufen Sie diese Funktion, um die Informationen der besitzerverwalteten Zugriffssteuerungsliste \(DACLs\) eines angegebenen Objekts festzulegen.|  
|[AtlGetGroupSid](../Topic/AtlGetGroupSid.md)|Rufen Sie diese Funktion auf, um die Gruppensicherheits\-id \(SID\) eines Objekts abzurufen.|  
|[AtlSetGroupSid](../Topic/AtlSetGroupSid.md)|Rufen Sie diese Funktion auf, um die Gruppensicherheits\-id \(SID\) eines Objekts festzulegen.|  
|[AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md)|Rufen Sie diese Funktion auf, um die Besitzerssicherheits\-id \(SID\) eines Objekts abzurufen.|  
|[AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md)|Rufen Sie diese Funktion auf, um die Besitzerssicherheits\-id \(SID\) eines Objekts festzulegen.|  
|[AtlGetSacl](../Topic/AtlGetSacl.md)|Rufen Sie diese Funktion, um die Informationen der Systemzugriffssteuerungsliste \(SACL\) eines angegebenen Objekts abzurufen.|  
|[AtlSetSacl](../Topic/AtlSetSacl.md)|Rufen Sie diese Funktion, um die Informationen der Systemzugriffssteuerungsliste \(SACL\) eines angegebenen Objekts festzulegen.|  
|[AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md)|Rufen Sie diese Funktion auf, um die Sicherheitsbeschreibung eines angegebenen Objekts abzurufen.|  
  
## Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)