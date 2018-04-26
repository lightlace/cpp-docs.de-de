---
title: ungetc, ungetwc | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9ce7de35118d4dd9c365b758a398b865e646036
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
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

Wenn erfolgreich, jede dieser Funktionen der Zeichenargument zurückgibt *c*. Wenn *c* nicht zurückgeschoben werden oder wenn kein Zeichen gelesen wurde, wird der Eingabestream unverändert und **Ungetc** gibt ** EOF`; **ungetwc` gibt **WEOF**. Wenn *Stream* ist **NULL**, den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **EOF** oder **WEOF** zurückgegeben und **Errno** festgelegt ist, um **EINVAL**.

Weitere Informationen über diese und andere Fehlercodes finden Sie unter [errno, _doserrno, _sys_errlist, and _sys_nerr (_doserrno, errno, _sys_errlist und _sys_nerr)](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Ungetc** -Funktion schiebt das Zeichen *c* wieder *Stream* und löscht den Dateiende-Indikator. Der Stream muss zum Lesen geöffnet sein. Eine nachfolgende Lesevorgang auf *Stream* beginnt mit *c*. Versuch, mithilfe von Push übertragen **EOF** auf den Stream unter Verwendung **Ungetc** wird ignoriert.

Zeichen in den Stream unter platziert **Ungetc** kann gelöscht werden, wenn **Fflush**, [Fseek](fseek-fseeki64.md), **Fsetpos**, oder [zurückspulen](rewind.md) wird aufgerufen, bevor das Zeichen aus dem Stream gelesen wird. Der Dateipositionszeiger erhält den Wert, den er auch schon hatte, bevor die Zeichen zurückgeschoben wurden. Der dem Stream entsprechende externe Speicher ist unverändert. Bei einem erfolgreichen **Ungetc** -Aufruf für einen Textstream der dateipositionszeiger nicht angegeben wird, bis alle zurückgeschobenen Zeichen gelesen oder verworfen werden. Auf jedem erfolgreichen **Ungetc** -Aufruf für einen binären Datenstrom, der dateipositionszeiger verringert ist; wenn sein Wert vor einem Aufruf 0 ist, ist der Wert nicht definiert nach dem Aufruf.

Ergebnisse sind unvorhersehbar, wenn **Ungetc** zweimal ohne einen Lesevorgang oder zwischen den beiden aufrufen dateipositionierungsvorgang aufgerufen wird. Nach einem Aufruf von **Fscanf**, einen Aufruf von **Ungetc** fehlschlagen, solange kein anderer Lesevorgang (wie z. B. **Getc**) ausgeführt wurde. Grund hierfür ist, **Fscanf** sich selbst aufruft **Ungetc**.

**Ungetwc** ist eine Breitzeichen-Version von **Ungetc**. Allerdings auf jedem erfolgreichen **Ungetwc** -Aufruf für einen Text- oder Binärformat Binärstream bleibt von der dateipositionszeiger nicht angegeben wird, bis alle zurückgeschobenen Zeichen gelesen oder verworfen wurden.

Diese Funktionen sind während der Ausführung threadsicher und sperrabhängige Daten. Eine nicht sperrende Version finden Sie unter [_ungetc_nolock, _ungetwc_nolock](ungetc-nolock-ungetwc-nolock.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc**|**ungetc**|**ungetc**|**ungetwc**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**ungetc**|\<stdio.h>|
|**ungetwc**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

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
