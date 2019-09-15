---
title: _CrtCheckMemory
ms.date: 11/04/2016
api_name:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: 7e458825a81b7032310458ccda52d9299e126a35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938858"
---
# <a name="_crtcheckmemory"></a>_CrtCheckMemory

Bestätigt die Integrität der Speicherblöcke, die im Debugheap zugeordnet werden (nur Debugversion).

## <a name="syntax"></a>Syntax

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung gibt **_CrtCheckMemory** true zurück. Andernfalls gibt die Funktion false zurück.

## <a name="remarks"></a>Hinweise

Die **_CrtCheckMemory** -Funktion überprüft den vom debugheapmanager belegten Speicher, indem der zugrunde liegende Basisheap überprüft und jeder Speicherblock überprüft wird. Wenn im zugrunde liegenden Basisheap, in den debugheaderinformationen oder den Überschreibungs Puffern eine Fehler-oder Speicher Inkonsistenz auftritt, generiert **_CrtCheckMemory** einen Debugbericht mit Informationen, die den Fehlerzustand beschreiben. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtCheckMemory** während der Vorverarbeitung entfernt.

Das Verhalten von **_CrtCheckMemory** kann gesteuert werden, indem die Bitfelder des [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) -Flags mithilfe der [_CrtSetDbgFlag](crtsetdbgflag.md) -Funktion festgelegt werden. Wenn Sie das **_CRTDBG_CHECK_ALWAYS_DF** -Bitfeld aktivieren, wird **_CrtCheckMemory** jedes Mal aufgerufen, wenn ein Speicher Belegungs Vorgang angefordert wird. Obwohl diese Methode die Ausführung verlangsamt, ist sie nützlich, um Fehler schell zu erfassen. Wenn Sie das **_CRTDBG_ALLOC_MEM_DF** -Bitfeld deaktivieren, wird der Heap nicht durch **_CrtCheckMemory** überprüft, und es wird sofort **true**zurückgegeben.

Da diese Funktion **TRUE** oder **FALSE** zurückgibt, kann sie an eine der [_ASSERT](assert-asserte-assert-expr-macros.md)-Makros übergeben werden, um einen einfachen Debug-Fehlerbehandlungsmechanismus zu erstellen. Im folgenden Beispiel wird ein Assertionsfehler ausgelöst, wenn eine Beschädigung im Heap erkannt wird:

```C
_ASSERTE( _CrtCheckMemory( ) );
```

Weitere Informationen dazu, wie **_CrtCheckMemory** mit anderen Debugfunktionen verwendet werden kann, finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Eine Übersicht der Speicherverwaltung und des Debugheaps finden Sie unter [Details zum CRT-Debugheap](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_CrtCheckMemory**finden Sie unter [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
