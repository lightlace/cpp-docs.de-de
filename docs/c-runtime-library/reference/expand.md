---
title: _expand
ms.date: 11/04/2016
apiname:
- _expand
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
ms.openlocfilehash: c1606bedbb1264bddb7674c829fe456f506d6584
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335203"
---
# <a name="expand"></a>_expand

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

**_expand** gibt einen void-Zeiger auf den neu belegten Speicherblock zurück. **_expand**anders als beim **Realloc**, einen Block, um die Änderung der Größe kann nicht verschoben werden. Also, wenn genügend Arbeitsspeicher verfügbar, um den Block auszudehnen, ohne zu verschieben, die *Memblock* Parameter **_expand** entspricht der zurückgegebene Wert.

**_expand** gibt **NULL** Wenn während des Vorgangs ein Fehler erkannt wird. Z. B. wenn **_expand** wird verwendet, um einen Speicherblock zu verkleinern, können sie erkennen eine Beschädigung im kleinen blockheap oder ein ungültiger blockzeiger und zurückgibt **NULL**.

Wenn es nicht genügend Arbeitsspeicher verfügbar ist, um den Block an die angegebene Größe auszudehnen, ohne ihn zu verschieben, gibt die Funktion **NULL**. **_expand** gibt einen Block nie erweitert auf eine Größe kleiner als angeforderte zurück. Wenn ein Fehler auftritt, **Errno** die Art des Fehlers angibt. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um die neue Größe des Elements zu überprüfen, verwenden Sie **_msize**. Um einen Zeiger auf einem Typ als **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **_expand** -Funktion ändert die Größe von einer vorherigen belegten Speicherblock, indem Sie versuchen, erweitern oder verkleinern den Block ohne Verschieben seiner Position im Heap. Die *Memblock* Parameter verweist auf den Anfang des Blocks. Die *Größe* Parameter gibt die neue Größe des Blocks in Bytes. Der Inhalt des Blocks bleibt bis zum Minimum von neuer und alter Größe unverändert. *Memblock* sollte sich nicht auf ein Block, der freigegeben wurde.

> [!NOTE]
> Auf 64-Bit-Plattformen **_expand** den Block kann keinen Vertrag, wenn die neue Größe kleiner als die aktuelle Größe ist; insbesondere, ist wenn der Block Größe kleiner als 16K war und daher die niedrige Heap-Fragmentierung, zugeordnet **_expand**  verlässt den Block nicht und gibt *Memblock*.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **_expand** löst in [_expand_dbg](expand-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

Diese Funktion überprüft ihre Parameter. Wenn *Memblock* ist ein null-Zeiger ruft diese Funktion einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktion gibt **NULL**. Wenn *Größe* ist größer als **_HEAP_MAXREQ**, **Errno** nastaven NA hodnotu **ENOMEM** und die Funktion gibt **NULL**.

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
