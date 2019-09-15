---
title: _set_new_mode
ms.date: 11/04/2016
api_name:
- _set_new_mode
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: b248f1c97b1ec334b7441f33862b90473e08993f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948445"
---
# <a name="_set_new_mode"></a>_set_new_mode

Legt einen neuen handlermodus für **malloc**fest.

## <a name="syntax"></a>Syntax

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>Parameter

*newhandlermode*<br/>
Neuer handlermodus für **malloc**; der gültige Wert ist 0 oder 1.

## <a name="return-value"></a>Rückgabewert

Gibt den vorherigen handlermodus für **malloc**zurück. Der Rückgabewert 1 gibt an, dass bei einem Speicher Belegungs Fehler **malloc** zuvor als neue Handlerroutine bezeichnet wurde. der Rückgabewert 0 gibt an, dass dies nicht der Fall war. Wenn das Argument " *netwhandlermode* " nicht gleich 0 oder 1 ist, wird-1 zurückgegeben.

## <a name="remarks"></a>Hinweise

Die C++-Funktion **_set_new_mode** legt den neuen Handlermodus für [malloc](malloc.md) fest. Der neue handlermodus gibt an, ob **malloc** bei einem Fehler die neue Handlerroutine aufrufen soll, wie von [_set_new_handler](set-new-handler.md)festgelegt. Standardmäßig ruft **malloc** die neue Handlerroutine nicht bei einem Fehler auf, um Arbeitsspeicher zuzuweisen. Sie können dieses Standardverhalten außer Kraft setzen, sodass, wenn **malloc** keinen Arbeitsspeicher zuordnen kann, die neue Handlerroutine von **malloc** auf die gleiche Weise aufgerufen wird wie der **neue** Operator, wenn dieser aus demselben Grund fehlschlägt. Weitere Informationen finden Sie unter den Operatoren [new](../../cpp/new-operator-cpp.md) und [delete](../../cpp/delete-operator-cpp.md) in der *C++-Sprachreferenz*. Um den Standardwert zu überschreiben, rufen Sie

```cpp
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit Newmode.obj (siehe [Link Options (Linkoptionen)](../../c-runtime-library/link-options.md)) her.

Diese Funktion überprüft seine Parameter. Wenn " *nwhandlermode* " etwas anderes als "0" oder "1" ist, ruft die Funktion den Handler für ungültige Parameter auf, wie unter [Parameter Validierung](../../c-runtime-library/parameter-validation.md)beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt <strong>_set_new_mode</strong> den Wert-1 zurück und legt `EINVAL` **errno** auf fest.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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
