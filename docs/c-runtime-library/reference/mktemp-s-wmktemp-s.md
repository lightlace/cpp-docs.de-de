---
title: _mktemp_s, _wmktemp_s
ms.date: 11/04/2016
api_name:
- _mktemp_s
- _wmktemp_s
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 464f0dfbdb0b84e1fd29ec650e53f5c2543c4403
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624210"
---
# <a name="_mktemp_s-_wmktemp_s"></a>_mktemp_s, _wmktemp_s

Vergibt einen eindeutigen Dateinamen. Dabei handelt es sich um Versionen von [_mktemp, _wmktem](mktemp-wmktemp.md) mit den unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschriebenen Erweiterungen.

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

*aufweisen*<br/>
Muster des Dateinamens.

*sizabchars*<br/>
Größe des Puffers in Einzel Byte Zeichen in **_mktemp_s**; breit Zeichen in **_wmktemp_s**, einschließlich des NULL-Terminator.

## <a name="return-value"></a>Rückgabewert

Beide Funktionen geben bei Erfolg null und bei Fehlern einen Fehlercode zurück.

### <a name="error-conditions"></a>Fehlerbedingungen

|*aufweisen*|*sizabchars*|Rückgabewert|Neuer Wert in " *nametemplate* "|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|any|**EINVAL**|**NULL**|
|Falsches Format (siehe Abschnitt "Hinweise" für das richtige Format)|any|**EINVAL**|Leere Zeichenfolge|
|any|<= Anzahl von X|**EINVAL**|Leere Zeichenfolge|

Wenn eine der genannten Fehlerbedingungen auftritt, wird ein Handler für ungültige Parameter aufgerufen (siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md)). Wenn die weitere Ausführung zugelassen wird, wird **errno** auf **EINVAL** festgelegt, und die Funktionen gibt **EINVAL**zurück.

## <a name="remarks"></a>Hinweise

Die **_mktemp_s** -Funktion erstellt einen eindeutigen Dateinamen, indem das *nametemplate* -Argument geändert wird, sodass der *nametemplate* -Zeiger nach dem-Befehl auf eine Zeichenfolge verweist, die den neuen Dateinamen enthält. **_mktemp_s** verarbeitet nach Bedarf automatisch Multibytezeichen-Zeichen folgen Argumente und erkennt multibytezeichensequenzen entsprechend der Multibytezeichen-Codepage, die zurzeit vom Laufzeitsystem verwendet wird. **_wmktemp_s** ist eine breit Zeichen Version von **_mktemp_s**. Das Argument von **_wmktemp_s** ist eine Zeichenfolge mit breit Zeichen. **_wmktemp_s** und **_mktemp_s** Verhalten sich andernfalls identisch, mit der Ausnahme, dass **_wmktemp_s** keine Multibyte-Zeichen folgen verarbeitet.

Die Debug-Bibliotheksversionen dieser Funktionen füllen zunächst den Puffer mit "0xFE" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

Das *nametemplate* -Argument hat das Format **baseXXXXXX**, wobei *Base* der von Ihnen angegebene Teil des neuen Datei namens und jedes X ein Platzhalter für ein Zeichen ist, das von **_mktemp_s**angegeben wird. Jedes Platzhalter Zeichen in *nametemplate* muss ein Großbuchstabe X sein. **_mktemp_s** behält die *Basis* bei und ersetzt das erste nachfolgende x durch ein alphabetisches Zeichen. **_mktemp_s** ersetzt die folgenden nachfolgenden X-Dateien durch einen fünfstelligen Wert. Dieser Wert ist eine eindeutige Zahl, die den aufrufenden Prozess identifiziert, bzw. in Multithreadprogrammen den aufrufenden Thread.

Bei jedem erfolgreichen **_mktemp_s** -Aufrufe wird " *nametemplate" geändert*. Bei jedem nachfolgenden Aufruf desselben Prozesses oder Threads mit demselben *nametemplate* -Argument prüft **_mktemp_s** nach Dateinamen, die mit den Namen übereinstimmen, die in vorherigen Aufrufen von **_mktemp_s** zurückgegeben wurden. Wenn für einen bestimmten Namen keine Datei vorhanden ist, gibt **_mktemp_s** den Namen zurück. Wenn Dateien für alle zuvor zurückgegebenen Namen vorhanden sind, erstellt **_mktemp_s** einen neuen Namen, indem das in dem zuvor zurückgegebenen Namen verwendete alphabetische Zeichen durch den nächsten verfügbaren Kleinbuchstaben (in der angegebenen Reihenfolge) von "a" bis "z" ersetzt wird. Wenn die *Basis* beispielsweise:

> **Extreme**

der von **_mktemp_s** bereitgestellte fünfstellige Wert ist 12345, der erste zurückgegebene Name lautet wie folgt:

> **FNA12345**

Wenn dieser Name verwendet wird, um die Datei zu erstellen FNA12345 und diese Datei immer noch vorhanden ist, lautet der nächste Name, der bei einem Rückruf desselben Prozesses oder Threads mit der gleichen *Basis* für " *nametemplate* " zurückgegeben wird, wie folgt:

> **fnb12345**

Ist FNA12345 nicht vorhanden, lautet der nächste zurückgegebene Name erneut:

> **FNA12345**

**_mktemp_s** kann maximal 26 eindeutige Dateinamen für eine bestimmte Kombination von *Basis* -und *nametemplate* -Werten erstellen. Daher ist FNZ12345 der letzte eindeutige Dateiname **_mktemp_s** der für die *Basis* -und *nametemplate* -Werte erstellt werden kann, die in diesem Beispiel verwendet werden.

In C++ wird die Verwendung dieser Funktionen durch Vorlagenüberladungen vereinfacht; die Überladungen können automatisch Rückschlüsse auf die Pufferlänge ziehen (wodurch kein Größenargument mehr angegeben werden muss), und sie können automatisch die älteren, nicht sicheren Funktionen durch ihre neueren, sicheren Entsprechungen ersetzen. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Compatibility](../../c-runtime-library/compatibility.md).

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
