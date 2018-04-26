---
title: realloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- realloc
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
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs:
- C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e81f0456fd436ddb0036e0aebd0f56697c1ac213
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="realloc"></a>realloc

Neubelegung von Arbeitsspeicherblöcken.

## <a name="syntax"></a>Syntax

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Parameter

*memblock*<br/>
Zeiger zum vorherigen belegten Speicherblock.

*size*<br/>
Neue Größe in Bytes.

## <a name="return-value"></a>Rückgabewert

**Realloc** gibt eine **"void"** Zeiger auf den neu belegten (und möglicherweise verschobenen) Speicherblock.

Wenn es nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die vorgegebene Größe auszudehnen, die ursprüngliche Blockgröße ist unverändert, und **NULL** zurückgegeben wird.

Wenn *Größe* ist 0 (null), und klicken Sie dann auf den Block verweist *Memblock* freigegeben wird; der Rückgabewert ist **NULL**, und *Memblock* bleibt zeigen Sie auf eine Freigegebene Block.

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um einen Zeiger auf einem Typ außer **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **Realloc** Funktion ändert die Größe eines belegten Blocks. Die *Memblock* Argument verweist auf den Anfang des Speicherblocks. Wenn *Memblock* ist **NULL**, **Realloc** verhält sich genauso wie **"malloc"** und ordnet einen neuen Block *Größe*Bytes. Wenn *Memblock* nicht **NULL**, es muss ein Zeiger von einem vorherigen Aufruf zurückgegebene **Calloc**, **"malloc"**, oder **Realloc** .

Die *Größe* Argument gibt die neue Größe des Blocks in Bytes an. Der Inhalt des Blocks bleibt bis zum Minimum von neuer und alter Größe unverändert, obwohl sich der neue Block an einem anderen Speicherort befinden kann. Da in einem neuen Speicherort des neuen Blocks sein kann, der zurückgegebene Zeiger durch **Realloc** ist nicht unbedingt der Zeiger übergeben der *Memblock* Argument. **Realloc** ist nicht 0 (null) neu Arbeitsspeicher belegt bei Puffer Wachstum.

**Realloc** legt **Errno** auf **ENOMEM** , wenn die speicherbelegung fehlschlägt oder wenn die Größe des Arbeitsspeichers größer ist als **_HEAP_MAXREQ**. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**Realloc** Aufrufe **"malloc"** um die c++ [_set_new_mode](set-new-mode.md) -Funktion zum Festlegen der neue handlermodus. Der neue handlermodus gibt an, ob bei einem Fehler **"malloc"** ist, rufen Sie die neue Handlerroutine Isolationstransaktionen gemäß [_set_new_handler](set-new-handler.md). Standardmäßig **"malloc"** auf bei einem speicherbelegungsfehler nicht die neue Handlerroutine aufgerufen. Sie können dieses Standardverhalten überschreiben, damit, wenn **Realloc** Arbeitsspeicher nicht belegen kann **"malloc"** die neue Handlerroutine genauso aufruft wie der **neue** Operator ist. Wenn dieser aus demselben Grund fehlschlägt. Um den Standardwert zu überschreiben, rufen Sie

```C
_set_new_mode(1);
```

rechtzeitig im Programm auf, oder stellen Sie eine Verknüpfung mit NEWMODE.OBJ (siehe [Linkoptionen](../../c-runtime-library/link-options.md)) her.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **Realloc** löst in [_realloc_dbg](realloc-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

**Realloc** RuntimeCompatibility `__declspec(noalias)` und `__declspec(restrict)`, was bedeutet, dass die Funktion wird sichergestellt, dass keine globalen Variablen zu ändern, und dass der zurückgegebene Zeiger nicht als Alias ist. Weitere Informationen finden Sie unter [noalias](../../cpp/noalias.md) und [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**realloc**|\<stdlib.h> und \<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
