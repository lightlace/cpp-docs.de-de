---
title: "tile_barrier-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tile_barrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tile_barrier-Klasse"
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# tile_barrier-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Synchronisiert die Ausführung von Threads, die in der Threadgruppe \(die Kachel\) mit `wait`\-Methoden ausgeführt werden.  Nur die Laufzeit kann diese Klasse instanziieren.  
  
## Syntax  
  
```  
class tile_barrier;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tile\_barrier::tile\_barrier\-Konstruktor](../Topic/tile_barrier::tile_barrier%20Constructor.md)|Initialisiert eine neue Instanz der `tile_barrier`\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tile\_barrier::wait\-Methode](../Topic/tile_barrier::wait%20Method.md)|Weist alle Threads in der Threadgruppe \(Kachel\) an, die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.|  
|[tile\_barrier::wait\_with\_all\_memory\_fence\-Methode](../Topic/tile_barrier::wait_with_all_memory_fence%20Method.md)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
|[tile\_barrier::wait\_with\_global\_memory\_fence\-Methode](../Topic/tile_barrier::wait_with_global_memory_fence%20Method.md)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle globalen Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
|[tile\_barrier::wait\_with\_tile\_static\_memory\_fence\-Methode](../Topic/tile_barrier::wait_with_tile_static_memory_fence%20Method.md)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle `tile_static`\-Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
  
## Vererbungshierarchie  
 `tile_barrier`  
  
## Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)