---
title: mutex-Klasse (C++-Standardbibliothek)| Microsoft-Dokumentation
ms.date: 11/04/2016
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.openlocfilehash: 7766b063eb89a14a94eaa41ebfa17f3e4a1c102e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522563"
---
# <a name="mutex-class-c-standard-library"></a>mutex-Klasse (C++-Standardbibliothek)

Stellt einen *mutex-Typ* dar. Objekte dieses Typs können dazu verwendet werden, den gegenseitigen Ausschluss innerhalb eines Programms zu erzwingen.

## <a name="syntax"></a>Syntax

```cpp
class mutex;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[mutex](#mutex)|Erstellt ein `mutex`-Objekt.|
|[mutex::~mutex Destructor (mutex::~mutex-Destruktor)](#dtormutex_destructor)|Gibt alle Ressourcen frei, die vom `mutex`-Objekt verwendet wurden.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[lock](#lock)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|
|[native_handle](#native_handle)|Gibt den implementierungsspezifischen Typ zurück, der das Mutexhandle darstellt.|
|[try_lock](#try_lock)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|
|[unlock](#unlock)|Gibt den Besitz von `mutex` frei.|

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="lock"></a>  Mutex:: lock

Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.

```cpp
void lock();
```

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="mutex"></a>mutex::mutex-Konstruktor

Erstellt ein `mutex`-Objekt, das nicht gesperrt ist.

```cpp
constexpr mutex() noexcept;
```

## <a name="dtormutex_destructor"></a>mutex::~mutex-Destruktor

Gibt alle Ressourcen frei, die vom `mutex`-Objekt verwendet werden.

```cpp
~mutex();
```

### <a name="remarks"></a>Hinweise

Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="native_handle"></a>  Mutex:: native_handle

Gibt den implementierungsspezifischen Typ zurück, der das Mutexhandle darstellt. Das Mutexhandle kann je nach Implementierung auf die jeweils entsprechende Weise verwendet werden.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Rückgabewert

`native_handle_type` ist als `Concurrency::critical_section *` definiert, das als `void *` umgewandelt wird.

## <a name="try_lock"></a>  Mutex:: try_lock

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Methode erfolgreich Besitzrechte erhält die `mutex`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="unlock"></a>  Mutex:: Unlock

Gibt den Besitz von `mutex` frei.

```cpp
void unlock();
```

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
