---
title: _CrtMemDumpStatistics | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 655d9be75fa031cc2cbebfd65c4634528f410e85
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110525"
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics

Gibt die Debugheaderinformationen für einen angegebenen Heapzustand in einer für den Benutzer lesbaren Form aus (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parameter

*state*<br/>
Zeiger zum auszugebenden Heapzustand.

## <a name="remarks"></a>Hinweise

Die **_CrtMemDumpStatistics** Funktion gibt die debugheaderinformationen für einen bestimmten Status des Heaps in einem Benutzer lesbaren Formular. Die Dumpstatistik kann von der Anwendung zum Nachverfolgen von Zuordnungen und zum Erkennen von Speicherproblemen verwendet werden. Der Speicherzustands kann einen bestimmten Heapzustand oder den Unterschied zwischen zwei Zuständen enthalten. Wenn [_DEBUG](../../c-runtime-library/debug.md) nicht definiert ist, werden Aufrufe von **_CrtMemDumpStatistics** werden während der vorverarbeitung entfernt.

Die *Zustand* Parameter muss ein Zeiger auf eine **_CrtMemState** -Struktur, die von gefüllt wurde [_CrtMemCheckpoint](crtmemcheckpoint.md) oder zurückgegebenes [_ CrtMemDifference](crtmemdifference.md) vor **_CrtMemDumpStatistics** aufgerufen wird. Wenn *Zustand* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und keine Aktion ausgeführt wird. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Weitere Informationen über heapzustandsfunktionen und die **_CrtMemState** Struktur, siehe [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Weitere Informationen darüber, wie Speicherblöcke in der Debugversion des Basisheaps zugeordnet, initialisiert und verwaltet werden, finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|Optionale Header|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h>|\<errno.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

**Bibliotheken:** Nur Debugversionen der [CRT-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md)

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
