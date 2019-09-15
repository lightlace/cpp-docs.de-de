---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam
ms.date: 11/04/2016
api_name:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
ms.openlocfilehash: 9fd1eb9f2f718afec5b7d5555145fcd7e5cc17cf
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957520"
---
# <a name="_tempnam-_wtempnam-tmpnam-_wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

Generiert Namen, die Sie verwenden können, um temporäre Dateien zu erstellen. Sicherere Versionen einiger dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [tmpnam_s, _wtmpnam_s](tmpnam-s-wtmpnam-s.md).

## <a name="syntax"></a>Syntax

```C
char *_tempnam(
   const char *dir,
   const char *prefix
);
wchar_t *_wtempnam(
   const wchar_t *dir,
   const wchar_t *prefix
);
char *tmpnam(
   char *str
);
wchar_t *_wtmpnam(
   wchar_t *str
);
```

### <a name="parameters"></a>Parameter

*prefix*<br/>
Die Zeichenfolge, die den von **_tempnam**zurückgegebenen Namen vorangestellt wird.

*dir*<br/>
Der im Dateinamen verwendete Pfad, wenn es keine TMP-Umgebungsvariable gibt oder wenn TMP kein gültiges Verzeichnis ist.

*str*<br/>
Zeiger, der den generierten Namen enthält und mit dem von der Funktion zurückgegebenen Namen identisch ist. Dies ist eine einfache Möglichkeit, den generierten Namen zu speichern.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf den generierten Namen oder **null** zurück, wenn ein Fehler auftritt. Ein Fehler kann auftreten, wenn Sie mehr als **TMP_MAX** versuchen (siehe stdio). H) wird mit **tmpnam** aufgerufen, oder wenn Sie **_tempnam** verwenden und in der TMP-Umgebungsvariablen und im *dir* -Parameter ein ungültiger Verzeichnisname angegeben ist.

> [!NOTE]
> Die von **tmpnam** und **_wtmpnam** zurückgegebenen Zeiger zeigen auf interne statische Puffer. [free](free.md) sollte nicht aufgerufen werden, um die Zuordnung dieser Zeiger aufzuheben. für Zeiger, die von **_tempnam** und **_wtempnam**zugeordnet werden, muss **Free** aufgerufen werden.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen gibt den Namen einer Datei zurück, die derzeit nicht vorhanden ist. **tmpnam** gibt einen Namen zurück, der im angegebenen temporären Windows-Verzeichnis, das von [gettemppathw](/windows/win32/api/fileapi/nf-fileapi-gettemppathw)zurückgegeben wurde, eindeutig ist. tempnam generiert einen eindeutigen Namen in einem anderen Verzeichnis als dem vorgesehenen.  **\_** Wenn einem Dateinamen ohne Pfadinformationen ein umgekehrter Schrägstrich vorangestellt ist, wie z.B. \fname21, weist dies darauf hin, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.

Für **tmpnam**können Sie diesen generierten Dateinamen in *Str*speichern. Wenn *Str* **null**ist, verlässt **tmpnam** das Ergebnis in einem internen statischen Puffer. Alle nachfolgenden Aufrufe zerstören deshalb diesen Wert. Der von **tmpnam** generierte Name besteht aus einem Programm generierten Dateinamen und nach dem ersten **tmpnam**-Rückruf eine Dateierweiterung von sequenziellen Zahlen in Basis 32 (... vvu, wenn **TMP_MAX** in stdio. H ist 32.767).

**_tempnam** generiert einen eindeutigen Dateinamen für ein Verzeichnis, das durch die folgenden Regeln ausgewählt wird:

- Wenn die TMP-Umgebungsvariable definiert und auf einen gültigen Verzeichnisnamen festgelegt ist, werden eindeutige Dateinamen für das von TMP angegebene Verzeichnis generiert.

- Wenn die TMP-Umgebungsvariable nicht definiert ist oder wenn Sie auf den Namen eines nicht vorhandenen Verzeichnisses festgelegt ist, verwendet **_tempnam** den *dir* -Parameter als Pfad, für den eindeutige Namen generiert werden.

