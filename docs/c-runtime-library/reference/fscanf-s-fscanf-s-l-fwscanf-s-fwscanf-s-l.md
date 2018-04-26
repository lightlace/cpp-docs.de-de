---
title: fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fwscanf_s
- _fscanf_s_l
- _fwscanf_s_l
- fscanf_s
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
- _fwscanf_s_l
- _fscanf_s_l
- fscanf_s
- _ftscanf_s_l
- _ftscanf_s
- fwscanf_s
dev_langs:
- C++
helpviewer_keywords:
- formatted data [C++], reading from streams
- _ftscanf_s_l function
- _fscanf_s_l function
- ftscanf_s function
- fwscanf_s function
- _ftscanf_s function
- data [CRT], reading from streams
- _fwscanf_s_l function
- fscanf_s function
- fwscanf_s_l function
- ftscanf_s_l function
- streams [C++], reading formatted data from
- fscanf_s_l function
ms.assetid: b6e88194-714b-4322-be82-1cc0b343fe01
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 85983434cb963fa4c936a8b6bae3d8bbb71028c7
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="fscanfs-fscanfsl-fwscanfs-fwscanfsl"></a>fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l

Liest formatierte Daten aus einem Stream. Diese Versionen von [fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
int fscanf_s(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fscanf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int fwscanf_s(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwscanf_s_l(
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

Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Wenn ein Fehler auftritt oder wenn das Ende des Dateistreams vor der ersten Konvertierung erreicht wird, des Rückgabewerts ist **EOF** für **Fscanf_s** und **Fwscanf_s**.

Diese Funktionen überprüfen ihre Parameter. Wenn *Stream* ist ein ungültigen Dateizeiger oder *Format* ist ein null-Zeiger, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **EOF** und **Errno** auf **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **Fscanf_s** -Funktion liest Daten aus der aktuellen Position des *Stream* in die Speicherorte, die sich durch *Argument* (sofern vorhanden). Jede *Argument* muss ein Zeiger auf eine Variable eines Typs, der einem Typspezifizierer in entspricht *Format*. *Format* steuert die Interpretation der Eingabefelder und hat die gleiche form und Funktion wie die *Format* Argument für **Scanf_s**; finden Sie unter [Formatangabefelder: Scanf und Wscanf-Funktionen](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) eine Beschreibung der *Format*.  **Fwscanf_s** ist eine Breitzeichen-Version von **Fscanf_s**; das Formatierungsargument **Fwscanf_s** ist eine Breitzeichen-Zeichenfolge. Diese Funktionen verhalten sich identisch, wenn der Stream im ANSI-Modus geöffnet ist. **Fscanf_s** unterstützt derzeit nicht die Eingabe aus einem Unicode-Stream.

Der Hauptunterschied zwischen den sichereren Funktionen (, auf denen die **_s** Suffix) und den anderen Versionen ist, dass die sichereren Funktionen die Größe in Zeichen von jedem erfordern **c**, **C**, **s**, **S**, und **[** -Typfeld als Argument sofort nach der folgenden Variablen übergeben werden. Weitere Informationen finden Sie unter [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) und [scanf-Breitenangabe](../../c-runtime-library/scanf-width-specification.md).

> [!NOTE]
> Der Größenparameter ist vom Typ **ohne Vorzeichen**, nicht **Size_t**.

Die Versionen dieser Funktionen mit dem **_l** -Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der übergeben wird anstelle des aktuellen threadgebietsschemas.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftscanf_s**|**fscanf_s**|**fscanf_s**|**fwscanf_s**|
|**_ftscanf_s_l**|**_fscanf_s_l**|**_fscanf_s_l**|**_fwscanf_s_l**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**Fscanf_s**, **_fscanf_s_l**|\<stdio.h>|
|**Fwscanf_s**, **_fwscanf_s_l**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_fscanf_s.c
// This program writes formatted
// data to a file. It then uses fscanf to
// read the various data back from the file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   long l;
   float fp;
   char s[81];
   char c;

   errno_t err = fopen_s( &stream, "fscanf.out", "w+" );
   if( err )
      printf_s( "The file fscanf.out was not opened\n" );
   else
   {
      fprintf_s( stream, "%s %ld %f%c", "a-string",
               65000, 3.14159, 'x' );
      // Set pointer to beginning of file:
      fseek( stream, 0L, SEEK_SET );

      // Read data back from file:
      fscanf_s( stream, "%s", s, _countof(s) );
      fscanf_s( stream, "%ld", &l );

      fscanf_s( stream, "%f", &fp );
      fscanf_s( stream, "%c", &c, 1 );

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
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
