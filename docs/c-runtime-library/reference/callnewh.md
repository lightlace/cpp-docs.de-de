---
title: _callnewh | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a40d8f621b7098618b9be3872620d5294013fbe3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393091"
---
# <a name="callnewh"></a>_callnewh

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

|Wert|Beschreibung|
|-----------|-----------------|
|0|Fehler: Entweder wurde kein neuer Handler installiert oder der neue Handler ist nicht aktiv.|
|1|Erfolg: Der neue Handler wurde installiert und ist aktiv. Die Speicherbelegung kann wiederholt werden.|

## <a name="exceptions"></a>Ausnahmen

Diese Funktion löst [bad_alloc](../../standard-library/bad-alloc-class.md) aus, wenn der *neue Handler* nicht gefunden werden kann.

## <a name="remarks"></a>Hinweise

Der *neue Handler* wird aufgerufen, wenn der [neue Operator](../../cpp/new-operator-cpp.md) die Speicherbelegung nicht erfolgreich durchführen kann. Der neue Handler initialisiert dann möglicherweise einige entsprechende Aktionen, z. B. die Freigabe des Speichers, sodass nachfolgende Belegungen erfolgreich sind.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>Siehe auch

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>
