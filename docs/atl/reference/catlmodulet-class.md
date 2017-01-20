---
title: "CAtlModuleT Class"
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
  - "ATL::CAtlModuleT<T>"
  - "ATL.CAtlModuleT"
  - "ATL.CAtlModuleT<T>"
  - "ATL::CAtlModuleT"
  - "CAtlModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModuleT class"
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein ATL\-Modul.  
  
## Syntax  
  
```  
  
      template <  
   class T   
>   
class ATL_NO_VTABLE CAtlModuleT :  
   public CAtlModule  
```  
  
#### Parameter  
 `T`  
 Die Klasse wird von abgeleitet `CAtlModuleT`.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](../Topic/CAtlModuleT::CAtlModuleT.md)|Der \-Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](../Topic/CAtlModuleT::InitLibId.md)|Initialisiert den Datenmember, der der GUID des aktuellen Moduls enthält.|  
|[CAtlModuleT::RegisterAppId](../Topic/CAtlModuleT::RegisterAppId.md)|Fügt die EXE\-Datei der Registrierung hinzu.|  
|[CAtlModuleT::RegisterServer](../Topic/CAtlModuleT::RegisterServer.md)|Fügt den Dienst der Registrierung hinzu.|  
|[CAtlModuleT::UnregisterAppId](../Topic/CAtlModuleT::UnregisterAppId.md)|Entfernt die EXE\-Datei aus der Registrierung.|  
|[CAtlModuleT::UnregisterServer](../Topic/CAtlModuleT::UnregisterServer.md)|Entfernt den Dienst aus der Registrierung.|  
|[CAtlModuleT::UpdateRegistryAppId](../Topic/CAtlModuleT::UpdateRegistryAppId.md)|Aktualisiert die EXE\-Informationen in der Registrierung.|  
  
## Hinweise  
 `CAtlModuleT`, abgeleitet von [CAtlModule](../../atl/reference/catlmodule-class.md), implementiert eine ausführbare Datei \(.exe\) oder ein Modul des Diensts \(EXE\) ATL.  Ein ausführbares Modul ist ein lokaler, prozessexterner Server, während ein Testmodul eine Windows\-Anwendung ist, die im Hintergrund ausgeführt wird, wenn Windows beginnt.  
  
 `CAtlModuleT` bietet Unterstützung für das Initialisieren, Registrieren und das Registrierung aufheben des Moduls.  
  
## Vererbungshierarchie  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CAtlModule Class](../../atl/reference/catlmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)