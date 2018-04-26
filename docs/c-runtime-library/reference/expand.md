---
title: _expand | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f55b7e3c321ff4a86464fab39313abbe742d77d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

**_vorhandenen Standort erweitern** gibt einen void-Zeiger auf den neu belegten Speicherblock zurück. **_vorhandenen Standort erweitern**sind im Gegensatz zum **Realloc**, einen Block so ändern Sie die Größe kann nicht verschoben werden. Daher, wenn es genügend Arbeitsspeicher verfügbar, um den Block zu erweitern, ohne zu verschieben, die *Memblock* Parameter **_vorhandenen Standort erweitern** entspricht der zurückgegebene Wert.

**_vorhandenen Standort erweitern** gibt **NULL** Wenn ein Fehler während des Betriebs erkannt wird. Z. B. wenn **_vorhandenen Standort erweitern** wird verwendet, um einen Speicherblock zu verkleinern, kann dies eine Beschädigung in kleinen Codeblock Heap oder ein ungültiger Block Zeiger erkennen und zurück **NULL**.

Wenn es nicht genügend Arbeitsspeicher verfügbar ist, um den Block auf die vorgegebene Größe auszudehnen, ohne diesen zu bewegen, gibt die Funktion **NULL**. **_vorhandenen Standort erweitern** gibt nie erweitert, um eine Größe kleiner als angeforderte ein Blocks zurück. Wenn ein Fehler auftritt, **Errno** die Art des Fehlers angibt. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Der Rückgabewert zeigt auf einen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet ist. Um die neue Größe des Elements zu überprüfen, verwenden Sie **_msize**. Um einen Zeiger auf einem Typ außer **"void"**, verwenden Sie eine Typumwandlung für den Rückgabewert.

## <a name="remarks"></a>Hinweise

Die **_vorhandenen Standort erweitern** -Funktion ändert die Größe des vorherigen belegten Speicherblock durch Erweitern oder Verkleinern des Blocks ohne dessen Speicherort im Heap verschieben möchten. Die *Memblock* Parameter verweist auf den Anfang des Blocks. Die *Größe* Parameter gibt die neue Größe des Blocks in Bytes an. Der Inhalt des Blocks bleibt bis zum Minimum von neuer und alter Größe unverändert. *Memblock* muss sich nicht auf ein Block, der freigegeben wurde.

> [!NOTE]
> Auf 64-Bit-Plattformen **_vorhandenen Standort erweitern** den Block kann keinen Vertrag, wenn die neue Größe kleiner als die aktuelle Größe; insbesondere, ist wenn der Block Größe von weniger als 16 KB wurde und daher in der niedrige Heap-Fragmentierung, belegt **_vorhandenen Standort erweitern**  verlässt den Block nicht geändert, und gibt *Memblock*.

Wenn die Anwendung mit einer Debugversion der C-Laufzeitbibliotheken verknüpft ist **_vorhandenen Standort erweitern** löst in [_expand_dbg](expand-dbg.md). Weitere Informationen dazu, wie der Heap während des Debugprozesses verwaltet wird, finden Sie unter [CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

Diese Funktion überprüft ihre Parameter. Wenn *Memblock* ist ein null-Zeiger, ruft diese Funktion einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt **NULL**. Wenn *Größe* ist größer als **_HEAP_MAXREQ**, **Errno** festgelegt ist, um **ENOMEM** und die Funktion gibt **NULL**.

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
