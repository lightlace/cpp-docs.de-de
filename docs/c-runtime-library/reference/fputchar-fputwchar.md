---
title: _fputchar, _fputwchar | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fputchar
- _fputwchar
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
- fputtchar
- _fputwchar
- fputwchar
- _fputtchar
- fputchar
- _fputchar
dev_langs:
- C++
helpviewer_keywords:
- fputchar function
- standard output, writing to
- _fputtchar function
- fputwchar function
- _fputwchar function
- fputtchar function
- _fputchar function
ms.assetid: b92ff600-a924-4f2b-b0e7-3097ee31bdff
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8ce9209f8ee99ef2f48eeb81c79548ff6e8cbf6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fputchar-fputwchar"></a>_fputchar, _fputwchar

Schreibt ein Zeichen in **stdout**.

## <a name="syntax"></a>Syntax

```C
int _fputchar(
   int c
);
wint_t _fputwchar(
   wchar_t c
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu schreibende Zeichen.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt das geschriebene Zeichen zurück. Für **_fputchar**, ein Rückgabewert von **EOF** zeigt einen Fehler an. Für **_fputwchar**, ein Rückgabewert von **WEOF** zeigt einen Fehler an. Wenn c **NULL**, generieren diese Funktionen eine Ausnahme für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben sie zurück **EOF** (oder **WEOF**), und legen **Errno** auf **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Beide Funktionen schreibt das einzelne Zeichen *c* auf **"stdout"** und verschieben den Indikator entsprechend. **_fputchar** entspricht `fputc( stdout )`. Dies entspricht auch **Putchar**, jedoch nur als Funktion anstelle einer Funktion und Makro implementiert. Im Gegensatz zu **Fputc** und **Putchar**, diese Funktionen sind nicht mit dem ANSI-Standard kompatibel.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fputtchar**|**_fputchar**|**_fputchar**|**_fputwchar**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fputchar**|\<stdio.h>|
|**_fputwchar**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind –**Stdin**, **"stdout"**, und **"stderr"**– umgeleitet werden müssen, damit C-Laufzeitfunktionen in uwp-apps verwendet werden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fputchar.c
// This program uses _fputchar
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
    char strptr[] = "This is a test of _fputchar!!\n";
    char *p = NULL;

    // Print line to stream using _fputchar.
    p = strptr;
    while( (*p != '\0') && _fputchar( *(p++) ) != EOF )
      ;
}
```

```Output
This is a test of _fputchar!!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
