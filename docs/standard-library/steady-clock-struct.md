---
title: steady_clock struct | Microsoft-Dokumentation
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5445379597c4fefcd657303a05c33b6509d54d2e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569897"
---
# <a name="steadyclock-struct"></a>steady_clock-Struktur

Stellt eine *stetige* Uhr.

## <a name="syntax"></a>Syntax

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Hinweise

Unter Windows `steady_clock` dient als Wrapper für die `QueryPerformanceCounter` Funktion.

Eine Uhr ist *monoton*, wenn der von einem ersten Aufruf von `now` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now` zurückgegeben wird. Eine Uhr ist *gleichmäßig*, wenn sie *monoton* und die Zeit zwischen den Teilstrichen konstant ist.

`high_resolution_clock` ist eine Typedef für `steady_clock`.

### <a name="public-typedefs"></a>Öffentliche typedefs

|name|Beschreibung|
|----------|-----------------|
|`steady_clock::duration`|Ein Synonym für `nanoseconds`in definierte \<Chrono >.|
|`steady_clock::period`|Ein Synonym für `nano`in definierte \<Verhältnis >.|
|`steady_clock::rep`|Ein Synonym für **lange** **lange**, der Typ, der verwendet wird, um die Anzahl von Zeiteinheiten in der enthaltenden Instanziierung von darstellen `duration`.|
|`steady_clock::time_point`|Ein Synonym für `chrono::time_point<steady_clock>`.|

## <a name="public-functions"></a>Öffentliche Funktionen

|Funktion|Beschreibung|
|--------------|-----------------|
|`now`|Gibt die aktuelle Uhrzeit als eine `time_point` Wert.|

## <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|`steady_clock::is_steady`|Ist `true`. Eine `steady_clock` ist *gleichmäßig*.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="see-also"></a>Siehe auch

- [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock-Struktur](../standard-library/system-clock-structure.md)
