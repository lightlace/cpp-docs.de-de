---
title: Tile_barrier-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
dev_langs: C++
helpviewer_keywords: tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1f6066422056efc17052afb11d01580abc340976
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tilebarrier-class"></a>tile_barrier-Klasse
Synchronisiert die Ausführung von Threads, die in der Threadgruppe (die Kachel) mit `wait`-Methoden ausgeführt werden. Nur die Laufzeit kann diese Klasse instanziieren.  
  
### <a name="syntax"></a>Syntax 
  
```  
class tile_barrier;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Tile_barrier-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `tile_barrier`-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Warte](#wait)|Weist alle Threads in der Threadgruppe (Kachel) an, die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.|  
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle globalen Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle `tile_static`-Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tile_barrier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  

## <a name="tile_barrier__ctor"></a>Tile_barrier-Konstruktor  
 Initialisiert eine neue Instanz der Klasse durch Kopieren einer vorhandenen Arbeitsaufgabe an.  
  
### <a name="syntax"></a>Syntax 
  
```  
tile_barrier(  
    const tile_barrier& _Other ) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `tile_barrier`-Objekt.  

## <a name="wait"></a>Warte 
Weist alle Threads in der Threadgruppe (Kachel), um die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait() const restrict(amp);  
```    

## <a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence   
Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass alle Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="wait_with_global_memory_fence"></a>wait_with_global_memory_fence   
Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass alle globalen Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="wait_with_tile_static_memory_fence"></a>wait_with_tile_static_memory_fence   
Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass `tile_static` -Speicherzugriffe für andere Threads in der threadkachel sichtbar sind und in der programmreihenfolge ausgeführt wurden.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
