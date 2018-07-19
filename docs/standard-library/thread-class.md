---
title: thread-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
dev_langs:
- C++
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::thread [C++]
- std::thread [C++], thread
- std::thread [C++], detach
- std::thread [C++], get_id
- std::thread [C++], hardware_concurrency
- std::thread [C++], join
- std::thread [C++], joinable
- std::thread [C++], native_handle
- std::thread [C++], swap
ms.workload:
- cplusplus
ms.openlocfilehash: 47afdbd5e4a5045ec5f91f8f766b45d3d547ba3e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958204"
---
# <a name="thread-class"></a>thread-Klasse

Definiert ein Objekt, das zum Überwachen und Verwalten eines Ausführungsthreads innerhalb einer Anwendung verwendet wird.

## <a name="syntax"></a>Syntax

```cpp
class thread;
```

## <a name="remarks"></a>Hinweise

Sie können eine **Thread** Objekt zum Überwachen und Verwalten eines Ausführungsthreads innerhalb einer Anwendung. Ein Threadobjekt, das mithilfe eines Standardkonstruktors erstellt wird, ist keinem Ausführungsthread zugeordnet. Mit einem Threadobjekt, das mithilfe eines aufrufbaren Objekts erstellt wird, wird ein neuer Ausführungsthread erstellt, und das aufrufbare Objekt in diesem Thread wird aufgerufen. Threadobjekte können verschoben aber nicht kopiert werden. Daher kann ein Ausführungsthread nur einem Threadobjekt zugeordnet werden.

Jeder Ausführungsthread besitzt einen eindeutigen Bezeichner des Typs `thread::id`. Die `this_thread::get_id`-Funktion gibt den Bezeichner des aufrufenden Threads zurück. Die `thread::get_id`-Memberfunktion gibt den Bezeichner des von einem Threadobjekt verwalteten Threads zurück. Ein nach Standard erstelltes Threadobjekt gibt die `thread::get_id`-Methode ein Objekt zurück, das über einen Wert verfügt, der für alle nach Standard erstellten Threadobjekte gleich ist und sich von dem von `this_thread::get_id` zurückgegebenen Wert für jeden Ausführungsthread, der zum Zeitpunkt des Aufrufs verknüpft werden kann, unterschiedet.

## <a name="members"></a>Member

### <a name="public-classes"></a>Öffentliche Klassen

