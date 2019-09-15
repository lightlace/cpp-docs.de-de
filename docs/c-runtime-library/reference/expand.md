---
title: _expand
ms.date: 11/04/2016
api_name:
- _expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
ms.openlocfilehash: cb986d893bd862e61ae595317a890fb489c19919
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941559"
---
# <a name="_expand"></a>_expand

Ändert die Größe eines Speicherblocks.

## <a name="syntax"></a>Syntax

```C
void *_expand(
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

**_expand** gibt einen void-Zeiger auf den neu belegten Speicherblock zurück. **_expand**kann im Gegensatz zu **rezuzuweisungen**einen Block nicht verschieben, um seine Größe zu ändern. Wenn ausreichend Arbeitsspeicher verfügbar ist, um den Block zu erweitern, ohne ihn zu verschieben, ist der *memblock* -Parameter für **_expand** derselbe wie der Rückgabewert.

**_expand** gibt **null** zurück, wenn während des Vorgangs ein Fehler erkannt wird. Wenn z. b. **_expand** verwendet wird, um einen Speicherblock zu verkleinern, erkennt er möglicherweise Beschädigungen im kleinen blockheap oder einen ungültigen Block Zeiger und gibt **null**zurück.

Wenn nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die angegebene Größe auszudehnen, ohne ihn zu verschieben, gibt die Funktion **null**zurück. **_expand** gibt niemals einen Block zurück, der auf eine Größe kleiner als angefordert erweitert ist. Wenn ein Fehler auftritt, gibt **errno** die Art des Fehlers an. Weitere Informationen zu **errno**finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Verwenden Sie **_msize**, um die neue Größe des Elements zu überprüfen. Um einen Zeiger auf einen anderen Typ als **void**abzurufen, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **_expand** -Funktion ändert die Größe eines zuvor zugeordneten Speicherblocks, indem versucht wird, den Block zu erweitern oder zu verkleinern, ohne seine Position im Heap zu verschieben. Der *memblock* -Parameter verweist auf den Anfang des Blocks. Der *size* -Parameter gibt die neue Größe des Blocks in Bytes an. Der Inhalt des Blocks bleibt bis zum Minimum von neuer und alter Größe unverändert. *memblock* darf kein Block sein, der freigegeben wurde.

> [!NOTE]
> Auf 64-Bit-Plattformen kann **_expand** den Block ggf. nicht schrumpfen, wenn die neue Größe kleiner als die aktuelle Größe ist. insbesondere wenn der Block kleiner als 16K ist und daher im niedrigen Fragmentierungs Heap zugeordnet ist, lässt **_expand** den Block unverändert und gibt *memblock*zurück.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist, wird **_expand** in [_expand_dbg](expand-dbg.md)aufgelöst. Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

Diese Funktion überprüft ihre Parameter. Wenn *memblock* ein NULL-Zeiger ist, ruft diese Funktion einen Handler für ungültige Parameter auf, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktion gibt **null**zurück. Wenn die *Größe* größer als **_HEAP_MAXREQ**ist, wird **errno** auf **ENOMEM** festgelegt, und die Funktion gibt **null**zurück.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
