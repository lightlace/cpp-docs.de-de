---
title: _set_new_mode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_new_mode
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
- set_new_mode
- _set_new_mode
dev_langs:
- C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b914e950fd94435768c355f327d3d48a653e0d5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407144"
---
# <a name="setnewmode"></a>_set_new_mode

Legt einen neuen handlermodus für **"malloc"**.

## <a name="syntax"></a>Syntax

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parameter

*newhandlermode*<br/>
Neuen handlermodus für **"malloc"**; gültige Wert ist 0 oder 1.

## <a name="return-value"></a>Rückgabewert

Gibt den vorherigen Handler Modus Satz für **"malloc"**. Ein Rückgabewert Wert 1 gibt an, auf Fehler beim Zuweisen von Arbeitsspeicher, **"malloc"** vorher: die neue Handlerroutine; ein Rückgabewert von 0 gibt an, dass dies nicht der Fall. Wenn die *Newhandlermode* Argument stimmt nicht mit 0 oder 1, wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die C++-Funktion **_set_new_mode** legt den neuen Handlermodus für [malloc](malloc.md) fest. Der neue handlermodus gibt an, ob bei einem Fehler **"malloc"** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß [_set_new_handler](set-new-handler.md). Standardmäßig **"malloc"** auf bei einem speicherbelegungsfehler nicht die neue Handlerroutine aufgerufen. Sie können dieses Standardverhalten überschreiben, damit, wenn **"malloc"** Arbeitsspeicher nicht belegen kann **"malloc"** die neue Handlerroutine genauso aufruft wie der **neue** Operator ist. Wenn dieser aus demselben Grund fehlschlägt. Weitere Informationen finden Sie unter den Operatoren [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*. Um den Standardwert zu überschreiben, rufen Sie

```cpp
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj (siehe [Link Options (Linkoptionen)](../../c-runtime-library/link-options.md)) her.

Diese Funktion überprüft seine Parameter. Wenn *Newhandlermode* wird alles außer 0 oder 1, um die Funktion wird den Handler für ungültige Parameter, als aufgerufen im beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **_ *** Set_new_mode** gibt-1 zurück und legt **Errno** auf **EINVAL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>
