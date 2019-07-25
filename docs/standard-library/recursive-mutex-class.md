---
title: recursive_mutex-Klasse
ms.date: 11/04/2016
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.openlocfilehash: 448b4d03e4d38dc45621cddab7d8f5d03b805968
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451681"
---
# <a name="recursivemutex-class"></a>recursive_mutex-Klasse

Stellt einen *mutex-Typ* dar. Das Verhalten von aufrufenden Sperrmethoden für Objekte, die bereits gesperrt sind, ist im Gegensatz zu [mutex](../standard-library/mutex-class-stl.md) klar definiert.

## <a name="syntax"></a>Syntax

```cpp
class recursive_mutex;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Erstellt ein `recursive_mutex`-Objekt.|
|[~recursive_mutex-Destruktor](#dtorrecursive_mutex_destructor)|Gibt alle Ressourcen frei, die vom `recursive_mutex`-Objekt verwendet werden.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[lock](#lock)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von mutex gelangt.|
|[try_lock](#try_lock)|Versucht, ohne Blockierung in den Besitz von mutex zu gelangen.|
|[unlock](#unlock)|Gibt den Besitz von mutex frei.|

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="lock"></a> lock

Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.

```cpp
void lock();
```

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, wird die Methode sofort zurückgegeben, und die vorherige Sperre bleibt in Kraft.

## <a name="recursive_mutex"></a> recursive_mutex

Erstellt ein `recursive_mutex`-Objekt, das nicht gesperrt ist.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a> ~recursive_mutex

Gibt alle Ressourcen frei, die vom Objekt verwendet werden.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Hinweise

Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="try_lock"></a> try_lock

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Methode erfolgreich in den `mutex` Besitz von gelangt, oder, wenn der aufrufenden Thread bereits den `mutex**; otherwise, **false`besitzt.

### <a name="remarks"></a>Hinweise

Wenn der aufrufenden Thread bereits im `mutex`Besitz von ist, gibt die Funktion sofort **true**zurück, und die vorherige Sperre bleibt in Kraft.

## <a name="unlock"></a> unlock

Gibt den Besitz von mutex frei.

```cpp
void unlock();
```

### <a name="remarks"></a>Hinweise

Diese Methode gibt den Besitz der `mutex` erst zurück, wenn sie so oft aufgerufen wurde, wie [lock](#lock) und [try_lock](#try_lock) erfolgreich im `recursive_mutex`-Objekt aufgerufen wurden.

Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
