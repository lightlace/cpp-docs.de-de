---
title: _callnewh
ms.date: 11/04/2016
apiname:
- _callnewh
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 98526f6c8c40b71104345563db71ef098b6cfb8d
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739826"
---
# <a name="_callnewh"></a>_callnewh

Ruft den aktuell installierten *neuen Handler* auf.

## <a name="syntax"></a>Syntax

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>Parameter

*size*<br/>
Der Speicherplatz, den der [neue Operator](../../cpp/new-operator-cpp.md) zu belegen versucht hat.

## <a name="return-value"></a>Rückgabewert

|Wert|Description|
|-----------|-----------------|
|0|Fehler Entweder ist kein neuer Handler installiert, oder es ist kein neuer Handler aktiv.|
|1|Erfolglos Der neue Handler ist installiert und aktiv. Die Speicherbelegung kann wiederholt werden.|

## <a name="exceptions"></a>Ausnahmen

Diese Funktion löst [bad_alloc](../../standard-library/bad-alloc-class.md) aus, wenn der *neue Handler* nicht gefunden werden kann.

## <a name="remarks"></a>Hinweise

Der *neue Handler* wird aufgerufen, wenn der [neue Operator](../../cpp/new-operator-cpp.md) die Speicherbelegung nicht erfolgreich durchführen kann. Der neue Handler initialisiert dann möglicherweise einige entsprechende Aktionen, z. B. die Freigabe des Speichers, sodass nachfolgende Belegungen erfolgreich sind.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>Siehe auch

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
