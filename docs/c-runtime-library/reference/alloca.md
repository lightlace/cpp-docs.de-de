---
title: _alloca
ms.date: 11/04/2016
apiname:
- _alloca
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
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 7c083e791301d3224709a5fc6c711ceaa6397d38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668072"
---
# <a name="alloca"></a>_alloca

Belegt Speicher für den Stapel. Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist. finden Sie unter [_malloca](malloca.md).

## <a name="syntax"></a>Syntax

```C
void *_alloca(
   size_t size
);
```

### <a name="parameters"></a>Parameter

*size*<br/>
Bytes, die vom Stapel zugeordnet werden.

## <a name="return-value"></a>Rückgabewert

Die **_alloca** -Routine gibt einen **"void"** Zeiger auf den zugewiesenen Speicherplatz, der für die Speicherung eines beliebigen Objekttyps geeignet. Wenn *Größe* ist 0 (null) **_alloca** weist ein Element der Länge 0 (null) und gibt einen gültigen Zeiger auf dieses Element zurück.

Eine Stapelüberlaufausnahme wird generiert, wenn der Speicherplatz nicht zugeordnet werden kann. Die Stapelüberlaufausnahme ist keine C++-Ausnahme, sondern eine strukturierte Ausnahme. Sie müssen anstelle der C++-Ausnahmebehandlung die [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) (Structured Exception Handling, SEH) verwenden.

## <a name="remarks"></a>Hinweise

**_alloca** ordnet *Größe* Bytes aus dem Programmstapel. Der zugewiesene Speicherplatz wird automatisch freigegeben, wenn die aufrufende Funktion beendet wird (nicht, wenn die Zuordnung lediglich außerhalb des gültigen Bereichs übergeben). Aus diesem Grund übergeben Sie keine der Zeigerwert zurückgegebenes **_alloca** als Argument an [kostenlose](free.md).

Es gibt Einschränkungen beim expliziten Aufruf **_alloca** in einem Ausnahmehandler (EH). EH-Routinen, die auf x86-Klasse-Prozessoren ausgeführt werden, arbeiten in ihrem eigenen Speicherrahmen: Sie führen Ihre Tasks im Speicherplatz aus, der nicht auf der aktuellen Position des Stapelzeigers der einschließenden Funktion basiert. Die am häufigsten verwendeten Implementierungen umfassen die strukturierte Windows NT-Ausnahmebehandlung (SEH) und C++-Catch-Klauselausdrücke. Aus diesem Grund explizit aufrufen **_alloca** in einem der folgenden Szenarien Ergebnisse in einem Programmfehler während an die aufrufende EH-Routine zurückgegeben:

- Windows NT-SEH-Ausnahme-Filterausdruck: `__except ( _alloca() )`

- Endgültige Ausnahmehandler von Windows NT-SEH: `__finally { _alloca() }`

- C++-EH-Catch-Klauselausdruck

Allerdings **_alloca** können direkt aufgerufen werden innerhalb einer EH-Routine oder von einer Anwendung bereitgestellten Rückruf, der aufgerufen wird, ruft einer der zuvor aufgeführten EH-Szenarios.

> [!IMPORTANT]
> In Windows XP Wenn **_alloca** wird aufgerufen, Sie müssen in einem Try/Catch-Block Aufrufen [_resetstkoflw](resetstkoflw.md) im Catch-Block.

Zusätzlich zu den oben genannten Einschränkungen kann bei Verwendung der[/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) Option **_alloca** kann nicht verwendet werden, **__except** Blöcke. Weitere Informationen finden Sie unter [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_alloca**|\<malloc.h>|

## <a name="example"></a>Beispiel

```C
// crt_alloca.c
// This program demonstrates the use of
// _alloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size = 1000;
    int     errcode = 0;
    void    *pData = NULL;

    // Note: Do not use try/catch for _alloca,
    // use __try/__except, since _alloca throws
    // Structured Exceptions, not C++ exceptions.

    __try {
        // An unbounded _alloca can easily result in a
        // stack overflow.
        // Checking for a size < 1024 bytes is recommended.
        if (size > 0 && size < 1024)
        {
            pData = _alloca( size );
            printf_s( "Allocated %d bytes of stack at 0x%p",
                      size, pData);
        }
        else
        {
            printf_s("Tried to allocate too many bytes.\n");
        }
    }

    // If an exception occured with the _alloca function
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_alloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf_s("Could not reset the stack!\n");
            _exit(1);
        }
    };
}
```

```Output
Allocated 1000 bytes of stack at 0x0012FB50
```

## <a name="see-also"></a>Siehe auch

[Speicherreservierung](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
[_malloca](malloca.md)<br/>
