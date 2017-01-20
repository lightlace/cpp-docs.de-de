---
title: "CAtlAutoThreadModuleT Class"
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
  - "ATL.CAtlAutoThreadModuleT"
  - "ATL::CAtlAutoThreadModuleT"
  - "CAtlAutoThreadModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModuleT class"
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlAutoThreadModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Implementieren eines mit Threadpool, ApartmentModell COM\-Server bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class ThreadAllocator= CComSimpleThreadAllocator,  
DWORD dwWait= INFINITE   
>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT :  
public IAtlAutoThreadModule  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die den COM\-Server implementiert.  
  
 `ThreadAllocator`  
 Die Klasse, die Thread\-Auswahl verwaltet.  Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Gibt das Timeoutintervall, in Millisekunden.  Der Standardwert ist UNBEGRENZT, der Folgendes bedeutet, dass das Timeoutintervall der Methode nie ab.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](../Topic/CAtlAutoThreadModuleT::GetDefaultThreads.md)|Diese statische Funktion dynamisch berechnet und gibt die maximale Anzahl von Threads zum EXE\-Modul, anhand der Anzahl der Prozessoren zurück.|  
  
## Hinweise  
 Die Klasse wird von abgeleitet [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)`CAtlAutoThreadModuleT`, um ein mit Threadpool, ApartmentModell COM\-Server zu implementieren.  Es ersetzt die veraltete Klasse [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Diese Klasse sollte nicht in einer DLL verwendet werden, da der Standardwert `dwWait`\-Wert von INFINITE einen Deadlock verursacht, wenn die DLL entladen wird.  
  
## Vererbungshierarchie  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Modulklassen](../../atl/atl-module-classes.md)