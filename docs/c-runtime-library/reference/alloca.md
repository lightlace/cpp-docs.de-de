---
title: _alloca
ms.date: 11/04/2016
api_name:
- _alloca
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
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 2212f9e40c78932b63eebfc221ad2f07fa3d3f9d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943698"
---
# <a name="_alloca"></a>_alloca

Belegt Speicher für den Stapel. Diese Funktion ist veraltet, da eine sicherere Version verfügbar ist. siehe [_malloca](malloca.md).

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

Die **_alloca** -Routine gibt einen **void** -Zeiger auf den zugeordneten Speicherplatz zurück, der für die Speicherung eines beliebigen Objekt Typs geeignet ist. Wenn *size* gleich 0 ist, ordnet **_alloca** ein Element der Länge 0 zu und gibt einen gültigen Zeiger auf dieses Element zurück.

Eine Stapelüberlaufausnahme wird generiert, wenn der Speicherplatz nicht zugeordnet werden kann. Die Stapelüberlaufausnahme ist keine C++-Ausnahme, sondern eine strukturierte Ausnahme. Sie müssen anstelle der C++-Ausnahmebehandlung die [Strukturierte Ausnahmebehandlung](../../cpp/structured-exception-handling-c-cpp.md) (Structured Exception Handling, SEH) verwenden.

## <a name="remarks"></a>Hinweise

**_alloca** ordnet die *Größe* von Bytes aus dem Programm Stapel zu. Der zugewiesene Speicherplatz wird automatisch freigegeben, wenn die aufrufende Funktion beendet wird (nicht, wenn die Zuordnung lediglich den Gültigkeitsbereich verlässt). Übergeben Sie daher den von **_alloca** zurückgegebenen Zeiger Wert nicht als Argument an [Free](free.md).

Es gibt Einschränkungen beim expliziten Aufrufen von **_alloca** in einem Ausnahmehandler (eh). EH-Routinen, die auf x86-Klassen-Prozessoren ausgeführt werden, arbeiten in Ihrem eigenen Arbeitsspeicher Rahmen: Sie führen ihre Aufgaben im Speicherbereich aus, der nicht auf dem aktuellen Speicherort des Stapel Zeigers der einschließenden Funktion basiert. Die am häufigsten verwendeten Implementierungen umfassen die strukturierte Windows NT-Ausnahmebehandlung (SEH) und C++-Catch-Klauselausdrücke. Daher führt das explizite Aufrufen von **_alloca** in einem der folgenden Szenarien zu einem Programmfehler während der Rückgabe an die aufrufenden eh-Routine:

- Ausnahme Filter Ausdruck für Windows NT-SEH:`__except ( _alloca() )`

- Abschließender Ausnahmehandler für Windows NT SEH:`__finally { _alloca() }`

- C++-EH-Catch-Klauselausdruck

**_Alloca** kann jedoch direkt innerhalb einer eh-Routine oder von einem von der Anwendung bereitgestellten Rückruf aufgerufen werden, der von einem der zuvor aufgelisteten eh-Szenarien aufgerufen wird.

> [!IMPORTANT]
> Wenn in Windows XP **_alloca** innerhalb eines try/catch-Blocks aufgerufen wird, müssen Sie [_resetstkoflw](resetstkoflw.md) im catch-Block aufrufen.

Zusätzlich zu den oben genannten Einschränkungen kann **_alloca** nicht in **__except** -Blöcken verwendet werden, wenn die Option[/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) verwendet wird. Weitere Informationen finden Sie unter [/clr Restrictions](../../build/reference/clr-restrictions.md).

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
