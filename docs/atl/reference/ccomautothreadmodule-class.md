---
title: "CComAutoThreadModule Class"
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
  - "CComAutoThreadModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartment model modules"
  - "CComAutoThreadModule class"
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CComAutoThreadModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ab ATL 7.0 ist `CComAutoThreadModule` veraltet: finden Sie unter [ATL\-Modul\-Klassen](../../atl/atl-module-classes.md) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
class ThreadAllocator= CComSimpleThreadAllocator   
>  
class CComAutoThreadModule :  
public CComModule  
```  
  
#### Parameter  
 `ThreadAllocator`  
 \[in\] Die Klasse, die Thread\-Auswahl verwaltet.  Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[CreateInstance](../Topic/CComAutoThreadModule::CreateInstance.md)|Wählt einen Thread aus und erstellt dann ein Objekt im zugeordneten Apartment.|  
|[GetDefaultThreads](../Topic/CComAutoThreadModule::GetDefaultThreads.md)|\(Statisch\) dynamisch berechnet die Anzahl der Threads für das Modul auf Grundlage der Anzahl der Prozessoren.|  
|[Init](../Topic/CComAutoThreadModule::Init.md)|Erstellt die Threads des Moduls.|  
|[Sperren](../Topic/CComAutoThreadModule::Lock.md)|Inkrementiert die Sperrenanzahl auf dem Modul und im aktuellen Thread.|  
|[Entsperren Sie](../Topic/CComAutoThreadModule::Unlock.md)|Dekrementiert die Sperrenanzahl auf dem Modul und im aktuellen Thread.|  
  
### Datenmember  
  
### Datenmember  
  
|||  
|-|-|  
|[dwThreadID](../Topic/CComAutoThreadModule::dwThreadID.md)|Enthält den Bezeichner des aktuellen Threads.|  
|[m\_Allocator](../Topic/CComAutoThreadModule::m_Allocator.md)|Verwaltet Thread\-Auswahl.|  
|[m\_nThreads](../Topic/CComAutoThreadModule::m_nThreads.md)|Enthält die Anzahl der Threads im Modul.|  
|[m\_pApartments](../Topic/CComAutoThreadModule::m_pApartments.md)|Verwaltet die Apartments des Moduls.|  
  
## Hinweise  
  
> [!NOTE]
>  Diese Klasse ist veraltet, nachdem sie durch die [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) und [CAtlModule](../../atl/reference/catlmodule-class.md) abgeleiteten Klassen sie ersetzt wurde.  Die Informationen, die erfolgreich ist, sind für die Verwendung mit älteren Versionen von ATL.  
  
 `CComAutoThreadModule` wird von abgeleitet [CComModule](../../atl/reference/ccommodule-class.md), um einen, ApartmentModell COM\-Server mit Threadpool für EXE\-Dateien und Windows\-Dienste zu implementieren.  `CComAutoThreadModule` verwendet [CComApartment](../../atl/reference/ccomapartment-class.md), um ein Apartment für jeden Thread im Modul zu verwalten.  
  
 Leiten Sie das Modul von `CComAutoThreadModule`, wenn Sie Objekte in mehreren Apartments erstellen möchten.  Sie müssen das [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)\-Makro in der Klassendefinition des Objekts auch einschließen, um [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als die Klassenfactory anzugeben.  
  
 Standardmäßig berechnet der Anwendungs\-Assistent ATL COM \(der ATL\-Projekt\-Assistent in Visual Studio .NET.\) das Modul von `CComModule`.  Um `CComAutoThreadModule` zu verwenden, ändern Sie die Klassendefinition.  Beispiel:  
  
 [!CODE [NVC_ATL_AxHost#2](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_AxHost#2)]  
  
## Vererbungshierarchie  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)