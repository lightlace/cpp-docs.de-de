---
title: "CAtlModule Class"
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
  - "ATL::CAtlModule"
  - "CAtlModule"
  - "ATL.CAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlModule class"
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, die von mehreren ATL\-Modulklassen verwendet werden.  
  
## Syntax  
  
```  
  
   class ATL_NO_VTABLE CAtlModule :  
public _ATL_MODULE  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](../Topic/CAtlModule::CAtlModule.md)|Der \-Konstruktor.|  
|[CAtlModule::~CAtlModule](../Topic/CAtlModule::~CAtlModule.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](../Topic/CAtlModule::AddCommonRGSReplacements.md)|Überschreiben Sie diese Methode, um Parameter der ATL\-Registrierungsteil \(Registrierungsstelle\) Ersatzzuordnung hinzuzufügen.|  
|[CAtlModule::AddTermFunc](../Topic/CAtlModule::AddTermFunc.md)|Fügt eine neue aufgerufen werden hinzu, Funktion, wenn das Modul beendet wird.|  
|[CAtlModule::GetGITPtr](../Topic/CAtlModule::GetGITPtr.md)|Gibt den globalen Schnittstellenzeiger zurück.|  
|[CAtlModule::GetLockCount](../Topic/CAtlModule::GetLockCount.md)|Gibt die Sperrenanzahl zurück.|  
|[CAtlModule::Lock](../Topic/CAtlModule::Lock.md)|Inkrementiert die Sperrenanzahl.|  
|[CAtlModule::Term](../Topic/CAtlModule::Term.md)|Befreit alle Datenmember.|  
|[CAtlModule::Unlock](../Topic/CAtlModule::Unlock.md)|Verringert die Sperrenanzahl.|  
|[CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md)|Führt das Skript, das in einer angegebenen Ressource enthalten ist, ein Objekt zu registrieren oder deren Registrierung aufzuheben.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](../Topic/CAtlModule::UpdateRegistryFromResourceDHelper.md)|Diese Methode wird von `UpdateRegistryFromResourceD` aufgerufen, um das Registrierungsupdate auszuführen.|  
|[CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md)|Führt das Skript, das in einer angegebenen Ressource enthalten ist, ein Objekt zu registrieren oder deren Registrierung aufzuheben.  Links dieser Methode statisch mit der ATL\-Registrierungs\-Komponente.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlModule::m\_libid](../Topic/CAtlModule::m_libid.md)|Enthält die GUID des aktuellen Moduls.|  
|[CAtlModule::m\_pGIT](../Topic/CAtlModule::m_pGIT.md)|Zeiger auf den globalen Schnittstellen\-Tabelle.|  
  
## Hinweise  
 Diese Klasse wird von [CAtlDllModuleT\-Klasse](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT\-Klasse](../../atl/reference/catlexemodulet-class.md) und [CAtlServiceModuleT\-Klasse](../../atl/reference/catlservicemodulet-class.md) verwendet, um Unterstützung für DLL\-Anwendungen, EXE\-Anwendungen und Windows\-Dienste zu unterstützen, bzw.  
  
 Weitere Informationen zu Modulen in ATL, finden Sie unter [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md).  
  
 Diese Klasse ersetzt veraltete [CComModule\-Klasse](../../atl/reference/ccommodule-class.md), das in früheren Versionen von ATL verwendet wird.  
  
## Vererbungshierarchie  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 `CAtlModule`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)   
 [Registrierungskomponente \(Registrar\)](../../atl/atl-registry-component-registrar.md)