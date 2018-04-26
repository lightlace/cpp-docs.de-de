---
title: _mktemp, _wmktemp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wmktemp
- _mktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs:
- C++
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c270623c0ea81294295e949a90de2a770db0b16
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp

Vergibt einen eindeutigen Dateinamen. Für diese Funktionen sind sicherere Versionen verfügbar. Informationen dazu finden Sie unter [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md).

## <a name="syntax"></a>Syntax

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*nameTemplate*<br/>
Muster des Dateinamens.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf die geänderte NameTemplate zurück. Die Funktion gibt **NULL** Wenn *NameTemplate* weist ein ungültiges Format oder keine weiteren eindeutigen Namen aus der angegebenen NameTemplate erstellt werden können.

## <a name="remarks"></a>Hinweise

Die **_mktemp** -Funktion erstellt einen eindeutigen Dateinamen an, durch das Ändern der *NameTemplate* Argument. **_mktemp** Multibyte-Zeichenfolgenargumente nach Bedarf, Erkennung von Multibyte-Zeichensequenzen entsprechend der multibyte-Codepage derzeit vom System zur Laufzeit automatisch behandelt. **_wmktemp** ist eine Breitzeichen-Version von **_mktemp**; der Wert Argument- und Rückgabetypen der **_wmktemp** sind Zeichenfolgen mit Breitzeichen. **_wmktemp** und **_mktemp** Verhalten sich andernfalls identisch, außer dass **_wmktemp** verarbeitet keine Multibyte-Zeichenfolgen.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

Die *NameTemplate* Argument hat das Format *Basis ** XXXXXX*, wobei *Basis* ist der Teil der neuen Dateinamen ein, den Sie angeben, und jedes "X" ein Platzhalter für ein Zeichen, das vom **_mktemp**. Jede Platzhalterzeichen in *NameTemplate* muss einen Großbuchstaben x **_mktemp** behält *Basis* und ersetzt das erste nachfolgende "X" mit einem alphanumerischen Zeichen. **_mktemp** ersetzt die folgenden nachgestellten x mit einem Wert fünfstellige; dieser Wert ist eine eindeutige Identifikationsnummer der aufrufende Prozess, oder in Multithreadprogrammen den aufrufenden Thread.

Jeden erfolgreichen Aufruf von **_mktemp** ändert *NameTemplate*. Bei jedem nachfolgenden Aufruf aus dem gleichen Prozess oder Thread mit dem gleichen *NameTemplate* Argument **_mktemp** sucht nach Dateinamen, die von zurückgegebene Namen entsprechen **_mktemp** in vorherigen aufrufen. Wenn keine Datei für einen angegebenen Namen existiert **_mktemp** zurückgegeben. Wenn Dateien vorhanden sind, für alle zuvor Namen zurückgegebenen **_mktemp** erstellt einen neuen Namen durch Ersetzen der alphabetischen Zeichens, die sie in den zuvor zurückgegebenen Namen mit den nächsten verfügbaren Kleinbuchstaben enthalten, in der Reihenfolge von "a" bis "Z" verwendet. Z. B. wenn *Basis* ist:

> **fn**

und der fünfstellige-Wert, der vom **_mktemp** 12345 ist, wird der erste Name zurückgegeben:

> **fna12345**

Wenn dieser Name verwendet wird, um die Datei FNA12345 erstellen und diese Datei noch vorhanden ist, den Namen des nächste zurückgegeben, bei einem Aufruf von den gleichen Prozess oder Thread mit dem gleichen *Basis* für *NameTemplate* ist:

> **fnb12345**

Ist FNA12345 nicht vorhanden, lautet der nächste zurückgegebene Name erneut:

> **fna12345**

**_mktemp** können bis zu 26 eindeutige Dateinamen für eine bestimmte Kombination von erstellen *Basis* und *NameTemplate* Werte. Daher FNZ12345 ist die letzte eindeutiger Dateiname **_mktemp** erstellen können, für die *Basis* und *NameTemplate* in diesem Beispiel verwendeten Werte.

Bei einem Fehler **Errno** festgelegt ist. Wenn *NameTemplate* weist ein ungültiges Format (z. B. weniger als 6 x), **Errno** festgelegt ist, um **EINVAL**. Wenn **_mktemp** kann einen eindeutigen Namen zu erstellen, da alle 26 möglichen Dateinamen bereits vorhanden sind, **_mktemp** legt NameTemplate auf eine leere Zeichenfolge und gibt **EEXIST**.

In C++ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
