---
title: max_none Class | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44981141be5bfb4f18cb278e724ab905aebcc5cf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964170"
---
# <a name="maxnone-class"></a>max_none-Klasse

Beschreibt ein Objekt der [max-Klasse](../standard-library/allocators-header.md), das ein [freelist](../standard-library/freelist-class.md)-Objekt auf eine maximale Länge begrenzt.

## <a name="syntax"></a>Syntax

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Max*|Die max-Klasse, die die maximale Anzahl von Elementen zum Speichern in der `freelist` bestimmt.|

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

## <a name="allocated"></a> max_none::allocated

Erhöht die Anzahl der zugeordneten Speicherblöcke.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*_Nx*|Der Inkrementwert|

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Sie wird aufgerufen, nach jedem erfolgreichen Aufruf von `cache_freelist::allocate` Operator **neue**. Das Argument *_Nx* ist die Anzahl der Speicherblöcke im Segment von Operator zugeordneten **neue**.

## <a name="deallocated"></a> max_none::deallocated

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

## <a name="full"></a> max_none::full

Gibt einen Wert zurück, der angibt, ob zur Freiliste weitere Speicherblöcke hinzugefügt werden sollen.

```cpp
bool full();
```

### <a name="return-value"></a>Rückgabewert

Diese Memberfunktion gibt immer zurück **"true"**.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird von `cache_freelist::deallocate` aufgerufen. Wenn der Aufruf zurückgegeben **"true"**, `deallocate` den Speicherblock der Freiliste hinzugefügt; versetzt, wenn "false" zurückgegeben `deallocate` Aufrufe Operator **löschen** beim Aufheben der Zuordnung des Blocks.

## <a name="released"></a> max_none::released

Verringert die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void released();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Die `released`-Memberfunktion der aktuellen max-Klasse wird von `cache_freelist::allocate` aufgerufen, wenn ein Speicherblock aus der Freiliste entfernt wird.

## <a name="saved"></a> max_none::saved

Erhöht die Anzahl der Speicherblöcke auf der Freiliste.

```cpp
void saved();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion bleibt untätig. Sie wird durch `cache_freelist::deallocate` aufgerufen, wann immer ein Speicherblock der Freiliste hinzugefügt wird.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
