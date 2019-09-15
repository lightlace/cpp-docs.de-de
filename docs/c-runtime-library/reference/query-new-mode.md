---
title: _query_new_mode
ms.date: 11/04/2016
api_name:
- _query_new_mode
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
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 59724dafdc6488596478d0b44b254c4f498fce99
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70950115"
---
# <a name="_query_new_mode"></a>_query_new_mode

Gibt eine ganze Zahl zurück, die den von **_set_new_mode** für **malloc**festgelegten neuen handlermodus angibt.

## <a name="syntax"></a>Syntax

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Rückgabewert

Gibt den aktuellen neuen handlermodus für **malloc**zurück, nämlich 0 oder 1. Der Rückgabewert 1 gibt an, dass **malloc** bei einem Fehler beim Zuordnen von Arbeitsspeicher die neue Handlerroutine aufruft. der Rückgabewert 0 gibt an, dass dies nicht der Fall ist.

## <a name="remarks"></a>Hinweise

Die C++ **_query_new_mode** -Funktion gibt eine ganze Zahl zurück, die den neuen handlermodus angibt C++ , der von der [_set_new_mode](set-new-mode.md) -Funktion für [malloc](malloc.md)festgelegt wird. Der neue handlermodus gibt an, ob bei einem Fehler beim Zuweisen von Arbeitsspeicher **malloc** die neue Handlerroutine aufrufen soll, wie von [_set_new_handler](set-new-handler.md)festgelegt. Standardmäßig ruft **malloc** die neue Handlerroutine bei einem Fehler nicht auf. Sie können **_set_new_mode** verwenden, um dieses Verhalten zu überschreiben, sodass bei einem Fehler **malloc** die neue Handlerroutine auf die gleiche Weise aufgerufen wird, die der **neue** Operator beim Zuordnen von Arbeitsspeicher vornimmt. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_query_new_mode**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
