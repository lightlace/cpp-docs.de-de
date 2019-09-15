---
title: _calloc_dbg
ms.date: 11/04/2016
api_name:
- _calloc_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _calloc_dbg
- calloc_dbg
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
ms.openlocfilehash: eab17348e473a4f642e784defe4569e0e799299e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939320"
---
# <a name="_calloc_dbg"></a>_calloc_dbg

Belegt einige Speicherblöcke im Heap mit zusätzlichem Speicherplatz für einen Debugheader und Überschreibungspuffer (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void *_calloc_dbg(
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parameter

*number*<br/>
Angeforderte Anzahl von Speicherblöcken.

*size*<br/>
Angeforderte Größe eines Speicherblocks (Bytes).

*blockType*<br/>
Angeforderter Typ des Speicherblocks: **_CLIENT_BLOCK** oder **_NORMAL_BLOCK**.

Weitere Informationen zu den Zuordnungsblocktypen und ihrer Verwendung finden Sie unter [Types of Blocks on the Debug Heap (Blocktypen auf dem Debugheap)](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Zeiger auf den Namen der Quelldatei, die den Zuordnungs Vorgang angefordert hat, oder **null**.

*linenumber*<br/>
Zeilennummer in der Quelldatei, in der der Zuordnungs Vorgang angefordert wurde, oder **null**.

Die Parameter " *filename* " und " *LineNumber* " sind nur verfügbar, wenn " **_calloc_dbg** " explizit aufgerufen wurde oder die [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) -präprozessorkonstante definiert wurde.

## <a name="return-value"></a>Rückgabewert

Nach erfolgreichem Abschluss gibt diese Funktion einen Zeiger auf den Benutzer Teil des zuletzt belegten Speicherblocks zurück, ruft die neue Handlerfunktion auf oder gibt **null**zurück. Eine vollständige Beschreibung des Rückgabeverhaltens finden Sie im Abschnitt "Hinweise". Weitere Informationen zur Verwendung der neuen Handlerfunktion finden Sie unter der [calloc](calloc.md)-Funktion.

## <a name="remarks"></a>Hinweise

**_calloc_dbg** ist eine Debugversion der [czuzuordnen](calloc.md) -Funktion. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, wird jeder **_calloc_dbg** -Rückruf auf einen **czuzuordnen**-Befehl reduziert. Sowohl **calloc** als auch _calloc_dbg *weisen Speicherblöcke* im Basisheap zu, **_calloc_dbg** bietet jedoch mehrere Debugfunktionen:

- Puffer auf beiden Seiten des Benutzerteils des Blocks zum Prüfen auf Speicherverluste.

- Blocktypparameter zum Nachverfolgen von bestimmten Belegungstypen.

- *Dateiname*/:*LineNumber* -Informationen zum Ermitteln des Ursprungs von Zuordnungs Anforderungen.

**_calloc_dbg** ordnet jeden Speicherblock mit etwas mehr Speicherplatz als die angeforderte *Größe*zu. Der zusätzliche Speicherplatz wird vom Debugheapmanager verwendet, um die Debugspeicherblöck zu verknüpfen und Debugheaderinformationen und Überschreibungspuffer für die Anwendung bereitzustellen. Wenn der Block belegt wurde, wird der Benutzerteil des Blocks mit dem Wert "0xCD" gefüllt, und jeder der Überschreibungspuffer wird mit "0xFD" gefüllt.

**_calloc_dbg** legt **errno** auf **den** Wert fest, wenn eine Speicher Belegung fehlschlägt. " **EINVAL** " wird zurückgegeben, wenn der benötigte Speicherplatz (einschließlich des bereits erwähnten Mehraufwands) **_HEAP_MAXREQ**überschreitet. Informationen hierzu und über andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen zu den Unterschieden zwischen dem Aufruf einer Standardheapfunktion und der Debugversion in einem Debugbuild einer Anwendung finden Sie unter [Debugversionen von Heapreservierungsfunktionen](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_calloc_dbg**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_callocd.c
// This program uses _calloc_dbg to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>
#include <crtdbg.h>

int main( void )
{
    long *bufferN, *bufferC;

    // Call _calloc_dbg to include the filename and line number
    // of our allocation request in the header and also so we can
    // allocate CLIENT type blocks specifically
    bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );
    bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );
    if( bufferN != NULL && bufferC != NULL )
        printf( "Allocated memory successfully\n" );
    else
        printf( "Problem allocating memory\n" );

    / _free_dbg must be called to free CLIENT type blocks
    free( bufferN );
    _free_dbg( bufferC, _CLIENT_BLOCK );
}
```

```Output
Allocated memory successfully
```

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[calloc](calloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
