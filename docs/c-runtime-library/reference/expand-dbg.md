---
title: _expand_dbg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _expand_dbg
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
apitype: DLLExport
f1_keywords:
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b8fc9db941700542d82b2a1a1449aafc0375fbf6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="expanddbg"></a>_expand_dbg

Ändert die Größe eines angegebenen Speicherblocks im Heap durch Erweitern oder Verkürzen des Blocks (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void *_expand_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*Benutzerdaten*<br/>
Zeiger zum vorherigen belegten Speicherblock.

*newSize*<br/>
Angeforderte neue Größe des Blocks (in Bytes).

*blockType*<br/>
Angeforderter Typ für vergrößerten/verkleinerten Block: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die angefordert hat die Erweiterung oder **NULL**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in dem die Erweiterung angefordert wurde, oder **NULL**.

Die *Filename* und *Linenumber* -Parameter sind nur verfügbar, wenn **_expand_dbg** explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)-Präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Bei erfolgreichem Abschluss **_expand_dbg** gibt einen Zeiger auf die vergrößerten/verkleinerten Speicherblock zurück. Da der Speicher nicht verschoben wird, ist die Adresse identisch mit "userData". Wenn ein Fehler aufgetreten, oder der Block nicht auf die angeforderte Größe erweitert werden konnte, wird **NULL**. Wenn ein Fehler auftritt, **Errno** mit Informationen des Betriebssystems über die Art des Fehlers ist. Weitere Informationen zu **Errno**, finden Sie unter [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_expand_dbg** Funktion ist eine Debugversion der _[erweitern](expand.md) Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, bei jedem Aufruf **_expand_dbg** wird zu einem Aufruf von reduziert **_vorhandenen Standort erweitern**. Beide **_vorhandenen Standort erweitern** und **_expand_dbg** ändern Sie die Größe eines Speicherblocks im Basisheap, jedoch **_expand_dbg** hat mehrere Debugfunktionen: Puffer auf beiden Seiten des Benutzers Teil des Blocks zum Prüfen auf Speicherverluste, einen blocktypparameter zum Nachverfolgen von bestimmten belegungstypen und *Filename*/*Linenumber* Informationen zum Ermitteln des Ursprungs von belegungsanforderungen.

**_expand_dbg** ändert die Größe des angegebene Speicherblocks mit etwas mehr Speicherplatz als der angeforderten *NewSize*. *NewSize* möglicherweise größer oder kleiner als die Größe des ursprünglich belegten Speicherblocks. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Die Größenänderung wird erreicht, indem der ursprüngliche Speicherblock erweitert oder verkürzt wird. **_expand_dbg** ändert nicht den Speicherblock, wie die [_realloc_dbg](realloc-dbg.md) Funktion.

Wenn *NewSize* ist größer als der ursprüngliche Block, der Speicherblock erweitert wird. Während einer Erweiterung, wenn der Speicherblock erweitert werden kann, um die angeforderte Größe erweitert **NULL** zurückgegeben wird. Wenn *NewSize* ist kleiner als der ursprüngliche Block Größe der Speicherblock verkürzt, bis die neue Größe erreicht ist.

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Informationen zu den Belegungsblocktypen und ihrer Verwendung finden Sie unter [Blocktypen auf dem Debugheap](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Diese Funktion überprüft ihre Parameter. Wenn *Memblock* ein null-Zeiger ist oder wenn Größe übersteigt **_HEAP_MAXREQ**, ruft diese Funktion einen Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktion gibt **NULL**.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>Kommentar

Die Ausgabe dieses Programms hängt von der Funktionalität des Computers ab, ob alle Abschnitte erweitert werden können. Wenn alle Abschnitte erweitert wurden, wird die Ausgabe im Ausgabeabschnitt wiedergegeben.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
