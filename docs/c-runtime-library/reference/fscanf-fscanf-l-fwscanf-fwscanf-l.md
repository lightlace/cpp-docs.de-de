---
title: fscanf, _fscanf_l, fwscanf, _fwscanf_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fscanf
- _fwscanf_l
- _fscanf_l
- fwscanf
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
- fscanf
- fwscanf
- _ftscanf_l
- _fwscanf_l
- _ftscanf
- _fscanf_l
dev_langs:
- C++
helpviewer_keywords:
- fscanf function
- fwscanf function
- formatted data [C++], reading from streams
- ftscanf_l function
- _ftscanf_l function
- _fwscanf_l function
- data [CRT], reading from streams
- _fscanf_l function
- ftscanf function
- fscanf_l function
- streams [C++], reading formatted data from
- _ftscanf function
- fwscanf_l function
ms.assetid: 9004e978-6c5f-4bb2-98fd-51e5948933f2
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2334998ab246d6406dbac6d877b6e710d3dfc79
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fscanf-fscanfl-fwscanf-fwscanfl"></a>fscanf, _fscanf_l, fwscanf, _fwscanf_l

Lesen formatierter Daten aus einem Stream Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md).

## <a name="syntax"></a>Syntax

```C
int fscanf(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fscanf_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int fwscanf(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwscanf_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>Parameter

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

*format*<br/>
Formatsteuerzeichenfolge.

*Argument*<br/>
Optionale Argumente.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden. Der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Wenn ein Fehler auftritt oder wenn das Ende des Dateistreams vor der ersten Konvertierung erreicht wird, des Rückgabewerts ist **EOF** für **Fscanf** und **Fwscanf**.

Diese Funktionen überprüfen ihre Parameter. Wenn *Stream* oder *Format* ist ein null-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EOF** und **Errno** auf **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **Fscanf** -Funktion liest Daten aus der aktuellen Position des *Stream* in die Speicherorte, die vom *Argument* (sofern vorhanden). Jede *Argument* muss ein Zeiger auf eine Variable eines Typs, der einem Typspezifizierer in entspricht *Format*. *Format* steuert die Interpretation der Eingabefelder und hat die gleiche form und Funktion wie die *Format* Argument für **Scanf**; finden Sie unter [Scanf](scanf-scanf-l-wscanf-wscanf-l.md) für eine Beschreibung des *Format*.

**Fwscanf** ist eine Breitzeichen-Version von **Fscanf**; das Formatierungsargument **Fwscanf** ist eine Breitzeichen-Zeichenfolge. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Fscanf** unterstützt derzeit nicht die Eingabe aus einem Unicode-Stream.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der übergebenen Gebietsschemaparameter anstelle des aktuellen threadgebietsschemas.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftscanf**|**fscanf**|**fscanf**|**fwscanf**|
|**_ftscanf_l**|**_fscanf_l**|**_fscanf_l**|**_fwscanf_l**|

Weitere Informationen finden Sie unter [Feldern für die Formatangabe – Funktionen Scanf und Wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Fscanf**, **_fscanf_l**|\<stdio.h>|
|**Fwscanf**, **_fwscanf_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fscanf.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses fscanf to
// read the various data back from the file.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long l;
   float fp;
   char s[81];
   char c;

   if( fopen_s( &stream, "fscanf.out", "w+" ) != 0 )
      printf( "The file fscanf.out was not opened\n" );
   else
   {
      fprintf( stream, "%s %ld %f%c", "a-string",
               65000, 3.14159, 'x' );
      // Security caution!
      // Beware loading data from a file without confirming its size,
      // as it may lead to a buffer overrun situation.

      // Set pointer to beginning of file:
      fseek( stream, 0L, SEEK_SET );

      // Read data back from file:
      fscanf( stream, "%s", s );   // C4996
      fscanf( stream, "%ld", &l ); // C4996

      fscanf( stream, "%f", &fp ); // C4996
      fscanf( stream, "%c", &c );  // C4996
      // Note: fscanf is deprecated; consider using fscanf_s instead

      // Output data read:
      printf( "%s\n", s );
      printf( "%ld\n", l );
      printf( "%f\n", fp );
      printf( "%c\n", c );

      fclose( stream );
   }
}
```

```Output
a-string
65000
3.141590
x
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
