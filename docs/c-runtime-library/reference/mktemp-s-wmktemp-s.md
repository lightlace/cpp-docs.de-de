---
title: _mktemp_s, _wmktemp_s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mktemp_s
- _wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0ed525f44150943496cddde57699035d8b62b6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s

Erstellt einen eindeutigen Dateinamen. Dabei handelt es sich um Versionen von [_mktemp, _wmktem](mktemp-wmktemp.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.

## <a name="syntax"></a>Syntax

```C
errno_t _mktemp_s(
   char *nameTemplate,
   size_t sizeInChars
);
errno_t _wmktemp_s(
   wchar_t *nameTemplate,
   size_t sizeInChars
);
template <size_t size>
errno_t _mktemp_s(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
errno_t _wmktemp_s(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Parameter

*nameTemplate*<br/>
Muster des Dateinamens.

*sizeInChars*<br/>
Größe des Puffers in Einzelbyte-Zeichen in **_mktemp_s**; Breite Zeichen **_wmktemp_s**, einschließlich null-Abschlusszeichen.

## <a name="return-value"></a>Rückgabewert

Beide Funktionen geben bei Erfolg null und bei Fehlern einen Fehlercode zurück.

### <a name="error-conditions"></a>Fehlerbedingungen

|*nameTemplate*|*sizeInChars*|Rückgabewert|Neuen Wert im *NameTemplate*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|alle|**EINVAL**|**NULL**|
|Falsches Format (finden Sie unter "Hinweise" im Abschnitt für das richtige Format)|alle|**EINVAL**|Leere Zeichenfolge|
|alle|<= Anzahl von X|**EINVAL**|Leere Zeichenfolge|

Wenn eine der oben genannten Fehlerbedingungen auftritt, wird ein Handler für ungültige Parameter aufgerufen (siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** festgelegt ist, um **EINVAL** und die Funktionen gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_mktemp_s** -Funktion erstellt einen eindeutigen Dateinamen an, durch das Ändern der *NameTemplate* Argument, damit nach dem Aufruf der *NameTemplate* Zeiger verweist auf eine Zeichenfolge enthält den neuen Dateinamen an. **_mktemp_s** Multibyte-Zeichenfolgenargumente nach Bedarf, Erkennung von Multibyte-Zeichensequenzen entsprechend der multibyte-Codepage derzeit vom System zur Laufzeit automatisch behandelt. **_wmktemp_s** ist eine Breitzeichen-Version von **_mktemp_s**; das Argument der **_wmktemp_s** ist eine Breitzeichen-Zeichenfolge. **_wmktemp_s** und **_mktemp_s** Verhalten sich andernfalls identisch, außer dass **_wmktemp_s** verarbeitet keine Multibyte-Zeichenfolgen.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

Die *NameTemplate* Argument hat das Format **BaseXXXXXX**, wobei *Basis* ist der Teil der neuen Dateinamen ein, den Sie angeben, und jedes "X" ein Platzhalter für ein Zeichen, das vom **_mktemp_s**. Jede Platzhalterzeichen in *NameTemplate* muss einen Großbuchstaben x **_mktemp_s** behält *Basis* und ersetzt das erste nachfolgende "X" mit einem alphanumerischen Zeichen. **_mktemp_s** ersetzt die folgenden nachgestellten x mit einem Wert fünfstellige; dieser Wert ist eine eindeutige Identifikationsnummer der aufrufende Prozess, oder in Multithreadprogrammen den aufrufenden Thread.

Jeden erfolgreichen Aufruf von **_mktemp_s** ändert *NameTemplate*. Bei jedem nachfolgenden Aufruf aus dem gleichen Prozess oder Thread mit dem gleichen *NameTemplate* Argument **_mktemp_s** sucht nach Dateinamen, die von zurückgegebene Namen entsprechen **_mktemp_s** in vorherigen aufrufen. Wenn keine Datei für einen angegebenen Namen existiert **_mktemp_s** zurückgegeben. Wenn Dateien vorhanden sind, für alle zuvor Namen zurückgegebenen **_mktemp_s** erstellt einen neuen Namen durch Ersetzen der alphabetischen Zeichens, die sie in den zuvor zurückgegebenen Namen mit den nächsten verfügbaren Kleinbuchstaben enthalten, in der Reihenfolge von "a" bis "Z" verwendet. Z. B. wenn *Basis* ist:

> **fn**

und der fünfstellige-Wert, der vom **_mktemp_s** 12345 ist, wird der erste Name zurückgegeben:

> **fna12345**

Wenn dieser Name verwendet wird, um die Datei FNA12345 erstellen und diese Datei noch vorhanden ist, den Namen des nächste zurückgegeben, bei einem Aufruf von den gleichen Prozess oder Thread mit dem gleichen *Basis* für *NameTemplate* ist:

> **fnb12345**

Ist FNA12345 nicht vorhanden, lautet der nächste zurückgegebene Name erneut:

> **fna12345**

**_mktemp_s** können bis zu 26 eindeutige Dateinamen für eine bestimmte Kombination von erstellen *Basis* und *NameTemplate* Werte. Daher FNZ12345 ist die letzte eindeutiger Dateiname **_mktemp_s** erstellen können, für die *Basis* und *NameTemplate* in diesem Beispiel verwendeten Werte.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```cpp
// crt_mktemp_s.cpp
/* The program uses _mktemp to create
* five unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>

char *fnTemplate = "fnXXXXXX";
char names[5][9];

int main()
{
   int i, err, sizeInChars;
   FILE *fp;

   for( i = 0; i < 5; i++ )
   {
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );
      /* Get the size of the string and add one for the null terminator.*/
      sizeInChars = strnlen(names[i], 9) + 1;
      /* Attempt to find a unique filename: */
      err = _mktemp_s( names[i], sizeInChars );
      if( err != 0 )
         printf( "Problem creating the template" );
      else
      {
         if( fopen_s( &fp, names[i], "w" ) == 0 )
            printf( "Unique filename is %s\n", names[i] );
         else
            printf( "Cannot open %s\n", names[i] );
         fclose( fp );
      }
   }

   return 0;
}
```

### <a name="sample-output"></a>Beispielausgabe

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>Siehe auch

[Dateibehandlung](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
