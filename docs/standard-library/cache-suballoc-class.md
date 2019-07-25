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
ms.openlocfilehash: aa0ceda69fc169593719c3a4f81d308bb6cde284
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449657"
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
|*Sz*|Die Anzahl der zuzuordnenden Elemente des Arrays.|

## <a name="remarks"></a>Hinweise

Die Cache_suballoc-Vorlagen Klasse speichert frei zugeordnete Speicherblöcke in einer frei Liste mit begrenzter Länge, `freelist<sizeof(Type), max_unbounded>`unter Verwendung von und unterordnet Speicherblöcke von einem größeren Block, der mit **Operator new** zugeordnet wird, wenn die Freiliste leer ist.

Jeder Block enthält `Sz * Nelts` Bytes des verwendbaren Speichers und die Daten, die der **Operator new** und der **Operator Delete** erfordern. Zugeordnete Blöcke werden niemals freigegeben.

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

[\<allocators>](../standard-library/allocators-header.md)
