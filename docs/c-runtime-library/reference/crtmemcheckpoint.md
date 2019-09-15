---
title: _CrtMemCheckpoint
ms.date: 11/04/2016
api_name:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: edf91cd8c76fd080326e2e5eeac98f7f81ab90cf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942370"
---
# <a name="_crtmemcheckpoint"></a>_CrtMemCheckpoint

Ruft den aktuellen Zustand des Debugheaps ab und speichert ihn in einer von der Anwendung bereitgestellten **_CrtMemState** -Struktur (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>Parameter

*state*<br/>
Zeiger auf die **_CrtMemState** -Struktur, die mit dem Arbeitsspeicher Prüf Punkt ausgefüllt werden

## <a name="remarks"></a>Hinweise

Die **_CrtMemCheckpoint** -Funktion erstellt eine Momentaufnahme des aktuellen Status des Debugheaps zu einem beliebigen Zeitpunkt. Diese Momentaufnahme kann von anderen Heapzustandsfunktionen wie [_CrtMemDifference](crtmemdifference.md) verwendet werden, um das Erkennen von Speicherverlusten und anderen Problemen zu unterstützen. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemState** während der Vorverarbeitung entfernt.

Die Anwendung muss einen Zeiger auf eine zuvor zugeordnete Instanz der **_CrtMemState** -Struktur, die in CRTDBG. h definiert ist, im *State* -Parameter übergeben. Wenn **_CrtMemCheckpoint** während der Prüf Punkt Erstellung einen Fehler feststellt, generiert die Funktion einen **_CRT_WARN** -Debugbericht, der das Problem beschreibt.

Weitere Informationen zu Heap Zustands Funktionen und der **_CrtMemState** -Struktur finden Sie unter [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Wenn *State* **null**ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameter](../../c-runtime-library/parameter-validation.md)Überprüfung) beschrieben. Wenn die weitere Ausführung zugelassen wird, wird [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) auf **EINVAL** festgelegt, und die Funktion gibt zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken** Nur Debugversionen der ucrt.

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
