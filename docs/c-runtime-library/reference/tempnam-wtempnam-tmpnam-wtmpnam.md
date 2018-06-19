---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55ff069d72d68493eee524ea2f9c012d2fc7f534
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417012"
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam

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
Die Zeichenfolge, die von zurückgegebenen Namen vorangestellt werden **_tempnam**.

*dir*<br/>
Der im Dateinamen verwendete Pfad, wenn es keine TMP-Umgebungsvariable gibt oder wenn TMP kein gültiges Verzeichnis ist.

*str*<br/>
Zeiger, der den generierten Namen enthält und mit dem von der Funktion zurückgegebenen Namen identisch ist. Dies ist eine einfache Möglichkeit, den generierten Namen zu speichern.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf den Namen generiert oder **NULL** , wenn ein Fehler auftritt. Fehler kann auftreten, wenn Sie versuchen, mehr als **TMP_MAX** (Siehe STDIO. H) Aufrufe mit **Tmpnam** oder bei Verwendung von **_tempnam** und es ist ein Ungültiger Verzeichnisname angegeben, in der TMP-Umgebungsvariable und die *Dir* Parameter.

> [!NOTE]
> Der zurückgegebene Zeiger **Tmpnam** und **_wtmpnam** zeigen Sie auf internen statischen Puffer. [free](free.md) sollte nicht aufgerufen werden, um die Zuordnung dieser Zeiger aufzuheben. **Kostenlose** muss aufgerufen werden, damit von belegte Zeiger **_tempnam** und **_wtempnam**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen gibt den Namen einer Datei zurück, die derzeit nicht vorhanden ist. **Tmpnam** gibt einen Namen in das aktuelle Arbeitsverzeichnis eindeutig und **_tempnam** können Sie einen eindeutigen Namen in einem Verzeichnis als dem aktuellen Objekt zu generieren. Wenn einem Dateinamen ohne Pfadinformationen ein umgekehrter Schrägstrich vorangestellt ist, wie z.B. \fname21, weist dies darauf hin, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.

Für **Tmpnam**, können Sie im generierten Dateinamen speichern *str*. Wenn *str* ist **NULL**, klicken Sie dann **Tmpnam** bewirkt, dass das Ergebnis in einer statischen internen Puffer. Alle nachfolgenden Aufrufe zerstören deshalb diesen Wert. Der Name von generierten **Tmpnam** besteht aus einem Programm generierten Dateinamen und nach dem ersten Aufruf von **Tmpnam**, einer Erweiterung von aufeinander folgenden Nummern Basis 32 (.1-.vvu When **TMP_MAX**  in STDIO. H beträgt 32.767.).

**_tempnam** generiert einen eindeutigen Dateinamen für ein Verzeichnis ausgewählt werden, indem Sie die folgenden Regeln:

- Wenn die TMP-Umgebungsvariable definiert und auf einen gültigen Verzeichnisnamen festgelegt ist, werden eindeutige Dateinamen für das von TMP angegebene Verzeichnis generiert.

- Wenn die TMP-Umgebungsvariable nicht definiert ist, oder wenn sie auf den Namen eines Verzeichnisses festgelegt ist, die nicht vorhanden ist, **_tempnam** verwendet die *Dir* Parameter als Pfad für die sie eindeutige Namen generiert.

- Wenn die TMP-Umgebungsvariable nicht definiert ist oder wenn sie auf den Namen eines Verzeichnisses festgelegt ist, die nicht vorhanden ist und wenn *Dir* handelt es sich um **NULL** oder legen Sie auf den Namen eines Verzeichnisses, das nicht existiert, **_ Tempnam** wird das aktuelle Arbeitsverzeichnis verwenden, um eindeutige Namen zu generieren. Aktuell, wenn beide TMP und *Dir* Namen von Verzeichnissen, die nicht vorhanden sind, geben die **_tempnam** Funktionsaufruf fehl.

Der zurückgegebene Name **_tempnam** werden eine Verkettung der *Präfix* und eine sequenzielle Zahl, die kombiniert werden, um einen eindeutigen Dateinamen an, für das angegebene Verzeichnis zu erstellen. **_tempnam** generiert Dateinamen, die keine Erweiterung aufweisen. **_tempnam** verwendet ["malloc"](malloc.md) Arbeitsspeicher für den Dateinamen; das Programm ist verantwortlich für die Freigabe dieser Speicherplatz, wenn er nicht mehr benötigt wird.

**_tempnam** und **Tmpnam** Handle Multibyte-Zeichenfolgen Zeichenfolgenargumente, wobei Multibyte-Zeichensequenzen entsprechend der OEM-Codepage erkannt automatisch abgerufen, von dem Betriebssystem. **_wtempnam** ist eine Breitzeichen-Version von **_tempnam**; die Argumente und der Rückgabewert von **_wtempnam** sind Zeichenfolgen mit Breitzeichen. **_wtempnam** und **_tempnam** Verhalten sich identisch, außer dass **_wtempnam** verarbeitet keine Multibyte-Zeichenfolgen. **_wtmpnam** ist eine Breitzeichen-Version von **Tmpnam**; der Wert Argument- und Rückgabetypen der **_wtmpnam** sind Zeichenfolgen mit Breitzeichen. **_wtmpnam** und **Tmpnam** Verhalten sich identisch, außer dass **_wtmpnam** verarbeitet keine Multibyte-Zeichenfolgen.

Wenn **_DEBUG** und **_CRTDBG_MAP_ALLOC** definiert sind, **_tempnam** und **_wtempnam** werden durch Aufrufe von ersetzt [_tempnam _dbg und _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md).

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam**|**tmpnam**|**tmpnam**|**_wtmpnam**|
|**_ttempnam**|**_tempnam**|**_tempnam**|**_wtempnam**|

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
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
// current working directory, then uses _tempnam to create
// a unique filename with a prefix of stq.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char* name1 = NULL;
   char* name2 = NULL;

   // Create a temporary filename for the current working directory:
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996
   // Note: tmpnam is deprecated; consider using tmpnam_s instead
      printf( "%s is safe to use as a temporary file.\n", name1 );
   else
      printf( "Cannot create a unique filename\n" );

   // Create a temporary filename in temporary directory with the
   // prefix "stq". The actual destination directory may vary
   // depending on the state of the TMP environment variable and
   // the global variable P_tmpdir.

   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )
      printf( "%s is safe to use as a temporary file.\n", name2 );
   else
      printf( "Cannot create a unique filename\n" );

   // When name2 is no longer needed :
   if(name2)
     free(name2);

}
```

```Output
\s1gk. is safe to use as a temporary file.
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile](tmpfile.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
