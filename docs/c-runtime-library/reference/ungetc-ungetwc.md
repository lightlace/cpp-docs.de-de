---
title: ungetc, ungetwc
ms.date: 11/04/2016
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
ms.openlocfilehash: c504540f8fbbe14961fa051bb93ebef350c2c1da
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332386"
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc

Schiebt ein Zeichen zurück auf den Stream.

## <a name="syntax"></a>Syntax

```C
int ungetc(
   int c,
   FILE *stream
);
wint_t ungetwc(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*c*<br/>
Zu verschiebendes Zeichen.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, jede dieser Funktionen das Zeichenargument zurückgibt *c*. Wenn *c* nicht zurückgeschoben werden oder wenn kein Zeichen gelesen wurde, der Eingabestream unverändert und **Ungetc** gibt **EOF**; **Ungetwc** gibt **WEOF**. Wenn *Stream* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **EOF** oder **WEOF** zurückgegeben und **Errno** nastaven NA hodnotu **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Ungetc** -Funktion schiebt das Zeichen *c* wieder *Stream* und löscht den Dateiende-Indikator. Der Stream muss zum Lesen geöffnet sein. Ein späterer Lesevorgang auf *Stream* beginnt mit *c*. Versuch, mithilfe von Push übertragen **EOF** auf der Stream mit **Ungetc** wird ignoriert.

Zeichen eingefügt werden, auf den Stream unter **Ungetc** kann gelöscht werden, wenn **Fflush**, [Fseek](fseek-fseeki64.md), **Fsetpos**, oder [rewind](rewind.md) wird aufgerufen, bevor das Zeichen aus dem Stream gelesen wird. Der Dateipositionszeiger erhält den Wert, den er auch schon hatte, bevor die Zeichen zurückgeschoben wurden. Der dem Stream entsprechende externe Speicher ist unverändert. Bei einem erfolgreichen **Ungetc** Aufruf für einen Textstream, der dateipositionszeiger nicht angegeben ist, bis alle zurückgeschobenen Zeichen gelesen oder verworfen werden. Auf jedem erfolgreichen **Ungetc** Aufrufen von einem binären Stream, der dateipositionszeiger verringert wird, wenn sein Wert vor einem Aufruf 0 ist, ist der Wert nicht definiert nach dem Aufruf.

Ergebnisse sind unvorhersehbar, wenn **Ungetc** zweimal ohne einen Lese- oder zwischen den beiden aufrufen dateipositionierungsvorgang aufgerufen wird. Nach einem Aufruf von **Fscanf**, einen Aufruf von **Ungetc** fehlschlagen, solange kein anderer Lesevorgang (wie z. B. **Getc**) ausgeführt wurde. Grund hierfür ist, **Fscanf** sich selbst aufruft **Ungetc**.

**Ungetwc** ist eine Breitzeichen-Version von **Ungetc**. Allerdings auf jedem erfolgreichen **Ungetwc** -Aufrufs an einen Text- oder Binärdaten-Datenstrom, der Wert des der dateipositionszeiger ist nicht angegeben, bis alle zurückgeschobenen Zeichen gelesen oder verworfen wurden.

Diese Funktionen sind während der Ausführung threadsicher und sperrabhängige Daten. Eine nicht sperrende Version finden Sie unter [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Standardstreamhandles, die mit der Konsole verknüpft sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_ungetc.c
// This program first converts a character
// representation of an unsigned integer to an integer. If
// the program encounters a character that is not a digit,
// the program uses ungetc to replace it in the  stream.
//

#include <stdio.h>
#include <ctype.h>

int main( void )
{
   int ch;
   int result = 0;

   // Read in and convert number:
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )
      result = result * 10 + ch - '0';    // Use digit.
   if( ch != EOF )
      ungetc( ch, stdin );                // Put nondigit back.
   printf( "Number = %d\nNext character in stream = '%c'",
            result, getchar() );
}
```

```Output

      521aNumber = 521
Next character in stream = 'a'
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
