---
title: "Worker Archetype"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Worker archetype"
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Worker Archetype
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Klassen, die an den *Workerprototyp* entsprechen, stellen den Code zu den Prozessarbeitsaufgaben bereit, die in einem Threadpool in die Warteschlange gestellt werden.  
  
 **Implementierung**  
  
 Um eine Klasse in Übereinstimmung mit diesem Prototyp zu implementieren, muss die Klasse die folgenden Features bereitstellen:  
  
|Methode|Description|  
|-------------|-----------------|  
|[Initialisieren](../Topic/WorkerArchetype::Initialize.md)|Aufgerufen, um das Workerobjekt vor allen Anforderungen zu initialisieren werden zu [Führen Sie aus](../Topic/WorkerArchetype::Execute.md) übergeben.|  
|[Ausführen](../Topic/WorkerArchetype::Execute.md)|Aufgerufen, um eine Arbeitsaufgabe zu verarbeiten.|  
|[Beenden](../Topic/WorkerArchetype::Terminate.md)|Aufgerufen, um die Anforderungen des Workerobjekts zu deinitialisieren schließlich sind zu [Führen Sie aus](../Topic/WorkerArchetype::Execute.md) übergeben wurde.|  
  
|TypeDef|Description|  
|-------------|-----------------|  
|[RequestType](../Topic/WorkerArchetype::RequestType.md)|Typedef für den Arbeitsaufgabentyp, der durch die Workerklasse verarbeitet werden kann.|  
  
 Eine typische *Workerklasse* sieht wie folgt aus:  
  
 [!CODE [NVC_ATL_Utilities#137](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#137)]  
  
 **Vorhandene Implementierungen**  
  
 Diese Klassen passen sich an diesen Prototyp:  
  
|Klasse|Description|  
|------------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Empfängt Anforderungen aus dem Threadpool und leitet sie an ein Workerobjekt weiter, das für jede Anforderung erstellt und zerstört wird.|  
  
 **Verwendung**  
  
 Diese Vorlagenparameter erwarten die Klasse, um es diesem Prototyp anzupassen:  
  
|Parametername|Verwendet von|  
|-------------------|-------------------|  
|*Worker*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Worker*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)