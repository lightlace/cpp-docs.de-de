---
title: _CrtCheckMemory | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6d4b84fd717525e7206956964204794fe6b88c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

Bestätigt die Integrität der Speicherblöcke, die im Debugheap zugeordnet werden (nur Debugversion).

## <a name="syntax"></a>Syntax

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Rückgabewert

Im Erfolgsfall **_CrtCheckMemory** gibt "true" ist, andernfalls "false" zurückgegeben.

## <a name="remarks"></a>Hinweise

Die **_CrtCheckMemory** Funktion überprüft der zugrunde liegende Basisheap überprüft und jeder Speicherblock untersucht vom debugheapmanager belegten Speicher. Wenn ein Fehler oder Inkonsistenzen in der zugrunde liegenden Basisheap, die debugheaderinformationen oder den überschreibungspuffern kommt **_CrtCheckMemory** erzeugt einen Debugbericht mit Informationen, die den Fehlerzustand beschreibt. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtCheckMemory** während der vorverarbeitung entfernt.

Das Verhalten des **_CrtCheckMemory** kann gesteuert werden, indem die Bitfelder des Festlegen der [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) Flags mithilfe der [_CrtSetDbgFlag](crtsetdbgflag.md) Funktion. Das Aktivieren der **_CRTDBG_CHECK_ALWAYS_DF** -Bitfelds in **_CrtCheckMemory** aufgerufen wird, jedes Mal, wenn ein speicherbelegungsvorgang angefordert wird. Obwohl diese Methode die Ausführung verlangsamt, ist sie nützlich, um Fehler schell zu erfassen. Das Aktivieren der **_CRTDBG_ALLOC_MEM_DF** -bit-Feld OFF Ursachen **_CrtCheckMemory** nicht überprüfen den Heap und Rückgaben unverzüglich **"true"**.

Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn eine Beschädigung im Heap erkannt wird:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Weitere Informationen dazu, wie **_CrtCheckMemory** kann mit anderen Debugfunktionen verwendet werden, finden Sie unter [den Heapzustand](/visualstudio/debugger/crt-debug-heap-details). Eine Übersicht der Speicherverwaltung und des Debugheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel zum Verwenden von **_CrtCheckMemory**, finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
