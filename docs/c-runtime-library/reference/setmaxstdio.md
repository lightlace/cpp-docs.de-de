---
title: _setmaxstdio
ms.date: 05/21/2019
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
ms.openlocfilehash: 94b768d920ffd86a5bd762f8994244dda67fb15f
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174824"
---
# <a name="setmaxstdio"></a>_setmaxstdio

Legt eine maximale Anzahl für die Dateien fest, die auf der E/A-Ebene des Streams gleichzeitig geöffnet sein können.

## <a name="syntax"></a>Syntax

```C
int _setmaxstdio(
   int new_max
);
```

### <a name="parameters"></a>Parameter

*new_max*<br/>
Neue maximale Anzahl für die Dateien, die auf der E/A-Ebene des Streams gleichzeitig geöffnet sein können.

## <a name="return-value"></a>Rückgabewert

Gibt *new_max* zurück, wenn erfolgreich; andernfalls -1.

Wenn *new_max* kleiner als **_IOB_ENTRIES** oder größer als die maximale Anzahl von Handles ist, die im Betriebssystem verfügbar sind, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation](../../c-runtime-library/parameter-validation.md) (Parameterüberprüfung) beschrieben. Wenn die Ausführung weiterhin zugelassen wird, gibt diese Funktion -1 zurück und legt **errno** auf **EINVAL** fest.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Anmerkungen

Die **_setmaxstdio**-Funktion ändert den Maximalwert für die Anzahl von Dateien, die gleichzeitig auf Stream-E/A-Ebene geöffnet sein können.

C-Laufzeit-E/A unterstützt nun bis zu 8.192 gleichzeitig geöffnete Dateien auf [niedriger E/A-Ebene](../../c-runtime-library/low-level-i-o.md). Diese Ebene umfasst Dateien, für die das Öffnen und der Zugriff mithilfe der Familie der E/A-Funktionen **_open**, **_read** und **_write** erfolgt ist. Standardmäßig können auf der [Stream-I/O-Ebene](../../c-runtime-library/stream-i-o.md) bis zu 512 Dateien gleichzeitig geöffnet sein. Diese Ebene umfasst Dateien, für die das Öffnen und der Zugriff mithilfe der Familie der Funktionen **fopen**, **fgetc** und **fputc** erfolgt ist. Die Grenze von 512 geöffneten Dateien auf der Stream-E/A-Ebene kann mithilfe der Funktion **_setmaxstdio** auf maximal 8.192 erhöht werden.

Da Funktionen der Stream-E/A-Ebene, wie z.B. **fopen**, auf den Funktionen der niedrigen E/A_Ebene aufsetzen, ist das Maximum von 8.192 eine feste Obergrenze für die Anzahl von gleichzeitig geöffneten Dateien, auf die über die C-Laufzeitbibliothek zugegriffen wird.

> [!NOTE]
> Diese Obergrenze kann über die von einer bestimmten Win32-Plattform und -Konfiguration unterstützten Werte hinausgehen.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_setmaxstdio**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Unter [_getmaxstdio](getmaxstdio.md) finden Sie ein Beispiel der Verwendung von **_setmaxstdio**.

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
