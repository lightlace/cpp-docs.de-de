---
title: max_fixed_size-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
ms.openlocfilehash: 08510ecc3b7469e8f88a61dcb0df28541e170892
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412955"
---
# <a name="maxfixedsize-class"></a>max_fixed_size-Klasse

Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das ein [freelist](../standard-library/freelist-class.md)-Objekt auf eine maximale Länge begrenzt.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Max*|Die max-Klasse, die die maximale Anzahl von Elementen zum Speichern in der `freelist` bestimmt.|

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[max_fixed_size](#max_fixed_size)|Konstruiert ein Objekt vom Typ `max_fixed_size`.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[allocated](#allocated)|Erhöht die Anzahl der zugeordneten Speicherblöcke.|
|[deallocated](#deallocated)|Verringert die Anzahl der zugeordneten Speicherblöcke.|
|[full](#full)|Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.|
|[released](#released)|Verringert die Anzahl der Speicherblöcke auf der Freiliste.|
|[saved](#saved)|Erhöht die Anzahl der Speicherblöcke auf der Freiliste.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="allocated"></a> max_fixed_size::allocated

Erhöht die Anzahl der zugeordneten Speicherblöcke.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Diese Memberfunktion aufgerufen wird, nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` Operator **neue**. Das Argument *_Nx* ist die Anzahl der Speicherblöcke im Segment von Operator zugeordneten **neue**.

## <a name="deallocated"></a> max_fixed_size::deallocated

Verringert die Anzahl der zugeordneten Speicherblöcke.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Diese Memberfunktion aufgerufen wird, nach jedem Aufruf von `cache_freelist::deallocate` Operator **löschen**. Das Argument *_Nx* ist die Anzahl der Speicherblöcke im Segment vom Operator aufgehoben **löschen**.

## <a name="full"></a> max_fixed_size::full

Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.

```cpp
bool full();
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn `Max <= _Nblocks`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf zurückgegeben **"true"**, `deallocate` den Speicherblock der Freiliste hinzugefügt; versetzt, wenn "false" zurückgegeben `deallocate` Aufrufe Operator **löschen** beim Aufheben der Zuordnung des Blocks.

## <a name="max_fixed_size"></a> max_fixed_size::max_fixed_size

Konstruiert ein Objekt vom Typ `max_fixed_size`.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Hinweise

Dieser Konstruktor initialisiert den gespeicherten Wert `_Nblocks` auf null.

## <a name="released"></a> max_fixed_size::released

Verringert die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void released();
```

### <a name="remarks"></a>Hinweise

Verringert den gespeicherten Wert `_Nblocks`. Die `released`-Memberfunktion der aktuellen [max-Klasse](../standard-library/allocators-header.md) wird von `cache_freelist::allocate` aufgerufen, wenn ein Speicherblock aus der Freiliste entfernt wird.

## <a name="saved"></a> max_fixed_size::saved

Erhöht die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void saved();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion inkrementiert den gespeicherten `_Nblocks`-Wert. Diese Memberfunktion wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
