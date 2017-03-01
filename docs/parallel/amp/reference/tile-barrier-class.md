---
title: Tile_barrier-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tile_barrier
dev_langs:
- C++
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 7ace6bb366881f9e5a9678b3a005f3079542c9cd
ms.lasthandoff: 02/24/2017

---
# <a name="tilebarrier-class"></a>tile_barrier-Klasse
Synchronisiert die Ausführung von Threads, die in der Threadgruppe (die Kachel) mit `wait`-Methoden ausgeführt werden. Nur die Laufzeit kann diese Klasse instanziieren.  
  
### <a name="syntax"></a>Syntax 
  
```  
class tile_barrier;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Tile_barrier-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `tile_barrier`-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Wait-Methode](#wait)|Weist alle Threads in der Threadgruppe (Kachel) an, die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.|  
|[Wait_with_all_memory_fence-Methode](#wait_with_all_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
|[Wait_with_global_memory_fence-Methode](#wait_with_global_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle globalen Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
|[Wait_with_tile_static_memory_fence-Methode](#wait_with_tile_static_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle `tile_static`-Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `tile_barrier`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Parallelität  

## <a name="a-nametilebarrierctora--tilebarrier-constructor"></a><a name="tile_barrier__ctor"></a>Tile_barrier-Konstruktor  
 Initialisiert eine neue Instanz der Klasse durch Kopieren einer vorhandenen Instanz.  
  
### <a name="syntax"></a>Syntax 
  
```  
tile_barrier(  
    const tile_barrier& _Other ) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `tile_barrier`-Objekt.  

## <a name="a-namewaita--wait"></a><a name="wait"></a>Warte 
Weist alle Threads in der Threadgruppe (Kachel), um die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait() const restrict(amp);  
```    

## <a name="a-namewaitwithallmemoryfencea--waitwithallmemoryfence"></a><a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence   
Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass alle Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="a-namewaitwithglobalmemoryfencea--waitwithglobalmemoryfence"></a><a name="wait_with_global_memory_fence"></a>wait_with_global_memory_fence   
Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass alle globalen Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="a-namewaitwithtilestaticmemoryfencea--waitwithtilestaticmemoryfence"></a><a name="wait_with_tile_static_memory_fence"></a>wait_with_tile_static_memory_fence   
Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass `tile_static`-Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.  
  
### <a name="syntax"></a>Syntax 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

