---
title: _fgetchar, _fgetwchar | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fgetchar
- _fgetwchar
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
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
dev_langs:
- C++
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3d83c1e86c574f56b08eecdf2c29e7ab20a28b4
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194317"
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar, _fgetwchar

Liest ein Zeichen aus **Stdin**.

## <a name="syntax"></a>Syntax

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>Rückgabewert

**\_Fgetchar** gibt das gelesene Zeichen als ein **Int** fest oder gibt `EOF` auf einen Fehler oder ein Dateiende anzugeben. **\_Fgetwchar** zurückgegeben wird, als eine [Wint_t](../../c-runtime-library/standard-types.md), das Breitzeichen, die das gelesene Zeichen entspricht, oder gibt `WEOF` auf einen Fehler oder ein Dateiende anzugeben. Verwenden Sie für beide Funktionen **Feof** oder **Ferror** ein Fehler auftritt und eine End-of-File-Bedingung unterscheiden.

## <a name="remarks"></a>Hinweise

Diese Funktionen lesen ein einzelnes Zeichen aus **Stdin**. Die Funktion erhöht dann den zugeordneten Dateizeiger (sofern definiert), um auf das nächste Zeichen zu zeigen. Wenn der Stream am Dateiende ist, wird der Dateiende-Indikator für den Stream festgelegt.

**_fgetchar** entspricht `fgetc( stdin )`. Dies entspricht auch **Getchar**, jedoch nur als Funktion anstelle einer Funktion und Makro implementiert. **_fgetwchar** ist die Breitzeichen-Version von **_fgetchar**.

Diese Funktionen sind nicht dem ANSI-Standard kompatibel.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fgetchar**|\<stdio.h>|
|**_fgetwchar**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Die mit der Konsole verknüpften standardstreamhandles,**Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fgetchar.c
// This program uses _fgetchar to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char buffer[81];
   int  i, ch;

   // Read in first 80 characters and place them in "buffer":
   ch = _fgetchar();
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = _fgetchar();
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
}
```

```Output

      Line one.
Line two.Line one.
Line two.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
