---
title: cache_chunklist-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: 73730e0a4a22e7f5e63809cc2c1603cbda1ab596
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449663"
---
# <a name="cachechunklist-class"></a>cache_chunklist-Klasse

Definiert eine [Blockzuweisung](../standard-library/allocators-header.md), die Speicherblöcke einheitlicher Größe zuweist und freigibt.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Sz*|Die Anzahl der zuzuordnenden Elemente des Arrays.|

## <a name="remarks"></a>Hinweise

Diese Vorlagen Klasse verwendet den **New-Operator** , um Segmente von unformatierten Arbeitsspeicher zuzuordnen, und subzuordnende Blöcke, um bei Bedarf Speicher für einen Speicherblock zuzuweisen. Er speichert frei zugeordnete Speicherblöcke in einer separaten freien Liste für jeden Block und verwendet den **Operator Delete** zum Aufheben der Zuordnung eines Segments, wenn kein Arbeitsspeicher Block verwendet wird.

Jeder Speicherblock enthält *SZ* -Bytes des verwendbaren Speichers und einen Zeiger auf den Block, zu dem er gehört. Jeder Block enthält `Nelts` Speicherblöcke, drei Zeiger, einen int-Wert und die Daten, die **Operator new** und **Operator Delete** erfordern.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[cache_chunklist](#cache_chunklist)|Konstruiert ein Objekt vom Typ `cache_chunklist`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[allocate](#allocate)|Belegt einen Speicherblock.|
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="allocate"></a> cache_chunklist::allocate

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

## <a name="cache_chunklist"></a> cache_chunklist::cache_chunklist

Konstruiert ein Objekt vom Typ `cache_chunklist`.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Hinweise

## <a name="deallocate"></a> cache_chunklist::deallocate

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