|Name|Beschreibung|
|----------|-----------------|
|[thread::id-Klasse](#id_class)|Identifiziert den zugeordneten Thread eindeutig.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[thread](#thread)|Erstellt eine **Thread** Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Trennen](#detach)|Trennt den zugeordneten Thread aus dem **Thread** Objekt.|
|[get_id](#get_id)|Gibt den eindeutigen Bezeichner des zugeordneten Threads zurück.|
|[hardware_concurrency](#hardware_concurrency)|Statisch Gibt eine Schätzung der Anzahl von Hardwarethreadkontexten zurück.|
|[join](#join)|Blockiert, bis der zugeordnete Thread abgeschlossen ist.|
|[joinable](#joinable)|Gibt an, ob dem zugehörigen Thread beigetreten werden kann.|
|[native_handle](#native_handle)|Gibt den implementierungsspezifischen Typ zurück, der das Threadhandle darstellt.|
|[swap](#swap)|Tauscht den Objektzustand mit einem angegebenen **Thread** Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[thread::operator=](#op_eq)|Weist einem Thread mit der aktuellen **Thread** Objekt.|

## <a name="requirements"></a>Anforderungen

**Header:** \<thread>

**Namespace:** std

## <a name="detach"></a>  Thread:: Detach

Trennt den zugeordneten Thread. Das Betriebssystem wird zum Freigeben von Threadressourcen zuständig.

```cpp
void detach();
```

### <a name="remarks"></a>Hinweise

Nach einem Aufruf von `detach` geben nachfolgende Aufrufe von [Get_id](#get_id) [id](#id_class) zurück.

Wenn der Thread, der dem aufrufenden Objekt zugeordnet ist, nicht beitreten kann, löst die Funktion einen [system_error](../standard-library/system-error-class.md)-Fehler mit Fehlercode `invalid_argument` aus.

Wenn der Thread, der dem aufrufenden Objekt zugeordnet ist, ungültig ist, löst die Funktion einen `system_error` mit Fehlercode `no_such_process` aus.

## <a name="get_id"></a>  Thread:: get_id

Gibt den eindeutigen Bezeichner für den zugeordneten Threads zurück.

```cpp
id get_id() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein [thread::id](#id_class)-Objekt, das den zugeordneten Thread eindeutig ausweist, oder `thread::id()`, wenn kein Thread dem Objekt zugeordnet ist.

## <a name="hardware_concurrency"></a>  Thread:: hardware_concurrency

Statische Methode, diet eine Schätzung der Anzahl von Hardwarethreadkontexten zurückgibt.

```cpp
static unsigned int hardware_concurrency() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Eine Schätzung der Anzahl von Hardwarethreadkontexten. Wenn der Wert nicht berechnet werden kann oder nicht klar definiert ist, gibt diese Methode 0 zurück.

## <a name="id_class"></a> thread::id-Klasse

Stellt einen eindeutigen Bezeichner für jeden Thread der Ausführung im Prozess bereit.

```cpp
class thread::id {
    id() noexcept;
};
```

### <a name="remarks"></a>Hinweise

Der Standardkonstruktor erstellt ein Objekt, das nicht gleich dem `thread::id`-Objekt für die vorhandenen Threads ist.

Alle mit dem Standwert konstruierten `thread::id`-Objekte gelten als gleich.

## <a name="join"></a>  Thread:: Join

Blockiert, bis der Thread der Ausführung, der das aufrufende Objekt zugeordnet wurde, abgeschlossen ist.

```cpp
void join();
```

### <a name="remarks"></a>Hinweise

Wenn der Aufruf erfolgreich ist, geben nachfolgende Aufrufe von [get_id](#get_id) für das aufrufende Objekt eine Standard-[Thread:: ID](#id_class) zurück, die nicht gleich `thread::id` eines beliebigen vorhandenen Threads ist. Wenn der Aufruf nicht erfolgreich ist, ist der Wert, der von `get_id` zurückgegeben wird, unverändert.

## <a name="joinable"></a>  Thread:: joinable

Gibt an, ob dem zugeordneten Thread *beigetreten* werden kann.

```cpp
bool joinable() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

**"true"** ist der zugeordnete Thread *beigetreten*ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Einem Thread-Objekt kann *beigetreten* werden, wenn `get_id() != id()`.

## <a name="native_handle"></a>  Thread:: native_handle

Gibt den implementierungsspezifischen Typ zurück, der das Threadhandle darstellt. Das Threadhandle kann je nach Implementierung auf die jeweils entsprechende Weise verwendet werden.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Rückgabewert

`native_handle_type` ist als Win32-`HANDLE` definiert, das als `void *` umgewandelt wird.

## <a name="op_eq"></a> thread::operator=

Ordnet den Thread für das angegebene Objekt dem aktuellen Objekt zu.

```cpp
thread& operator=(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parameter

*Andere*  
 Ein **Thread** Objekt.

### <a name="return-value"></a>Rückgabewert

`*this`

### <a name="remarks"></a>Hinweise

Die Methodenaufrufe trennen, wenn dem aufrufenden Objekt beigetreten werden kann.

Nach dem Erstellen die Zuordnung wird `Other` auf einen standardmäßig konstruierten Zustand festgelegt.

## <a name="swap"></a>  Thread:: Swap

Tauscht den Objektzustand mit dem eines angegebenen **Thread** Objekt.

```cpp
void swap(thread& Other) noexcept;
```

### <a name="parameters"></a>Parameter

*Andere*  
 Ein **Thread** Objekt.

## <a name="thread"></a> thread::thread-Konstruktor

Erstellt eine **Thread** Objekt.

```cpp
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```

### <a name="parameters"></a>Parameter

*F*  
 Eine anwendungsdefinierte Funktion, die vom Thread ausgeführt werden soll.

*A*  
 Eine Liste der zu übergebenden Argumente *F*.

*Andere*  
 Eine vorhandene **Thread** Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein Objekt, das nicht einem Thread der Ausführung zugeordnet ist. Der Wert, der durch einen Aufruf von `get_id` für das erstellte Objekt zurückgegeben wird, ist `thread::id()`.

Der zweite Konstruktor erstellt ein Objekt, das einem neuen Thread der Ausführung zugeordnet ist und die Pseudofunktion `INVOKE` ausführt, die in [\<functional>](../standard-library/functional.md) definiert ist. Wenn nicht genügend Ressourcen zum Starten eines neuen Threads verfügbar sind, löst die Funktion ein [system_error](../standard-library/system-error-class.md)-Objekt mit dem Fehlercode `resource_unavailable_try_again` aus. Wenn der Aufruf von *F* wird mit einer nicht abgefangenen Ausnahme beendet [beenden](../standard-library/exception-functions.md#terminate) aufgerufen wird.

Der dritte Konstruktor erstellt ein Objekt, das mit dem Thread verknüpft ist, der `Other` zugeordnet ist. `Other` wird dann auf einen standardmäßig konstruierten Zustand festgelegt.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<thread>](../standard-library/thread.md)<br/>
