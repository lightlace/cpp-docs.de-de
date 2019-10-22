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
ms.openlocfilehash: b0ec7d4d3dbe5ef1334bf3c394819a4f5235c28c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688981"
---
# <a name="rts_alloc-class"></a>rts_alloc-Klasse

Die Rts_alloc-Klassen Vorlage beschreibt einen [Filter](../standard-library/allocators-header.md) , der ein Array von Cache Instanzen enthält und bestimmt, welche Instanz für die Zuordnung und Aufhebung der Zuordnung zur Laufzeit anstatt zur Kompilierzeit verwendet werden soll.

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

Diese Klassen Vorlage enthält mehrere Block Belegungs Instanzen und bestimmt, welche Instanz zur Laufzeit anstelle der Kompilierzeit für die Zuordnung oder Aufhebung der Zuordnung verwendet werden soll. Sie wird mit Compilern verwendet, die keine Neubindungen kompilieren können.

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

Die Member-Funktion gibt `caches[_IDX].allocate(count)` zurück, wobei der Index `_IDX` von der angeforderten Blockgrößen *Anzahl*bestimmt wird. wenn die *Anzahl* zu groß ist, wird `operator new(count)` zurückgegeben. `cache`, das das Cache-Objekt darstellt.

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

Die Member-Funktion ruft `caches[_IDX].deallocate(ptr, count)` auf, bei dem der Index `_IDX` von der angeforderten Blockgrößen *Anzahl*bestimmt wird, oder wenn die *Anzahl* zu groß ist, wird `operator delete(ptr)` zurückgegeben.

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

**true** , wenn das Ergebnis von `caches[0].equals(other.caches[0])`; andernfalls **false**. `caches` stellt das Array von Cache-Objekten dar.

## <a name="see-also"></a>Siehe auch

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<allocators>](../standard-library/allocators-header.md)
