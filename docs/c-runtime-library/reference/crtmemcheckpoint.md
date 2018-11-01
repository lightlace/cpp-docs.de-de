---
title: _CrtMemCheckpoint
ms.date: 11/04/2016
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: ee435ba3e9e40795280dee0f97feaad32c8b0fc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589516"
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

Ruft den aktuellen Zustand des Debugheaps und speichert Sie in einer Anwendung bereitgestellten **_CrtMemState** Struktur (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Parameter

*state*<br/>
Zeiger auf **_CrtMemState** Struktur mit dem arbeitsspeicherprüfpunkt ausgefüllt.

## <a name="remarks"></a>Hinweise

Die **_CrtMemCheckpoint** -Funktion erstellt eine Momentaufnahme des aktuellen Zustands des Debugheaps zu einem bestimmten Zeitpunkt. Diese Momentaufnahme kann von anderen Heapzustandsfunktionen wie [_CrtMemDifference](crtmemdifference.md) verwendet werden, um das Erkennen von Speicherverlusten und anderen Problemen zu unterstützen. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemState** werden während der vorverarbeitung entfernt.

Die Anwendung muss einen Zeiger auf eine zuvor zugeordnete Instanz von übergeben die **_CrtMemState** Struktur, definiert in "CRTDBG.h" definiert, in der *Zustand* Parameter. Wenn **_CrtMemCheckpoint** einen Fehler bei der prüfpunkterstellung erkennt, generiert die Funktion eine **_CRT_WARN** Debugbericht, die Beschreibung des Problems.

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** Struktur, siehe [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Wenn *Zustand* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, [Errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) nastaven NA hodnotu **EINVAL** und die Funktion zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** nur Debugversionen der UCRT.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
