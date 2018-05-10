---
title: recursive_mutex-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 89c39f006cee8c62c22f3caf7e2c10ee9a0c1d03
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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

`true`, wenn die Methode erfolgreich Besitzrechte von `mutex` erhält, oder wenn der aufrufende Thread bereits im Besitz der `mutex` ist; andernfalls `false`.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, gibt die Funktion sofort `true` zurück, und die vorherige Sperre bleibt in Kraft.

## <a name="unlock"></a> unlock

Gibt den Besitz von mutex frei.

```cpp
void unlock();
```

### <a name="remarks"></a>Hinweise

Diese Methode gibt den Besitz der `mutex` erst zurück, wenn sie so oft aufgerufen wurde, wie [lock](#lock) und [try_lock](#try_lock) erfolgreich im `recursive_mutex`-Objekt aufgerufen wurden.

Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
