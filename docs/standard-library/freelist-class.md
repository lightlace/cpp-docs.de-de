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
ms.openlocfilehash: ef1f2e617e93869a1084dc030c6496c819f1ed96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159391"
---
# <a name="freelist-class"></a>freelist-Klasse

Verwaltet eine Liste von Speicherblöcken

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Sz*|Die Anzahl der zuzuordnenden Elemente des Arrays.|
|*Max*|Die max-Klasse, die die maximale Anzahl von Elementen darstellt, die in der freien Liste gespeichert werden. Die Klasse kann [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) oder [max_variable_size](../standard-library/max-variable-size-class.md) sein.|

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse verwaltet eine Liste von Speicherblöcken der Größe *Sz* mit die maximale Länge der Liste bestimmt, indem die max-Klasse übergeben *Max*.

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

Die Memberfunktion gibt NULL zurück, wenn die Liste leer ist. Andernfalls entfernt sie den ersten Speicherblock aus der Liste.

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

**"true"** Wenn die `full` Funktionsergebnis ist eine der max-Klasse **"false"** ist, andernfalls die `push` -Funktion zurückgegeben **"false"**.

### <a name="remarks"></a>Hinweise

Wenn die `full` Funktionsergebnis ist eine der max-Klasse **"false"**, diese Memberfunktion fügt den Speicherblock verweist *Ptr* an den Anfang der Liste.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
