---
title: sync_per_container-Klasse
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 641595f663c382129a40ce503ebdb789f8042cf0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412162"
---
# <a name="syncpercontainer-class"></a>sync_per_container-Klasse

Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), der für jedes Zuweisungsobjekt ein getrenntes Cache-Objekt bereitstellt.

## <a name="syntax"></a>Syntax

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Cache*|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dieser kann [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) oder [cache_suballoc](../standard-library/cache-suballoc-class.md) sein.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|

## <a name="requirements"></a>Anforderungen

**Header:** \<allocators>

**Namespace:** stdext

## <a name="equals"></a> sync_per_container::equals

Vergleicht zwei Caches auf Gleichheit.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Cache*|Das Cache-Objekt des Synchronisierungsfilters.|
|*Andere*|Das Cache-Objekt, das auf Gleichheit verglichen werden soll.|

### <a name="return-value"></a>Rückgabewert

Die Memberfunktion gibt immer zurück **"false"**.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)<br/>
