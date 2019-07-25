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
ms.openlocfilehash: 065c0eaf936a438f48dbb8aa28704e0f53926a03
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451135"
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

Die Member-Funktion `caches[_IDX].allocate(count)`gibt zurück, wobei `_IDX` der Index durch die angeforderte Block *Größe bestimmt*wird, oder wenn *count* zu groß ist, wird `operator new(count)`zurückgegeben. `cache`, das das Cache-Objekt darstellt.

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

Die Member-Funktion `caches[_IDX].deallocate(ptr, count)`Ruft auf, wobei `_IDX` der Index durch die angeforderte Block *Größe bestimmt*wird, oder wenn *count* zu groß ist, wird `operator delete(ptr)`zurückgegeben.

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

**true** , wenn das Ergebnis `caches[0].equals(other.caches[0])`von ist, andernfalls **false**. `caches` stellt das Array von Cache-Objekten dar.

## <a name="see-also"></a>Siehe auch

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<allocators>](../standard-library/allocators-header.md)
