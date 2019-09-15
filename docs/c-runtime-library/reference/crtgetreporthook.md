---
title: _CrtGetReportHook
ms.date: 11/04/2016
api_name:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
ms.openlocfilehash: bc005dda435b5e11d6c3c886de180ed85b9c2a04
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942400"
---
# <a name="_crtgetreporthook"></a>_CrtGetReportHook

Ruft die clientdefinierte Berichtsfunktion ab, um sie mit der C-Laufzeit für den Debug-Berichterstellungsprozess zu verknüpfen (nur Debugversion).

## <a name="syntax"></a>Syntax

```C
_CRT_REPORT_HOOK _CrtGetReportHook( void );
```

## <a name="return-value"></a>Rückgabewert

Gibt die aktuelle clientdefinierte Berichtsfunktion zurück.

## <a name="remarks"></a>Hinweise

**_CrtGetReportHook** ermöglicht es einer Anwendung, die aktuelle Berichtsfunktion für den Debugbibliothek-Bericht Erstellungs Prozess der C-Laufzeit abzurufen.

Weitere Informationen zur Verwendung anderer hookfähiger Laufzeitfunktionen und zum Schreiben eigener clientdefinierter Hookfunktionen finden Sie unter [Debug Hook Function Writing (Schreiben von Hookfunktionen zum Debuggen)](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_CrtGetReportHook**|\<crtdbg.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Debugversionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_CrtSetReportHook**finden Sie unter [Report](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report).

## <a name="see-also"></a>Siehe auch

[Debugroutinen](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportHook](crtsetreporthook.md)<br/>
