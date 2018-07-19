---
title: lock_guard-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f53732fee62906da19a5771c8598cce51fc6331
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953757"
---
# <a name="lockguard-class"></a>lock_guard-Klasse

Stellt eine Vorlage dar, die zum Erstellen eines Objekts instanziiert werden kann, dessen Destruktor ein `mutex`-Objekt entsperrt.

## <a name="syntax"></a>Syntax

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Hinweise

Das Vorlagenargument `Mutex` muss einem *Mutex-Typ* benennen.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`lock_guard::mutex_type`|Synonym für das Vorlagenargument `Mutex`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[lock_guard](#lock_guard)|Erstellt ein `lock_guard`-Objekt.|
|[lock_guard::~lock_guard Destruktor](#dtorlock_guard_destructor)|Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.|

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="lock_guard"></a> lock_guard::lock_guard-Konstruktor

Erstellt ein `lock_guard`-Objekt.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parameter

*Mtx* ein *Mutex-Typ* Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor konstruiert ein Objekt des Typs `lock_guard` und Sperren *Mtx*. Wenn *Mtx* ist keiner rekursiven Mutex entspricht, muss dieses entsperrt werden, wenn dieser Konstruktor aufgerufen wird.

Der zweite Konstruktor sperrt nicht *Mtx*. *Mtx* muss gesperrt werden, wenn dieser Konstruktor aufgerufen wird. Der Konstruktor löst keine Ausnahmen aus.

## <a name="dtorlock_guard_destructor"></a> lock_guard::~lock_guard-Destruktor

Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Hinweise

Wenn das `mutex`-Objekt nicht vorhanden ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
