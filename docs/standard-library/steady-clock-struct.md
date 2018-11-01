---
title: steady_clock-Struktur
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 19e9f5c4dcfc7306b989605894e9a0787e0920ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579295"
---
# <a name="steadyclock-struct"></a>steady_clock-Struktur

Stellt eine *stetige* Uhr.

## <a name="syntax"></a>Syntax

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Hinweise

Auf Windows `steady_clock` dient als Wrapper für die `QueryPerformanceCounter` Funktion.

Eine Uhr ist *monoton*, wenn der von einem ersten Aufruf von `now` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now` zurückgegeben wird. Eine Uhr ist *gleichmäßig*, wenn sie *monoton* und die Zeit zwischen den Teilstrichen konstant ist.

`high_resolution_clock` eine typedef für `steady_clock`.

### <a name="public-typedefs"></a>Öffentliche typedefs

|name|Beschreibung|
|----------|-----------------|
|`steady_clock::duration`|Ein Synonym für `nanoseconds`, definiert in \<Chrono >.|
|`steady_clock::period`|Ein Synonym für `nano`, definiert in \<Ratio >.|
|`steady_clock::rep`|Ein Synonym für **lange** **lange**, der Typ, der verwendet wird, zum Darstellen der Anzahl von Zeiteinheiten in der enthaltenden Instanziierung von `duration`.|
|`steady_clock::time_point`|Ein Synonym für `chrono::time_point<steady_clock>`.|

## <a name="public-functions"></a>Öffentliche Funktionen

|Funktion|Beschreibung|
|--------------|-----------------|
|`now`|Gibt die aktuelle Uhrzeit als eine `time_point` Wert.|

## <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|`steady_clock::is_steady`|Enthält **"true"**. Eine `steady_clock` ist *gleichmäßig*.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="see-also"></a>Siehe auch

- [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock-Struktur](../standard-library/system-clock-structure.md)
