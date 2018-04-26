---
title: _query_new_mode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- query_new_mode function
- handler modes
- _query_new_mode function
ms.assetid: e185c5f9-b73b-4257-8eff-b47648374768
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 67a7b52bc2a16e5c87e6ba83c3ba9c2710c2ed88
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="querynewmode"></a>_query_new_mode

Gibt eine ganze Zahl, der angibt, die vom festgelegten neuen handlermodus **_set_new_mode** für **"malloc"**.

## <a name="syntax"></a>Syntax

```C
int _query_new_mode(
   void
);
```

## <a name="return-value"></a>Rückgabewert

Gibt den aktuellen neuen handlermodus, nämlich 0 oder 1 für **"malloc"**. Ein Rückgabewert Wert 1 gibt an, auf Fehler beim Zuweisen von Arbeitsspeicher, **"malloc"** Ruft die neue Handlerroutine; ein Rückgabewert von 0 gibt an, dass dies nicht der Fall.

## <a name="remarks"></a>Hinweise

Die C++ **_query_new_mode** Funktion gibt eine ganze Zahl, die der neue handlermodus gibt an, die von der C++ festgelegt ist [_set_new_mode](set-new-mode.md) für Funktion ["malloc"](malloc.md). Der neue handlermodus gibt an, ob bei Fehler beim Zuweisen von Arbeitsspeicher, **"malloc"** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß [_set_new_handler](set-new-handler.md). Standardmäßig **"malloc"** bei einem Fehler nicht die neue Handlerroutine aufgerufen. Können Sie **_set_new_mode** also dieses Verhalten überschreiben, die bei einem Fehler **"malloc"** die neue Handlerroutine genauso aufruft wie der **neue** Operator wird bei einem auf Reservieren Sie Arbeitsspeicher. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
