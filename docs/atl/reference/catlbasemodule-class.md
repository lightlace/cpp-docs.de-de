---
title: "CAtlBaseModule Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlBaseModule"
  - "ATL.CAtlBaseModule"
  - "CAtlBaseModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlBaseModule class"
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlBaseModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird in jedem ATL\-Projekt instanziiert.  
  
## Syntax  
  
```  
  
   class CAtlBaseModule :  
public _ATL_BASE_MODULE  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](../Topic/CAtlBaseModule::CAtlBaseModule.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](../Topic/CAtlBaseModule::AddResourceInstance.md)|Fügt eine Ressourceninstanz der Liste der gespeicherten Handles hinzu.|  
|[CAtlBaseModule::GetHInstanceAt](../Topic/CAtlBaseModule::GetHInstanceAt.md)|Gibt ein Handle einer angegebenen Ressourceninstanz zurück.|  
|[CAtlBaseModule::GetModuleInstance](../Topic/CAtlBaseModule::GetModuleInstance.md)|Gibt die Modulinstanz von einem `CAtlBaseModule`\-Objekt zurück.|  
|[CAtlBaseModule::GetResourceInstance](../Topic/CAtlBaseModule::GetResourceInstance.md)|Gibt die Ressourceninstanz von einem `CAtlBaseModule`\-Objekt zurück.|  
|[CAtlBaseModule::RemoveResourceInstance](../Topic/CAtlBaseModule::RemoveResourceInstance.md)|Entfernt eine Ressourceninstanz aus der Liste der gespeicherten Handles.|  
|[CAtlBaseModule::SetResourceInstance](../Topic/CAtlBaseModule::SetResourceInstance.md)|Legt die Ressourceninstanz `CAtlBaseModule` eines Objekts fest.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlBaseModule::m\_bInitFailed](../Topic/CAtlBaseModule::m_bInitFailed.md)|Eine Variable, die angibt, ob die Modulinitialisierung fehlgeschlagen ist.|  
  
## Hinweise  
 Eine Instanz von `CAtlBaseModule` benannte \_AtlBaseModule vorhanden ist in jedem ATL\-Projekt und enthielt ein Handle auf die Modulinstanz, ein Handle für das Modul, das Ressourcen enthält \(standardmäßig, eines und gleich sind\) und ein Array von Handles auf Module, die primäre Ressourcen bereitstellen.  auf `CAtlBaseModule` kann von mehreren Threads sicher zugegriffen werden.  
  
 Diese Klasse ersetzt die veraltete [CComModule](../../atl/reference/ccommodule-class.md)\-Klasse, die in früheren Versionen von ATL verwendet wird.  
  
## Vererbungshierarchie  
 [\_ATL\_BASE\_MODULE](../Topic/_ATL_BASE_MODULE.md)  
  
 `CAtlBaseModule`  
  
## Anforderungen  
 **Header:** atlcore.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)