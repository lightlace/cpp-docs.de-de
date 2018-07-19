---
title: fputc, fputwc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fputc
- fputwc
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
- fputc
- fputwc
- _fputtc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af93e0c42002dc557f691daadd2fc003dced0247
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401416"
---
# <a name="fputc-fputwc"></a>fputc, fputwc

Schreibt ein Zeichen in einen Stream.

## <a name="syntax"></a>Syntax

```C
int fputc(
   int c,
   FILE *stream
);
wint_t fputwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu schreibende Zeichen.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt das geschriebene Zeichen zurück. Für **Fputc**, ein Rückgabewert von **EOF** zeigt einen Fehler an. Für **Fputwc**, ein Rückgabewert von **WEOF** zeigt einen Fehler an. Wenn *Stream* ist **NULL**, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben sie zurück **EOF** und **Errno** auf **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen schreibt das einzelne Zeichen *c* in eine Datei an der Position durch die dazugehörige dateipositionsanzeige (sofern definiert) und verschieben den Indikator entsprechend. Im Fall von **Fputc** und **Fputwc**, die Datei zugeordnet ist *Stream*. Wenn die Datei keine Positionierungsanforderungen unterstützt oder im Append-Modus geöffnet wurde, wird das Zeichen am Ende des Streams angefügt.

Die zwei Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Fputc** unterstützt derzeit keine Ausgabe in einen Unicode-Stream.

Die Versionen mit dem Suffix **_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt. Weitere Informationen finden Sie unter [_fputc_nolock, _fputwc_nolock](fputc-nolock-fputwc-nolock.md).

Es folgen routinespezifische Hinweise.

|Routine|Hinweise|
|-------------|-------------|
|**fputc**|Entspricht **Putc**, jedoch nur als Funktion anstelle einer Funktion und Makro implementiert.|
|**fputwc**|Breitzeichen Version von **Fputc**. Schreibt *c* als Multibytezeichen oder Breitzeichen, je nachdem, ob *Stream* im Textmodus oder Binärmodus geöffnet ist.|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind –**Stdin**, **"stdout"**, und **"stderr"**– umgeleitet werden müssen, damit C-Laufzeitfunktionen in uwp-apps verwendet werden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fputc.c
// This program uses fputc
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of fputc!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of fputc!!
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
