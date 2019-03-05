---
title: tile_barrier-Klasse
ms.date: 11/04/2016
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
ms.openlocfilehash: 4336a4cc317344c881f60e5ed4c5bdf8328a34b8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301167"
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
|[wait](#wait)|Weist alle Threads in der Threadgruppe (Kachel) an, die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle globalen Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Blockiert die Ausführung aller Threads in einer Kachel, bis alle `tile_static`-Speicherzugriffe abgeschlossen sind und alle Threads in der Kachel diesen Aufruf erreicht haben.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tile_barrier`

## <a name="requirements"></a>Anforderungen

**Header:** amp.h

**Namespace:** Parallelität

## <a name="tile_barrier__ctor"></a>  Tile_barrier-Konstruktor

Initialisiert eine neue Instanz der Klasse durch Kopieren einer vorhandenen Instanz an.

### <a name="syntax"></a>Syntax

```
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
Das zu kopierende `tile_barrier`-Objekt.

## <a name="wait"></a>  Warte

Weist alle Threads in der Threadgruppe (Kachel), um die Ausführung zu beenden, bis alle Threads in der Kachel den Wartevorgang beendet haben.

### <a name="syntax"></a>Syntax

```
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a>  wait_with_all_memory_fence

Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass alle Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.

### <a name="syntax"></a>Syntax

```
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="wait_with_global_memory_fence"></a>  wait_with_global_memory_fence

Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass alle globalen Speicherzugriffe für andere Threads in der Threadkachel sichtbar sind und in der Programmreihenfolge ausgeführt wurden.

### <a name="syntax"></a>Syntax

```
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="wait_with_tile_static_memory_fence"></a>  wait_with_tile_static_memory_fence

Blockiert die Ausführung aller Threads in einer Kachel, bis alle Threads in einer Kachel diesen Aufruf erreicht haben. Dadurch wird sichergestellt, dass `tile_static` Arbeitsspeicher zugreift, für andere Threads in der threadkachel sichtbar sind, und in der programmreihenfolge ausgeführt wurden.

### <a name="syntax"></a>Syntax

```
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
