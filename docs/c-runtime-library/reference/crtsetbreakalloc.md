---
title: _CrtSetBreakAlloc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e14e1d40d5d20b9759d115eaf2fd29b3cae57172
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc

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

**_CrtSetBreakAlloc** ermöglicht es einer Anwendung an den Ursprung der Anforderung angehalten und wichtige zu einem bestimmten Zeitpunkt der speicherbelegung speicherverlusterkennung ausführen. Die Funktion verwendet die sequenzielle Bestellnummer der Objektzuordnung, die dem Speicherblock zugewiesen wird, wenn sie im Heap reserviert wurde. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtSetBreakAlloc** während der vorverarbeitung entfernt.

Die Bestellnummer der Objektzuordnung wird im *lRequest*-Feld der **_CrtMemBlockHeader**-Struktur gespeichert, die in „Crtdbg.h“ definiert ist. Wenn Informationen zu einem Speicherblock von einer der Debugdumpfunktionen ausgegeben werden, wird die Nummer in geschweiften Klammern angezeigt, z. B. {36}.

Weitere Informationen dazu, wie **_CrtSetBreakAlloc** kann mit anderen Speicherverwaltungsfunktionen verwendet werden, finden Sie unter [Nachverfolgen von Heapreservierungsanforderungen](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
