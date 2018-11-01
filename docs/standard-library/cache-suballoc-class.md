---
title: cache_suballoc-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 06d0ef390e6ae1980b9ab20b8ceb67213837148b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438869"
---
# <a name="cachesuballoc-class"></a>cache_suballoc-Klasse

Definiert eine [Blockzuweisung](../standard-library/allocators-header.md), die Speicherblöcke einheitlicher Größe zuweist und freigibt.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*sz*|Die Anzahl der zuzuordnenden Elemente des Arrays.|

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse Cache_suballoc speichert freigegebene Speicherblöcke in einer Freiliste mit unbegrenzter Länge unter Verwendung `freelist<sizeof(Type), max_unbounded>`, und führt eine unterzuweisung von Speicherblöcken aus einem größeren Block zugeordnet **new-Operator** bei der Freiliste hinzugefügt wird leer.

Jeder Block enthält `Sz * Nelts` Bytes Speicherkapazität und die Daten, die **new-Operator** und **Delete-Operator** erfordern. Zugeordnete Blöcke werden niemals freigegeben.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[cache_suballoc](#cache_suballoc)|Konstruiert ein Objekt vom Typ `cache_suballoc`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[allocate](#allocate)|Belegt einen Speicherblock.|
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="allocate"></a> cache_suballoc::allocate

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

## <a name="cache_suballoc"></a> cache_suballoc::cache_suballoc

Konstruiert ein Objekt vom Typ `cache_suballoc`.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Hinweise

## <a name="deallocate"></a> cache_suballoc::deallocate

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

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
