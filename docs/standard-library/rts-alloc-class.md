---
title: rts_alloc-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
ms.openlocfilehash: 2c77f93a2311dbf21959b0d2a7830c20ba6dce96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409745"
---
# <a name="rtsalloc-class"></a>rts_alloc-Klasse

Die rts_alloc-Vorlagenklasse beschreibt einen [Filter](../standard-library/allocators-header.md), der ein Array von Cache-Instanzen enthält, und ermittelt, welche Instanz für die Belegung und Freigabe zur Laufzeit und nicht zur Kompilierzeit zu verwenden ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Cache*|Der Typ der Cache-Instanzen, die im Array enthalten sind. Dieser kann eine [cache_chunklist-Klasse](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) oder [cache_suballoc](../standard-library/cache-suballoc-class.md) sein.|

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse enthält mehrere Blockbelegungsinstanzen und ermittelt zur Laufzeit, nicht zur Kompilierzeit, welche Instanz für die Belegung oder Freigabe von Speicher zu verwenden ist. Sie wird mit Compilern verwendet, die keine Neubindungen kompilieren können.

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[allocate](#allocate)|Belegt einen Speicherblock.|
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="allocate"></a> rts_alloc::allocate

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

Die Memberfunktion gibt `caches[_IDX].allocate(count)`, wobei der Index `_IDX` richtet sich nach der Größe der angeforderten Blocks *Anzahl*, oder wenn *Anzahl* ist zu groß ist, gibt `operator new(count)`. `cache`, das das Cache-Objekt darstellt.

## <a name="deallocate"></a> rts_alloc::deallocate

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

Die Memberfunktion ruft `caches[_IDX].deallocate(ptr, count)`, wobei der Index `_IDX` richtet sich nach der Größe der angeforderten Blocks *Anzahl*, oder wenn *Anzahl* ist zu groß ist, gibt `operator delete(ptr)`.

## <a name="equals"></a> rts_alloc::equals

Vergleicht zwei Caches auf Gleichheit.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Cache*|Das Cache-Objekt, das dem Filter zugeordnet ist.|
|*_Other*|Das Cache-Objekt, das auf Gleichheit verglichen werden soll.|

### <a name="remarks"></a>Hinweise

**"true"** Wenn das Ergebnis des `caches[0].equals(other.caches[0])`ist, andernfalls **"false"**. `caches` stellt das Array von Cache-Objekten dar.

## <a name="see-also"></a>Siehe auch

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)<br/>
[\<allocators>](../standard-library/allocators-header.md)<br/>
