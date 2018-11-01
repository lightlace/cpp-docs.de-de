---
title: _CrtCheckMemory
ms.date: 11/04/2016
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: cb39a76c140934dabdd1269c02aba6018691f917
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537149"
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

Bestätigt die Integrität der Speicherblöcke, die im Debugheap zugeordnet werden (nur Debugversion).

## <a name="syntax"></a>Syntax

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **_CrtCheckMemory** gibt "true" ist, andernfalls gibt die Funktion "false" zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtCheckMemory** Funktion überprüft, die von der zugrunde liegende Basisheap überprüft und jeder Speicherblock untersucht vom debugheapmanager belegten Arbeitsspeichers. Wenn ein Fehler oder speicherinkonsistenzen, in der zugrunde liegende Basisheap, die debugheaderinformationen oder den überschreibungspuffern gefunden wird **_CrtCheckMemory** erzeugt einen Debugbericht mit Informationen, die den Fehlerzustand beschreibt. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtCheckMemory** werden während der vorverarbeitung entfernt.

Das Verhalten der **_CrtCheckMemory** kann gesteuert werden, indem die Bitfelder des der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) Flags mithilfe der [_CrtSetDbgFlag](crtsetdbgflag.md) Funktion. Aktivieren der **_CRTDBG_CHECK_ALWAYS_DF** -Bitfelds in **_CrtCheckMemory** aufgerufen wird, wenn ein speicherbelegungsvorgang angefordert wird. Obwohl diese Methode die Ausführung verlangsamt, ist sie nützlich, um Fehler schell zu erfassen. Aktivieren der **_CRTDBG_ALLOC_MEM_DF** OFF wird bewirkt, dass **_CrtCheckMemory** nicht den Heap überprüft und unverzüglich den Wert **"true"**.

Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn eine Beschädigung im Heap erkannt wird:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Weitere Informationen dazu, wie **_CrtCheckMemory** kann mit anderen Debugfunktionen verwendet werden, finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Eine Übersicht der Speicherverwaltung und des Debugheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung **_CrtCheckMemory**, finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
