---
title: Event-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74e871255e3308450764e8f65cdb6acebe79df38
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437741"
---
# <a name="event-class"></a>event-Klasse

Ein Ereignis für manuelles Zurücksetzen, das explizit die Concurrency Runtime beachtet.

## <a name="syntax"></a>Syntax

```
class event;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[~ Event-Destruktor](#dtor)|Zerstört ein Ereignis.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[reset](#reset)|Setzt das Ereignis auf einen nicht signalisierten Zustand zurück.|
|[set](#set)|Signalisiert das Ereignis.|
|[wait](#wait)|Wartet, bis das Ereignis signalisiert wird.|
|[wait_for_multiple](#wait_for_multiple)|Wartet, bis mehrere Ereignisse signalisiert werden.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|Ein Wert, der angibt, dass ein Wartevorgang nie durch einen Timeout beendet werden sollte.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Synchronisierungsdatenstrukturen](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`event`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> Ereignis

Erstellt ein neues Ereignis.

```
_CRTIMP event();
```

### <a name="remarks"></a>Hinweise

##  <a name="dtor"></a> ~ Event

Zerstört ein Ereignis.

```
~event();
```

### <a name="remarks"></a>Hinweise

Es wird erwartet, dass keine Threads auf das Ereignis warten, wenn der Destruktor ausgeführt wird. Wenn das Ereignis zerstört wird, während Threads auf das Ereignis warten, kann dies zu einem nicht definiertem Verhalten führen.

##  <a name="reset"></a> Zurücksetzen

Setzt das Ereignis auf einen nicht signalisierten Zustand zurück.

```
void reset();
```

##  <a name="set"></a> Legen Sie

Signalisiert das Ereignis.

```
void set();
```

### <a name="remarks"></a>Hinweise

Das Signalisieren des Ereignisses kann möglicherweise dazu führen, dass eine beliebige Anzahl von Kontexten, die auf das Ereignis warten, ausführbar werden.

##  <a name="timeout_infinite"></a> timeout_infinite

Ein Wert, der angibt, dass ein Wartevorgang nie durch einen Timeout beendet werden sollte.

```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

##  <a name="wait"></a> Warte

Wartet, bis das Ereignis signalisiert wird.

```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parameter

*_Timeout*<br/>
Gibt die Wartezeit in Millisekunden bis zum Timeout an. Der Wert `COOPERATIVE_TIMEOUT_INFINITE` gibt an, dass kein Timeout besteht.

### <a name="return-value"></a>Rückgabewert

Wenn der Wartezustand erfüllt wurde, wird der Wert `0` zurückgegeben. Andernfalls gibt der Wert `COOPERATIVE_WAIT_TIMEOUT` an, dass der Wartezustand durch einen Timeout beendet wurde, ohne dass das Ereignis signalisiert wurde.

> [!IMPORTANT]
>  Rufen Sie in einer app (Universelle Windows Plattform) nicht `wait` im asta thread auf, da dieser Aufruf den aktuellen Thread blockieren kann und dazu führen, die app dass kann reagiert.

##  <a name="wait_for_multiple"></a> wait_for_multiple

Wartet, bis mehrere Ereignisse signalisiert werden.

```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parameter

*_PPEvents*<br/>
Ein Array von Ereignissen, auf die gewartet werden soll. Die Anzahl der Ereignisse im Array wird durch den `count`-Parameter angegeben.

*count*<br/>
Die Anzahl von Ereignissen innerhalb des im `_PPEvents`-Parameter angegebenen Arrays.

*_FWaitAll*<br/>
Wenn der Parameter auf den Wert `true` festgelegt wird, gibt dies an, dass innerhalb des Arrays, das im `_PPEvents`-Parameter angegeben wurde, alle Ereignisse ausgelöst werden müssen, um den Wartevorgang zu beenden. Eine Festlegung auf den Wert `false` gibt an, dass jedes ausgelöste Ereignis innerhalb des Arrays, das im `_PPEvents`-Parameter angegeben wurde, für den Wartevorgang ausreichend ist.

*_Timeout*<br/>
Gibt die Wartezeit in Millisekunden bis zum Timeout an. Der Wert `COOPERATIVE_TIMEOUT_INFINITE` gibt an, dass kein Timeout besteht.

### <a name="return-value"></a>Rückgabewert

Wenn die Anforderungen des Wartevorgangs erfüllt wurden, ist dies der Index innerhalb des Arrays, das im `_PPEvents`-Parameter angegeben wurde und die Wartebedingung erfüllt hat. Andernfalls gibt der Wert `COOPERATIVE_WAIT_TIMEOUT` an, dass das Timeout für den Wartevorgang abgelaufen ist, ohne dass die Bedingung erfüllt wurde.

### <a name="remarks"></a>Hinweise

Wenn der Parameter `_FWaitAll` auf den Wert `true` festgelegt wurde, um anzugeben, dass alle Ereignisse signalisiert werden müssen, um den Wartevorgang zu beenden, hat der von der Funktion zurückgegebene Index keine andere besondere Bedeutung außer der Tatsache, dass er nicht den Wert `COOPERATIVE_WAIT_TIMEOUT` darstellt.

> [!IMPORTANT]
>  Rufen Sie in einer app (Universelle Windows Plattform) nicht `wait_for_multiple` im asta thread auf, da dieser Aufruf den aktuellen Thread blockieren kann und dazu führen, die app dass kann reagiert.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
