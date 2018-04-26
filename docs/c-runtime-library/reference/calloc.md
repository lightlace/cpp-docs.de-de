---
title: calloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- calloc
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
- calloc
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e755be214542dc4a601ad5e0f1d4aa02201dd552
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="calloc"></a>calloc

Ordnet ein Array im Arbeitsspeicher mit Elementen an, die auf 0 initialisiert sind.

## <a name="syntax"></a>Syntax

```C
void *calloc(
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Parameter

*Anzahl*<br/>
Anzahl der Elemente.

*size*<br/>
Länge jedes Elements in Bytes.

## <a name="return-value"></a>Rückgabewert

**Calloc** gibt einen Zeiger auf den zugewiesenen Speicherplatz. Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einem Typ außer **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **Calloc** Funktion reserviert Speicherplatz für ein Array von *Anzahl* Elementen, von denen jedes Länge *Größe* Bytes. Jedes Element wird auf 0 initialisiert.

**Calloc** legt **Errno** auf **ENOMEM** , wenn eine speicherbelegung fehlschlägt oder wenn die Größe des Arbeitsspeichers größer ist als **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**Calloc** Aufrufe **"malloc"** verwendet die C++ [_set_new_mode](set-new-mode.md) -Funktion zum Festlegen der neue handlermodus. Der neue handlermodus gibt an, ob bei einem Fehler **"malloc"** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß [_set_new_handler](set-new-handler.md). Standardmäßig **"malloc"** auf bei einem speicherbelegungsfehler nicht die neue Handlerroutine aufgerufen. Sie können dieses Standardverhalten überschreiben, damit, wenn **Calloc** Arbeitsspeicher nicht belegen kann **"malloc"** die neue Handlerroutine genauso aufruft wie der **neue** Operator ist. Wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie

```C
_set_new_mode(1);
```

rechtzeitig im Programm auf oder stellen eine Verknüpfung mit NEWMODE.OBJ her (siehe [Link Options (Linkoptionen)](../../c-runtime-library/link-options.md)).

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **Calloc** löst in [_calloc_dbg](calloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**Calloc** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`, was bedeutet, dass die Funktion wird sichergestellt, dass keine globalen Variablen zu ändern, und dass der zurückgegebene Zeiger nicht als Alias ist. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**calloc**|\<stdlib.h> und \<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
