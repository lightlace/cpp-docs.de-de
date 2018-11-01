---
title: sync_shared-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: c368e99eb9f128963e90cdc1d39bdb9d4569efe9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483381"
---
# <a name="syncshared-class"></a>sync_shared-Klasse

Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), in dem ein Mutex verwendet wird, um den Zugriff auf ein Cache-Objekt zu steuern, das von allen Zuweisungen (allocator-Objekten) gemeinsam verwendet wird.

## <a name="syntax"></a>Syntax

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Cache*|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dieser kann [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) oder [cache_suballoc](../standard-library/cache-suballoc-class.md) sein.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[allocate](#allocate)|Belegt einen Speicherblock.|
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="allocate"></a> sync_shared::allocate

Belegt einen Speicherblock.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*count*|Die Anzahl der zuzuordnenden Elemente des Arrays.|

### <a name="return-value"></a>Rückgabewert

Zeiger auf das zugewiesene Objekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion sperrt den Mutex, ruft `cache.allocate(count)` auf, entsperrt den Mutex und gibt das Ergebnis des früheren Aufrufs an `cache.allocate(count)` zurück. `cache` stellt das aktuelle Cache-Objekt dar.

## <a name="deallocate"></a> sync_shared::deallocate

Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*ptr*|Ein Zeiger auf das erste Objekt, dessen Zuweisung zum Speicher aufgehoben werden soll.|
|*count*|Die Anzahl von Objekten, deren Zuweisung zum Speicherplatz aufgehoben werden soll.|

### <a name="remarks"></a>Hinweise

Diese Memberfunktion sperrt den Mutex, ruft `cache.deallocate(ptr, count)` auf, wobei `cache` das Cache-Objekt darstellt, und entsperrt dann den Mutex.

## <a name="equals"></a> sync_shared::equals

Vergleicht zwei Caches auf Gleichheit.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Cache*|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll.|
|*Andere*|Das Cache-Objekt, das auf Gleichheit verglichen werden soll.|

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn das Ergebnis des `cache.equals(Other.cache)`, wobei `cache` das Cache-Objekt darstellt, ist **"true"** ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
