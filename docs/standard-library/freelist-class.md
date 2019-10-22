---
title: freelist-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: e37b2371238211033d6a8a0847a41677b4e908a2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688052"
---
# <a name="freelist-class"></a>freelist-Klasse

Verwaltet eine Liste von Speicherblöcken.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*RT*|Die Anzahl der zuzuordnenden Elemente des Arrays.|
|*Max*|Die max-Klasse, die die maximale Anzahl von Elementen darstellt, die in der freien Liste gespeichert werden. Die Klasse kann [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) oder [max_variable_size](../standard-library/max-variable-size-class.md) sein.|

## <a name="remarks"></a>Hinweise

Diese Klassen Vorlage verwaltet eine Liste von Speicherblöcken der Größe- *SZ* mit der maximalen Länge der Liste, die durch die max-Klasse festgelegt wird, *die maximal überschritten wird.*

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[freelist](#freelist)|Konstruiert ein Objekt vom Typ `freelist`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[pop](#pop)|Entfernt den ersten Speicherblock aus der freien Liste|
|[push](#push)|Fügt der Liste einen Speicherblock hinzu|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="freelist"></a> freelist::freelist

Konstruiert ein Objekt vom Typ `freelist`.

```cpp
freelist();
```

### <a name="remarks"></a>Hinweise

## <a name="pop"></a> freelist::pop

Entfernt den ersten Speicherblock aus der freien Liste

```cpp
void *pop();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf den Speicherblock zurück, der aus der Liste entfernt wurde

### <a name="remarks"></a>Hinweise

Die Member-Funktion gibt NULL zurück, wenn die Liste leer ist. Andernfalls entfernt sie den ersten Speicherblock aus der Liste.

## <a name="push"></a> freelist::push

Fügt der Liste einen Speicherblock hinzu

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*ptr*|Ein Zeiger auf den Speicherblock, der der freien Liste hinzugefügt werden soll|

### <a name="return-value"></a>Rückgabewert

**true** , wenn die `full`-Funktion der Max-Klasse **false**zurückgibt. Andernfalls gibt die `push`-Funktion **false**zurück.

### <a name="remarks"></a>Hinweise

Wenn die `full`-Funktion der Max-Klasse **false**zurückgibt, fügt diese Member-Funktion den Speicherblock, auf den *ptr* zeigt, an den Anfang der Liste an.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
