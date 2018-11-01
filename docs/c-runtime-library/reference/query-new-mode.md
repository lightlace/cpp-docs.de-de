---
title: _query_new_mode
ms.date: 11/04/2016
apiname:
- _query_new_mode
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
- query_new_mode
- _query_new_mode
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
ms.openlocfilehash: 327f22c847793316bd126721b4a66846d7da84dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620024"
---
# <a name="querynewmode"></a>_query_new_mode

Gibt eine ganze Zahl, der angibt, der des neuen handlermodus festlegen, indem **_set_new_mode** für **Malloc**.

## <a name="syntax"></a>Syntax

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Rückgabewert

Gibt den aktuellen neuen handlermodus, nämlich 0 oder 1 für **Malloc**. Ein Rückgabewert 1 gibt an, dass bei einem Fehler bei der speicherbelegung **Malloc** Ruft die neue Handlerroutine; der Rückgabewert 0 gibt an, dass dies nicht der Fall.

## <a name="remarks"></a>Hinweise

Die C++ **_query_new_mode** Funktionsergebnis ist eine ganze Zahl, die der neue handlermodus gibt an, die von der C++ festgelegt ist [_set_new_mode](set-new-mode.md) für Funktion [Malloc](malloc.md). Der neue handlermodus gibt an, ob bei einem Fehler bei der speicherbelegung **Malloc** besteht darin, rufen Sie die neue Handlerroutine mit [_set_new_handler](set-new-handler.md). In der Standardeinstellung **Malloc** wird die neue Handlerroutine nicht bei einem Fehler aufgerufen. Können Sie **_set_new_mode** also dieses Verhalten zu überschreiben, die bei einem Fehler **"malloc"** die neue Handlerroutine aufruft, in der gleichen Weise die **neue** Operator ist, wenn ein Fehler auftritt, Speicher zuordnen. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.

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
