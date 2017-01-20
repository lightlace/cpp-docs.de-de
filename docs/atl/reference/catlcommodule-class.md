---
title: "CAtlComModule Class"
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
  - "ATL.CAtlComModule"
  - "CAtlComModule"
  - "ATL::CAtlComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlComModule class"
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein COM\-Server\-Modul.  
  
## Syntax  
  
```  
  
   class CAtlComModule :  
public _ATL_COM_MODULE  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](../Topic/CAtlComModule::CAtlComModule.md)|Der \-Konstruktor.|  
|[CAtlComModule::~CAtlComModule](../Topic/CAtlComModule::~CAtlComModule.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](../Topic/CAtlComModule::RegisterServer.md)|Rufen Sie diese Methode auf, um die Systemregistrierung für jedes Objekt in der Objektzuordnung zu aktualisieren.|  
|[CAtlComModule::RegisterTypeLib](../Topic/CAtlComModule::RegisterTypeLib.md)|Rufen Sie diese Methode auf, um eine Typbibliothek zu registrieren.|  
|[CAtlComModule::UnregisterServer](../Topic/CAtlComModule::UnregisterServer.md)|Rufen Sie diese Methode auf, um jedes Objekt in der Objektzuordnung Registrierung aufzuheben.|  
|[CAtlComModule::UnRegisterTypeLib](../Topic/CAtlComModule::UnRegisterTypeLib.md)|Rufen Sie diese Methode auf, um eine Typbibliothek Registrierung aufzuheben.|  
  
## Hinweise  
 `CAtlComModule` implementiert ein COM\-Server\-Modul und ermöglicht einem Client, um auf die Komponenten des Moduls zuzugreifen.  
  
 Diese Klasse ersetzt die veraltete [CComModule](../../atl/reference/ccommodule-class.md)\-Klasse, die in früheren Versionen von ATL verwendet wird.  Siehe [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md) für weitere Details.  
  
## Vererbungshierarchie  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)  
  
 `CAtlComModule`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md)   
 [Class Overview](../../atl/atl-class-overview.md)