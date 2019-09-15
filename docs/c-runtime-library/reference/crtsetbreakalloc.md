---
title: _CrtSetBreakAlloc
ms.date: 11/04/2016
api_name:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
ms.openlocfilehash: e13c908c1efd1af9196885dee6e3b0f45845946b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942303"
---
# <a name="_crtsetbreakalloc"></a>_CrtSetBreakAlloc

Legt einen Haltepunkt für eine angegebene Bestellnummer der Objektzuordnung fest (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
long _CrtSetBreakAlloc(
   long lBreakAlloc
);
```

### <a name="parameters"></a>Parameter

*lBreakAlloc*<br/>
Zuordnungsbestellnummer, für die der Haltepunkt festzulegen ist.

## <a name="return-value"></a>Rückgabewert

Gibt die vorherige Bestellnummer der Objektzuordnung zurück, die einen festgelegten Haltepunkt hatte.

## <a name="remarks"></a>Hinweise

**_CrtSetBreakAlloc** ermöglicht es einer Anwendung, die Speicherplatz Erkennung durchzuführen, indem an einem bestimmten Punkt der Speicher Belegung und Nachverfolgung zurück zum Ursprung der Anforderung unterbrochen wird. Die Funktion verwendet die sequenzielle Bestellnummer der Objektzuordnung, die dem Speicherblock zugewiesen wird, wenn sie im Heap reserviert wurde. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetBreakAlloc** während der Vorverarbeitung entfernt.

Die Bestellnummer der Objektzuordnung wird im *lRequest*-Feld der **_CrtMemBlockHeader**-Struktur gespeichert, die in „Crtdbg.h“ definiert ist. Wenn Informationen zu einem Speicherblock von einer der debugdumpfunktionen gemeldet werden, wird diese Zahl in geschweifte Klammern eingeschlossen, {36}z. b.

Weitere Informationen dazu, wie **_CrtSetBreakAlloc** mit anderen Speicherverwaltungsfunktionen verwendet werden kann, finden Sie unter nach [Verfolgen von Heap Zuordnungs Anforderungen](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtSetBreakAlloc**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

```C
// crt_setbrkal.c
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug

/*
* In this program, a call is made to the _CrtSetBreakAlloc routine
* to verify that the debugger halts program execution when it reaches
* a specified allocation number.
*/

#include <malloc.h>
#include <crtdbg.h>

int main( )
{
        long allocReqNum;
        char *my_pointer;

        /*
         * Allocate "my_pointer" for the first
         * time and ensure that it gets allocated correctly
         */
        my_pointer = malloc(10);
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);

        /*
         * Set a breakpoint on the allocation request
         * number for "my_pointer"
         */
        _CrtSetBreakAlloc(allocReqNum+2);

        /*
         * Alternate freeing and reallocating "my_pointer"
         * to verify that the debugger halts program execution
         * when it reaches the allocation request
         */
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
}
```

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
