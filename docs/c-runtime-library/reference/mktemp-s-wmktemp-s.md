---
title: _mktemp_s, _wmktemp_s
ms.date: 11/04/2016
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
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
ms.openlocfilehash: fef10f2cfbcc0332741d560a41a782b70ed14798
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156535"
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
Größe des Puffers in Einzelbytezeichen in **_mktemp_s**; Breitzeichen Zeichen **_wmktemp_s**, einschließlich null-Terminator.

## <a name="return-value"></a>Rückgabewert

Beide Funktionen geben bei Erfolg null und bei Fehlern einen Fehlercode zurück.

### <a name="error-conditions"></a>Fehlerbedingungen

|*nameTemplate*|*sizeInChars*|Rückgabewert|Neuen Wert im *NameTemplate*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|any|**EINVAL**|**NULL**|
|Falsches Format (finden Sie unter "Hinweise" im Abschnitt für das richtige Format)|any|**EINVAL**|Leere Zeichenfolge|
|any|<= Anzahl von X|**EINVAL**|Leere Zeichenfolge|

Wenn eine der oben genannten Fehlerbedingungen auftritt, wird ein Handler für ungültige Parameter aufgerufen (siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, **Errno** nastaven NA hodnotu **EINVAL** und die Funktionen gibt **EINVAL**.

## <a name="remarks"></a>Hinweise

Die **_mktemp_s** Funktion erstellt einen eindeutigen Dateinamen durch Ändern der *NameTemplate* Argument, damit nach dem Aufruf der *NameTemplate* Zeiger verweist auf eine Zeichenfolge die den neuen Dateinamen enthält. **_mktemp_s** behandelt automatisch Multibyte-Zeichenfolge nach Bedarf erkennt multibytezeichensequenzen gemäß dem multibyte-Codepage derzeit vom System zur Laufzeit. **_wmktemp_s** ist eine Breitzeichen-Version von **_mktemp_s**; das Argument der **_wmktemp_s** ist eine Breitzeichen-Zeichenfolge. **_wmktemp_s** und **_mktemp_s** Verhalten sich andernfalls identisch, außer dass **_wmktemp_s** verarbeitet keine Multibyte-Zeichenfolgen.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

Die *NameTemplate* Argument weist das Format **BaseXXXXXX**, wobei *Basis* ist der Teil den neuen Dateinamen an, die Sie angeben, und jedes X ist ein Platzhalter für ein Zeichen, das vom **_mktemp_s**. Einzelnen Platzhalterzeichen in *NameTemplate* x in Großschreibung angegeben sein **_mktemp_s** behält *Basis* und ersetzt das erste nachgestellte X mit einem alphabetischen Zeichen. **_mktemp_s** ersetzt das nächste nachgestellte x mit einem fünfstelligen Wert; dieser Wert ist eine eindeutige Zahl, die Identifizierung des aufrufenden Prozesses bzw. in Multithreadprogrammen den aufrufenden Thread.

Jeden erfolgreichen Aufruf von **_mktemp_s** ändert *NameTemplate*. Bei jedem darauffolgenden Aufruf aus demselben Prozess oder Thread mit dem gleichen *NameTemplate* Argument **_mktemp_s** sucht nach Dateinamen, die von zurückgegebene Namen entsprechen **_mktemp_s** im Rahmen vorheriger Aufrufe. Wenn keine Datei für den angegebenen Namen existiert **_mktemp_s** diesen Namen zurück. Wenn Dateien vorhanden sind, für alle zuvor Namen zurückgegebenen **_mktemp_s** erstellt einen neuen Namen durch Ersetzen der alphabetischen Zeichens, die sie in den zuvor zurückgegebenen Namen mit der nächsten verfügbaren Kleinbuchstaben, in der Reihenfolge von "a" bis "Z" verwendet. Z. B. wenn *Basis* ist:

> **fn**

Der fünfstellige- Wert, der vom **_mktemp_s** 12345, ist der erste zurückgegebene Name:

> **fna12345**

Wenn dieser Name verwendet wird, um die Datei FNA12345 zu erstellen und diese Datei noch vorhanden ist, der nächste Namen, die bei einem Aufruf aus demselben Prozess oder Thread mit demselben zurückgegebenen *Basis* für *NameTemplate* ist:

> **fnb12345**

Ist FNA12345 nicht vorhanden, lautet der nächste zurückgegebene Name erneut:

> **fna12345**

**_mktemp_s** können bis zu 26 eindeutige Dateinamen für eine beliebige Kombination aus erstellen *Basis* und *NameTemplate* Werte. Daher ist FNZ12345 der letzte eindeutige Dateiname **_mktemp_s** erstellen können, für die *Basis* und *NameTemplate* in diesem Beispiel verwendeten Werte.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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
