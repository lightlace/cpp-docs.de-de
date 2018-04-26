---
title: fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
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
- _ftprintf_s
- fprintf_s
- fwprintf_s
dev_langs:
- C++
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70f960302ee5b3a5e0c702e158396ab329aa5121
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fprintfs-fprintfsl-fwprintfs-fwprintfsl"></a>fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l

Geben formatierte Daten an einen Stream aus Dies sind Versionen von [fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int fprintf_s(
   FILE *stream,
   const char *format [,
   argument_list ]
);
int _fprintf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument_list ]
);
int fwprintf_s(
   FILE *stream,
   const wchar_t *format [,
   argument_list ]
);
int _fwprintf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument_list ]
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

*format*<br/>
Formatsteuerzeichenfolge.

*argument_list*<br/>
Optionale Argumente, die der Formatzeichenfolge.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**Fprintf_s** gibt die Anzahl der geschriebenen Bytes zurück. **Fwprintf_s** gibt die Anzahl der geschriebenen Zeichen zurück. Jede dieser Funktionen gibt stattdessen einen negativen Wert zurück, wenn ein Ausgabefehler auftritt.

## <a name="remarks"></a>Hinweise

**Fprintf_s** formatiert und druckt eine Reihe von Zeichen und Werten für die Ausgabe *Stream*. Jedes Argument in *Argument_list* (sofern vorhanden) konvertiert und ausgegeben wird, entsprechend der jeweiligen Formatangabe in *Format*. Die *Format* Argument verwendet den [formatieren Sie die Syntax der Formatangabe für Printf und Wprintf-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

**Fwprintf_s** ist eine Breitzeichen-Version von **Fprintf_s**in **Fwprintf_s**, *Format* ist eine Breitzeichen-Zeichenfolge. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Fprintf_s** derzeit die Ausgabe in eine Unicode-Stream unterstützt keine.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter anstelle des aktuellen Gebietsschemas übergeben.

> [!IMPORTANT]
> Stellen Sie sicher, dass *format* keine benutzerdefinierte Zeichenfolge ist.

Wie Sie die nicht sicheren Versionen (finden Sie unter [Fprintf, _fprintf_l, Fwprintf _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)), diese Funktionen überprüfen ihre Parameter und den Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md), wenn entweder *Stream* oder *Format* ist ein null-Zeiger. Auch wird die Formatzeichenfolge selbst überprüft. Gibt es unbekannte oder ungültige Formatbezeichner, generieren diese Funktionen die Ausnahme für ungültige Parameter. In allen Fällen, wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktionen – 1 zurück und legen Sie **Errno** auf **EINVAL**. Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftprintf_s**|**fprintf_s**|**fprintf_s**|**fwprintf_s**|
|**_ftprintf_s_l**|**_fprintf_s_l**|**_fprintf_s_l**|**_fwprintf_s_l**|

Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Fprintf_s**, **_fprintf_s_l**|\<stdio.h>|
|**Fwprintf_s**, **_fwprintf_s_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fprintf_s.c
// This program uses fprintf_s to format various
// data and print it to the file named FPRINTF_S.OUT. It
// then displays FPRINTF_S.OUT on the screen using the system
// function to invoke the operating-system TYPE command.

#include <stdio.h>
#include <process.h>

FILE *stream;

int main( void )
{
   int    i = 10;
   double fp = 1.5;
   char   s[] = "this is a string";
   char   c = '\n';

   fopen_s( &stream, "fprintf_s.out", "w" );
   fprintf_s( stream, "%s%c", s, c );
   fprintf_s( stream, "%d\n", i );
   fprintf_s( stream, "%f\n", fp );
   fclose( stream );
   system( "type fprintf_s.out" );
}
```

```Output
this is a string
10
1.500000
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
