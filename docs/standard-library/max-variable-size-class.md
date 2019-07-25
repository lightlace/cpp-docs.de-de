---
title: max_variable_size-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
ms.openlocfilehash: f8b3c61676f784bf9369c22b5db97d7b251f7ac6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447283"
---
# <a name="maxvariablesize-class"></a>max_variable_size-Klasse

Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das die maximale Länge eines [freelist](../standard-library/freelist-class.md)-Objekts auf eine maximale Länge einschränkt, die annähernd proportional zur Anzahl von zugewiesenen Speicherblöcken ist.

## <a name="syntax"></a>Syntax

```cpp
class max_variable_size
```

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[max_variable_size](#max_variable_size)|Konstruiert ein Objekt vom Typ `max_variable_size`.|

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

## <a name="allocated"></a> max_variable_size::allocated

Erhöht die Anzahl der zugeordneten Speicherblöcke.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Diese Member-Funktion fügt *_Nx* dem gespeicherten Wert `_Nallocs`hinzu. Diese Member-Funktion wird nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` für den **New**-Operator aufgerufen. Das Argument *_Nx* ist die Anzahl der Speicherblöcke in dem Block, der von Operator **New**zugeordnet wird.

## <a name="deallocated"></a> max_variable_size::deallocated

Verringert die Anzahl der zugeordneten Speicherblöcke.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Member-Funktion subtrahiert *_Nx* vom `_Nallocs`gespeicherten Wert. Diese Member-Funktion wird nach jedem Aufruf von `cache_freelist::deallocate` zum **Delete**-Operator aufgerufen. Das Argument *_Nx* gibt die Anzahl der Speicherblöcke in dem Block an, dessen Zuordnung durch den Operator **Delete**aufgehoben wird.

## <a name="full"></a> max_variable_size::full

Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.

```cpp
bool full();
```

### <a name="return-value"></a>Rückgabewert

**true** , `_Nallocs / 16 + 16 <= _Nblocks`wenn.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf **true**zurückgibt `deallocate` , wird der Speicherblock in die freie Liste eingefügt; Wenn false zurück `deallocate` gegeben wird, ruft der Operator Delete auf, um den Block zu **Entfernen** .

## <a name="max_variable_size"></a> max_variable_size::max_variable_size

Konstruiert ein Objekt vom Typ `max_variable_size`.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Hinweise

Dieser Konstruktor initialisiert die gespeicherten Werte `_Nblocks` und `_Nallocs` auf null.

## <a name="released"></a> max_variable_size::released

Verringert die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void released();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion verringert den gespeicherten `_Nblocks`-Wert. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wann immer ein Speicherblock aus der Freiliste entfernt wird.

## <a name="saved"></a> max_variable_size::saved

Erhöht die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void saved();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion inkrementiert den gespeicherten `_Nblocks`-Wert. Diese Memberfunktion wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
