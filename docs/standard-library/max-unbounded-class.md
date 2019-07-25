---
title: max_unbounded-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
ms.openlocfilehash: cea2f09837e5efc6969e4ab305d106b9c9728412
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447207"
---
# <a name="maxunbounded-class"></a>max_unbounded-Klasse

Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das ein [freelist](../standard-library/freelist-class.md)-Objekt nicht auf eine maximale Länge begrenzt.

## <a name="syntax"></a>Syntax

```cpp
class max_unbounded
```

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

## <a name="allocated"></a> max_unbounded::allocated

Erhöht die Anzahl der zugeordneten Speicherblöcke.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Sie wird nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` für den **New**-Operator aufgerufen. Das Argument *_Nx* ist die Anzahl der Speicherblöcke in dem Block, der von Operator **New**zugeordnet wird.

## <a name="deallocated"></a> max_unbounded::deallocated

Verringert die Anzahl der zugeordneten Speicherblöcke.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Diese Member-Funktion wird nach jedem Aufruf von `cache_freelist::deallocate` zum **Delete**-Operator aufgerufen. Das Argument *_Nx* gibt die Anzahl der Speicherblöcke in dem Block an, dessen Zuordnung durch den Operator **Delete**aufgehoben wird.

## <a name="full"></a> max_unbounded::full

Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.

```cpp
bool full();
```

### <a name="return-value"></a>Rückgabewert

Die Member-Funktion gibt immer **false**zurück.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf **true**zurückgibt `deallocate` , wird der Speicherblock in die freie Liste eingefügt; Wenn false zurück `deallocate` gegeben wird, ruft der Operator Delete auf, um den Block zu **Entfernen** .

## <a name="released"></a> max_unbounded::released

Verringert die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void released();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wann immer ein Speicherblock aus der Freiliste entfernt wird.

## <a name="saved"></a> max_unbounded::saved

Erhöht die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void saved();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Sie wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
