---
title: _query_new_handler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- query_new_handler function
- handler routines
- error handling
- _query_new_handler function
ms.assetid: 9a84b5c3-fe33-4c01-83a0-be87dc3ec518
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c59b12c57af4d8a3d40b1ced2ffdc2a2cb00bc1f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Gibt die Adresse des aktuellen neuen Handlerroutine Isolationstransaktionen gemäß **_set_new_handler**.

## <a name="remarks"></a>Hinweise

Die C++ **_query_new_handler** Funktion gibt die Adresse für die aktuelle festlegen, indem die C++-Ausnahmebehandlung-Funktion [_set_new_handler](set-new-handler.md) Funktion. **_set_new_handler** wird verwendet, um eine Funktion für die Ausnahmebehandlung anzugeben, wenn die Steuerung übernehmen die **neue** -Operator keine speicherbelegung vornehmen kann. Weitere Informationen finden Sie unter der Erläuterung [new and delete operators (Operatoren new und delete)](../../cpp/new-and-delete-operators.md) in der C++-Sprachreferenz.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_query_new_handler**|\<new.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
