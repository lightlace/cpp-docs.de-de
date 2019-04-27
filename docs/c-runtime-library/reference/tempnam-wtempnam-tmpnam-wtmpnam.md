---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam
ms.date: 11/04/2016
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
ms.openlocfilehash: 29fa8fc836b1b52bcf66247b3f6aaba47b8c2eaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284867"
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

Jede dieser Funktionen gibt einen Zeiger auf den erzeugten Namen zurück oder **NULL** , wenn ein Fehler auftritt. Fehler kann auftreten, wenn Sie versuchen, mehr als **TMP_MAX** (Siehe STDIO. H) Aufrufe mit **Tmpnam** oder bei Verwendung von **_tempnam** und es ist ein Ungültiger Verzeichnisname angegeben, in der TMP-Umgebungsvariable und die *Dir* Parameter.

> [!NOTE]
> Der zurückgegebene Zeiger **Tmpnam** und **_wtmpnam** zeigen Sie auf die internen statischen Puffer. [free](free.md) sollte nicht aufgerufen werden, um die Zuordnung dieser Zeiger aufzuheben. **Kostenlose** für zugeordnete durch Zeiger aufgerufen werden muss, **_tempnam** und **_wtempnam**.

## <a name="remarks"></a>Hinweise

Jede dieser Funktionen gibt den Namen einer Datei zurück, die derzeit nicht vorhanden ist. **Tmpnam** gibt einen eindeutigen Namen in das angegebene temporäre Verzeichnis mit Windows zurückgegebenes [GetTempPathW](/windows/desktop/api/fileapi/nf-fileapi-gettemppathw). **\_Tempnam** generiert einen eindeutigen Namen in einem Verzeichnis als dem angegebenen. Wenn einem Dateinamen ohne Pfadinformationen ein umgekehrter Schrägstrich vorangestellt ist, wie z.B. \fname21, weist dies darauf hin, dass der Name für das aktuelle Arbeitsverzeichnis gültig ist.

Für **Tmpnam**, können Sie in diesen generierten Dateinamen speichern *str*. Wenn *str* ist **NULL**, klicken Sie dann **Tmpnam** bewirkt, dass das Ergebnis in einem internen statischen Puffer. Alle nachfolgenden Aufrufe zerstören deshalb diesen Wert. Der Name, der vom **Tmpnam** besteht aus einem Programm generierten Dateinamen und nach dem ersten Aufruf von **Tmpnam**, eine Dateierweiterung aus aufeinanderfolgenden Zahlen mit Basis 32 (.1-.vvu, wenn **TMP_MAX**  in STDIO. H beträgt 32.767.).

**_tempnam** generiert einen eindeutigen Dateinamen für ein Verzeichnis, das die folgenden Regeln ausgewählt:

- Wenn die TMP-Umgebungsvariable definiert und auf einen gültigen Verzeichnisnamen festgelegt ist, werden eindeutige Dateinamen für das von TMP angegebene Verzeichnis generiert.

- Wenn die TMP-Umgebungsvariable nicht definiert ist, oder wenn sie auf den Namen eines Verzeichnisses festgelegt ist, die nicht vorhanden ist, **_tempnam** verwendet die *Dir* Parameter als Pfad für die sie eindeutige Namen generiert.

- Wenn die TMP-Umgebungsvariable nicht definiert ist oder wenn sie auf den Namen eines Verzeichnisses festgelegt ist, die nicht vorhanden ist, und wenn *Dir* ist entweder **NULL** oder legen Sie auf den Namen eines Verzeichnisses, das nicht vorhanden ist, **_ Tempnam** wird das aktuelle Arbeitsverzeichnis verwenden, um eindeutige Namen zu generieren. Aktuell, wenn TMP und *Dir* Geben Sie Namen von Verzeichnissen, die nicht vorhanden sind, die **_tempnam** Funktionsaufruf fehl.

Der Name, der vom **_tempnam** werden eine Verkettung von *Präfix* und einer sequentiellen Nummer, die kombiniert werden, um einen eindeutigen Dateinamen für das angegebene Verzeichnis zu erstellen. **_tempnam** generiert Dateinamen, die keine Erweiterung haben. **_tempnam** verwendet [Malloc](malloc.md) zum Zuweisen von Speicherplatz für den Dateinamen des Programms ist verantwortlich für die Freigabe dieses Speicherplatzes, wenn es nicht mehr benötigt wird.

**_tempnam** und **Tmpnam** Handle Multibyte-Zeichensätze Zeichenfolgenargumente, erkennt Multibyte-Zeichenfolgen entsprechend der OEM-Codepage automatisch abgerufen, von dem Betriebssystem. **_wtempnam** ist eine Breitzeichen-Version von **_tempnam**; die Argumente und der Rückgabewert von **_wtempnam** sind Breitzeichen Zeichenfolgen. **_wtempnam** und **_tempnam** Verhalten sich identisch, außer dass **_wtempnam** verarbeitet keine Multibyte-Zeichenfolgen. **_wtmpnam** ist eine Breitzeichen-Version von **Tmpnam**; der Wert Argument- und Rückgabetypen der **_wtmpnam** sind Breitzeichen Zeichenfolgen. **_wtmpnam** und **Tmpnam** Verhalten sich identisch, außer dass **_wtmpnam** verarbeitet keine Multibyte-Zeichenfolgen.

Wenn **_DEBUG** und **_CRTDBG_MAP_ALLOC** definiert sind, **_tempnam** und **_wtempnam** werden durch Aufrufe von ersetzt [_tempnam _dbg und _wtempnam_dbg](tempnam-dbg-wtempnam-dbg.md).

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
