---
title: _setmaxstdio
ms.date: 11/04/2016
apiname:
- _setmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setmaxstdio
- _setmaxstdio
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
ms.openlocfilehash: 58cffedf673e23a69c2d8040071b2e3353ff4502
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445083"
---
# <a name="setmaxstdio"></a>_setmaxstdio

Legt eine maximale Anzahl von gleichzeitig geöffneten Dateien an die **Stdio** Ebene.

## <a name="syntax"></a>Syntax

```C
int _setmaxstdio(
   int newmax
);
```

### <a name="parameters"></a>Parameter

*newmax*<br/>
Neue maximale Anzahl von gleichzeitig geöffneten Dateien an die **Stdio** Ebene.

## <a name="return-value"></a>Rückgabewert

Gibt *Newmax* Wenn erfolgreich; andernfalls -1.

Wenn *Newmax* ist kleiner als **_IOB_ENTRIES** oder größer als die maximale Anzahl der Handles, die zur Verfügung, in das Betriebssystem, den Handler für ungültige Parameter aufgerufen wird, wie in beschrieben, [ Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, diese Funktion gibt-1 zurück und legt **Errno** zu **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_setmaxstdio** Funktion ändert sich den maximalen Wert für die Anzahl der Dateien, die möglicherweise gleichzeitig geöffnet, auf die **Stdio** Ebene.

C-Laufzeit-E/A unterstützt nun eine größere Anzahl von geöffneten Dateien auf Win32-Plattformen als in früheren Versionen. Bis zu 2.048 Dateien kann gleichzeitig auf geöffnet werden die [Lowio-Ebene](../../c-runtime-library/low-level-i-o.md) (d.h. geöffnet und mithilfe von der **_open**, **_read**, **_write**, e/a-Funktionen und ähnliches Familie). Bis zu 512 Dateien kann gleichzeitig auf geöffnet werden die [Stdio-Ebene](../../c-runtime-library/stream-i-o.md) (d.h. geöffnet und mithilfe von der **Fopen**, **Fgetc**, **Fputc** und so weiter Funktionsreihe). Das Limit von 512 geöffnete Dateien auf den **Stdio** -Stufe erhöht werden kann, auf ein Maximum von 2.048 von der **_setmaxstdio** Funktion.

Da **Stdio**-level-Funktionen, z. B. **Fopen**, basieren auf der die **Lowio** Funktionen das Maximum von 2.048 ist eine feste Obergrenze für die Anzahl der gleichzeitig Öffnen Sie die Dateien, die über die C-Laufzeitbibliothek zugegriffen.

> [!NOTE]
> Die Obergrenze überschreitet möglicherweise die von einer bestimmten Win32-Plattform und -Konfiguration unterstützte Grenze.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Finden Sie unter [_getmaxstdio](getmaxstdio.md) ein Beispiel der Verwendung von **_setmaxstdio**.

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