- Wenn die TMP-Umgebungsvariable nicht definiert ist oder wenn Sie auf den Namen eines Verzeichnisses festgelegt ist, das nicht vorhanden ist, und wenn *dir* entweder **null** ist oder auf den Namen eines nicht vorhandenen Verzeichnisses festgelegt ist, verwendet **_tempnam** das aktuelle Arbeitsverzeichnis für das-Objekt. Bewerten Sie eindeutige Namen. Wenn sowohl tmp als auch *dir* Namen von Verzeichnissen angeben, die nicht vorhanden sind, kann der **_tempnam** -Funktions Aufrufvorgang nicht ausgeführt werden.

Der von **_tempnam** zurückgegebene Name ist eine Verkettung von *Präfix* und eine sequenzielle Zahl, die kombiniert wird, um einen eindeutigen Dateinamen für das angegebene Verzeichnis zu erstellen. **_tempnam** generiert Dateinamen, die keine Erweiterung haben. **_tempnam** verwendet [malloc](malloc.md) , um Speicherplatz für den Dateinamen zuzuweisen. Das Programm ist dafür verantwortlich, diesen Speicherplatz freizugeben, wenn er nicht mehr benötigt wird.

**_tempnam** und **tmpnam** behandeln nach Bedarf automatisch Multibyte-Zeichen folgen Argumente und erkennen Multibyte-Zeichen folgen entsprechend der OEM-Codepage, die vom Betriebssystem abgerufen wird. **_wtempnam** ist eine breit Zeichen Version von **_tempnam**. die Argumente und der Rückgabewert von **_wtempnam** sind Zeichen folgen mit breit Zeichen. **_wtempnam** und **_tempnam** Verhalten sich identisch, mit dem Unterschied, dass **_wtempnam** keine Multibyte-Zeichen folgen verarbeitet. **_wtmpnam** ist eine breit Zeichen Version von **tmpnam**. Das Argument und der Rückgabewert von **_wtmpnam** sind Zeichen folgen mit breit Zeichen. **_wtmpnam** und **tmpnam** Verhalten sich identisch, mit dem Unterschied, dass **_wtmpnam** keine Multibyte-Zeichen folgen verarbeitet.

Wenn **_DEBUG** und **_CRTDBG_MAP_ALLOC** definiert sind, werden **_tempnam** und **_wtempnam** durch Aufrufe von [_tempnam_dbg und _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md)ersetzt.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tmpnam**|**tmpnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_tempnam**|\<stdio.h>|
|**_wtempnam**, **_wtmpnam**|\<stdio.h> oder \<wchar.h>|
|**tmpnam**|\<stdio.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_tempnam.c
// compile with: /W3
// This program uses tmpnam to create a unique filename in the
// temporary directory, and _tempname to create a unique filename
// in C:\\tmp.

#include <stdio.h>
#include <stdlib.h>

int main(void)
{
   char * name1 = NULL;
   char * name2 = NULL;
   char * name3 = NULL;

   // Create a temporary filename for the current working directory:
   if ((name1 = tmpnam(NULL)) != NULL) { // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf("%s is safe to use as a temporary file.\n", name1);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if ((name2 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name2);
   } else {
      printf("Cannot create a unique filename\n");
   }

   // When name2 is no longer needed:
   if (name2) {
      free(name2);
   }

   // Unset TMP environment variable, then create a temporary filename in C:\tmp.
   if (_putenv("TMP=") != 0) {
      printf("Could not remove TMP environment variable.\n");
   }

   // With TMP unset, we will use C:\tmp as the temporary directory.
   // Create a temporary filename in C:\tmp with prefix "stq".
   if ((name3 = _tempnam("c:\\tmp", "stq")) != NULL) {
      printf("%s is safe to use as a temporary file.\n", name3);
   }
   else {
      printf("Cannot create a unique filename\n");
   }

   // When name3 is no longer needed:
   if (name3) {
      free(name3);
   }

   return 0;
}
```

```Output
C:\Users\LocalUser\AppData\Local\Temp\sriw.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\stq2 is safe to use as a temporary file.
c:\tmp\stq3 is safe to use as a temporary file.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
