---
title: _query_new_handler
ms.date: 11/04/2016
apiname:
- _query_new_handler
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
- _query_new_handler
- query_new_handler
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
ms.openlocfilehash: febefbe46d95b7e5c8de026806a20d7eff74e7cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357876"
---
# <a name="querynewhandler"></a>_query_new_handler

Gibt die Adresse der aktuellen neuen Handlerroutine zurück.

## <a name="syntax"></a>Syntax

```C
_PNH _query_new_handler(
   void
);
```

## <a name="return-value"></a>Rückgabewert

Gibt die Adresse der aktuellen neuen Handlerroutine zurück, mit **_set_new_handler**.

## <a name="remarks"></a>Hinweise

Die C++ **_query_new_handler** Funktionsergebnis ist die Adresse der aktuellen ausnahmebehandlungsfunktion festlegen, indem die C++ [_set_new_handler](set-new-handler.md) Funktion. **_set_new_handler** wird verwendet, um eine Funktion für die Ausnahmebehandlung anzugeben, unter Kontrolle bringen, wenn die **neue** -Operator keine speicherbelegung vornehmen kann. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_query_new_handler**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
