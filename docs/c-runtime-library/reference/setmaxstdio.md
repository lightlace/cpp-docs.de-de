---
title: _setmaxstdio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 785fcc05c6b19086c14edc85983749894c867c18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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

Gibt *Newmax* Wenn erfolgreich, andernfalls -1.

Wenn *Newmax* ist kleiner als **_IOB_ENTRIES** oder höher, und klicken Sie dann die maximale Anzahl von Handles zur Verfügung, in das Betriebssystem, den Handler für ungültige Parameter aufgerufen wird, wie in beschrieben, [ Überprüfen der Parameter](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion gibt-1 zurück und setzt **Errno** auf **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_setmaxstdio** -Funktion ändert den Maximalwert für die Anzahl der Dateien, die gleichzeitig geöffnet sein können die **Stdio** Ebene.

C-Laufzeit-E/A unterstützt nun eine größere Anzahl von geöffneten Dateien auf Win32-Plattformen als in früheren Versionen. Kann auf bis zu 2.048 Dateien gleichzeitig am offen sein der [Lowio Ebene](../../c-runtime-library/low-level-i-o.md) (d. h. geöffnet und mithilfe von zugegriffen der **_open**, **_microsoft**, **_write**, usw. Funktionsreihe e/a). Kann auf bis zu 512 Dateien gleichzeitig am offen sein der [Stdio-Ebene](../../c-runtime-library/stream-i-o.md) (d. h. geöffnet und mithilfe von zugegriffen der **Fopen**, **Fgetc**, **Fputc** usw. Funktionsreihe). Das Limit von 512 geöffneten Dateien an die **Stdio** Ebene erhöht werden kann, auf ein Maximum von 2.048 anhand der die **_setmaxstdio** Funktion.

Da **Stdio**-level-Funktionen, z. B. **Fopen**, basieren auf der Basis von der **Lowio** Funktionen, die maximal von 2.048 ist eine feste Obergrenze für die Anzahl der gleichzeitig Öffnen von Dateien, die über die C-Laufzeitbibliothek zugegriffen.

> [!NOTE]
> Die Obergrenze überschreitet möglicherweise die von einer bestimmten Win32-Plattform und -Konfiguration unterstützte Grenze.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Finden Sie unter [_getmaxstdio](getmaxstdio.md) ein Beispiel der Verwendung von **_setmaxstdio**.

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
