---
title: "CAtlAutoThreadModule Class"
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
  - "ATL.CAtlAutoThreadModule"
  - "CAtlAutoThreadModule"
  - "ATL::CAtlAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModule class"
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein mit Threadpool, ApartmentModell COM\-Server.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      class CAtlAutoThreadModule :  
public CAtlAutoThreadModuleT< CAtlAutoThreadModule >  
```  
  
## Hinweise  
 `CAtlAutoThreadModule` [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) wird von abgeleitet und implementiert ein mit Threadpool, ApartmentModell COM\-Server.  `CAtlAutoThreadModule` verwendet [CComApartment](../../atl/reference/ccomapartment-class.md), um ein Apartment für jeden Thread im Modul zu verwalten.  
  
 Sie müssen das [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)\-Makro in der Klassendefinition des Objekts verwenden, um [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als die Klassenfactory anzugeben.  Sie sollten eine einzelne Instanz einer Klasse hinzufügen, die von `CAtlAutoThreadModuleT` wie `CAtlAutoThreadModule` abgeleitet wird.  Beispiel:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Diese Klasse ersetzt die veraltete [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)\-Klasse.  
  
## Vererbungshierarchie  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CAtlAutoThreadModuleT Class](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)