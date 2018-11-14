---
title: fopen, _wfopen
ms.date: 11/04/2016
apiname:
- _wfopen
- fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
ms.openlocfilehash: 1397f3b3513fc9a3e93a69841a93b40c16e490cf
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51333227"
---
# <a name="fopen-wfopen"></a>fopen, _wfopen

Öffnet eine Datei. Es sind sicherere Versionen dieser Funktionen verfügbar, die eine zusätzliche Parameterüberprüfung durchführen und Fehlercodes zurückgeben. Siehe dazu [fopen_s, _wfopen_s](fopen-s-wfopen-s.md).

## <a name="syntax"></a>Syntax

```C
FILE *fopen(
   const char *filename,
   const char *mode
);
FILE *_wfopen(
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Dateiname

*mode*<br/>
Art des Zugriffs, der aktiviert ist.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf die geöffnete Datei zurück. Ein NULL-Zeigerwert gibt einen Fehler an. Wenn *Filename* oder *Modus* ist **NULL** oder eine leere Zeichenfolge ist, lösen diese Funktionen den Handler für ungültige Parameter, dies wird im beschrieben [Parameter Überprüfung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **NULL** und **Errno** zu **EINVAL**.

Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **Fopen** -Funktion öffnet die Datei, die angegebenen *Filename*. Standardmäßig werden in einer schmalen *Filename* Zeichenfolge mit der ANSI-Codepage (CP_ACP) interpretiert. In Windows-Desktopanwendungen kann dies in die OEM-Codepage (CP_OEMCP) geändert werden, indem Sie die [SetFileApisToOEM](/windows/desktop/api/fileapi/nf-fileapi-setfileapistooem) -Funktion verwenden. Können Sie die [AreFileApisANSI](/windows/desktop/api/fileapi/nf-fileapi-arefileapisansi) Funktion, um zu bestimmen, ob *Filename* wird unter Verwendung des ANSI- oder der standardmäßigen OEM-Codepage interpretiert. **_wfopen** ist eine Breitzeichen-Version von **Fopen**; die Argumente für **_wfopen** sind Breitzeichen Zeichenfolgen. Andernfalls **_wfopen** und **Fopen** Verhalten sich identisch. Nur **_wfopen** wirkt sich nicht auf den codierten Zeichensatz, der im Dateistream verwendet wird.

**Fopen** akzeptiert Pfade, die im Dateisystem, zum Zeitpunkt der Ausführung; gültig sind **Fopen** akzeptiert UNC-Pfade und Pfade mit zugeordneten Netzlaufwerken, solange das System, den Code ausführt, Zugriff auf die Freigabe verfügt oder einem zugeordneten Laufwerk zum Zeitpunkt der Ausführung. Beim Erstellen von Pfaden für **Fopen**, stellen Sie sicher, dass Laufwerke, Pfade oder Netzwerkfreigaben in der ausführungsumgebung verfügbar sind. Als Verzeichnistrennzeichen in einem Pfad können Sie entweder den Schrägstrich (/) oder den umgekehrten Schrägstrich (\\) verwenden.

Überprüfen Sie stets den Rückgabewert, um zu ermitteln, ob der Zeiger NULL ist, bevor Sie weitere Vorgänge mit der Datei ausführen. Wenn ein Fehler auftritt, die globale Variable **Errno** festgelegt und kann verwendet werden, um bestimmte Fehlerinformationen abzurufen. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="unicode-support"></a>Unterstützung für Unicode

**Fopen** unterstützt Unicode-Dateistreams. Um eine Unicode-Datei zu öffnen, geben eine **ccs** Flag, das angibt, das die gewünschte Codierung zu **Fopen**wie folgt.

> **Datei *fp Fopen = ("newfile.txt", "rt und höher, ccs =**_Codierung_**");**

Zulässige Werte von *Codierung* sind **UNICODE**, **UTF-8**, und **UTF-16LE**.

Wenn eine Datei im Unicode-Modus geöffnet wird, übersetzen Eingabefunktionen die Daten, die aus der Datei in UTF-16-Daten als Typ gelesen werden **"wchar_t"**. Funktionen, die für eine im Unicode-Modus geöffnete Datei zu schreiben, erwarten Puffer, die UTF-16-Daten als Typ enthalten **"wchar_t"**. Wenn eine Datei als UTF-8 kodiert ist, dann werden UTF-16-Daten beim Schreiben in UTF-8 übersetzt, und die UTF-8-kodierten Inhalte der Datei werden beim Lesen in UTF-16 übersetzt. Der Versuch, eine ungerade Anzahl von Bytes im Unicode-Modus zu lesen oder zu schreiben, führt zu einem [Parametervalidierungsfehler](../../c-runtime-library/parameter-validation.md) . Wenn Sie Daten lesen oder schreiben möchten, die in Ihrem Programm als UTF-8 gespeichert sind, verwenden Sie den Text- oder Binärdateienmodus anstelle eines Unicode-Modus. Sie sind für jede erforderliche Kodierungsübersetzung verantwortlich.

Wenn die Datei bereits vorhanden ist und zum Lesen oder Anhängen geöffnet ist, bestimmt die Bytereihenfolge-Marke (BOM), sofern in der Datei vorhanden, die Codierung. Die BOM-Codierung hat Vorrang vor der Codierung, die angegeben wird die **ccs** Flag. Die **ccs** -Codierung wird nur verwendet werden, wenn keine BOM vorhanden ist, oder die Datei eine neue Datei ist.

> [!NOTE]
> BOM-Erkennung gilt nur für Dateien, die im Unicode-Modus geöffnet werden (das heißt durch Übergeben der **ccs** Flag).

Die folgende Tabelle enthält die Modi, die für verschiedene **ccs** Flags für **Fopen** und Bytereihenfolge-Marken in der Datei.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Verwendete Codierungen auf Grundlage von ccs-Flag und BOM

|CCS-flag|Keine BOM (oder neue Datei)|BOM: UTF-8|BOM: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

In Dateien, die zum Schreiben im Unicode-Modus geöffnet sind, wird automatisch eine BOM geschrieben.

Wenn *Modus* ist **"a, ccs =**_Codierung_**"**, **Fopen** versucht zuerst, öffnen Sie die Datei mit Lese- und Schreibzugriff. Ist der Vorgang erfolgreich, liest die Funktion die BOM, um die Codierung für die Datei zu bestimmen. Schlägt der Vorgang fehl, verwendet die Funktion die Standardcodierung für die Datei. In beiden Fällen **Fopen** wird erneut öffnen Sie die Datei mit Schreibschutz. (Dies gilt für **"a"** Modus nicht nur **"a +"** Modus.)

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen**|**fopen**|**fopen**|**_wfopen**|

Die Zeichenfolge *Modus* gibt die Art des Zugriffs, die wie folgt für die Datei angefordert wird.

|*mode*|Zugriff|
|-|-|
| **"r"** | Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder wurde nicht gefunden, die **Fopen** -Aufruf fehl. |
| **"w"** | Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a“** | Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei (Anfügen) geöffnet, ohne die EOF-Markierung (end-of-file, Dateiende) zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist. |
| **„r+“** | Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein. |
| **„w+“** | Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a+“** | Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen der EOF-Markierung, bevor neue Daten in die Datei geschrieben werden. Die EOF-Markierung wird nach Abschluss des Schreibvorgangs nicht wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist. |

Wenn eine Datei geöffnet wird, mithilfe der **"a"** Zugriffstyp oder **"a +"** Zugriffstyp am Ende der Datei erfolgen alle Schreibvorgänge. Der Dateizeiger kann mit [Fseek](fseek-fseeki64.md) oder [rewind](rewind.md), jedoch ist immer an das Ende der Datei bevor ein Schreibvorgang ausgeführt. Daher können vorhandene Daten nicht überschrieben werden.

Die **"a"** Modus wird die EOF-Markierung nicht entfernt, bevor sie an der Datei angefügt. Nach dem Anfügen werden durch den MS-DOS-Befehl TYPE nur Daten bis zur ursprünglichen EOF-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Bevor sie an der Datei angefügt der **"a +"** Modus wird die EOF-Markierung entfernt. Nach dem Anhängen werden mit dem Befehl MS-DOS TYPE alle Daten in der Datei angezeigt. Die **"a +"** Modus ist erforderlich, zum Anfügen an eine streamdatei, die mit der STRG + Z EOF-Markierung beendet wird.

Wenn die **"R +"**, **"w +"**, oder **"a +"** angegeben wird, Lese- und Schreibvorgänge aktiviert sind (die Datei gilt als für "Update" geöffnet). Wenn Sie jedoch vom Lesevorgang in den Schreibvorgang wechseln, muss die Eingabeoperation eine EOF-Markierung antreffen. Wenn keine EOF-Markierung vorhanden ist, müssen Sie einen zwischenzeitlichen Aufruf einer dateipositionierenden Funktion verwenden. Die dateipositionierenden Funktionen sind **Fsetpos**, [Fseek](fseek-fseeki64.md), und [rewind](rewind.md). Wenn Sie vom Schreibvorgang in den Lesevorgang wechseln, müssen Sie einen zwischenzeitlichen Aufruf von verwenden **Fflush** oder einer dateipositionierenden Funktion.

Neben früheren Werte können die folgenden Zeichen können an angehängt werden *Modus* um den Übersetzungsmodus für Zeilenumbruchzeichen anzugeben.

|*Modus* Modifizierer|Commit-Modus|
|-|-|
| **t** | Öffnen im Textmodus (übersetzt). |
| **b** | Öffnen im binären (unübersetzten) Modus; Übersetzungen von Wagenrücklauf- und Zeilenvorschubzeichen werden unterdrückt. |

Im Textmodus wird STRG + Z als EOF-Zeichen bei Eingabe interpretiert. In Dateien, die geöffnet werden für das Lesen/Schreiben mit **"a +"**, **Fopen** STRG + Z am Ende der Datei überprüft und entfernt, wenn es möglich ist. Dies geschieht, da mit [Fseek](fseek-fseeki64.md) und **Ftell** zum Navigieren innerhalb einer Datei, die mit STRG + Z endet verursachen [Fseek](fseek-fseeki64.md) am Ende der Datei nicht ordnungsgemäß verhält.

Im Textmodus Carriage Return-Zeilenvorschub-Kombinationen in einzelne Zeilenvorschübe bei Eingabe übersetzt, und Zeilenvorschubzeichen in Carriage Return-Zeilenvorschub-Kombinationen, bei der Ausgabe übersetzt werden. Wenn eine Stream-E/A-Funktion von Unicode im Textmodus (Standard) funktioniert, wird angenommen, dass es sich bei Quell- oder Zielstream um eine Sequenz von Multibytezeichen handelt. Daher konvertieren die Unicode-Streameingabefunktionen Multibytezeichen in Breitzeichen (wie bei einem Aufruf der **mbtowc**-Funktion). Aus demselben Grund konvertieren die Unicode-Streamausgabefunktionen Breitzeichen in Multibytezeichen (wie bei einem Aufruf der **wctomb**-Funktion).

Wenn **t** oder **b** nicht erhält, *Modus*, wird der standardübersetzungsmodus durch die globale Variable definiert [_fmode](../../c-runtime-library/fmode.md). Wenn **t** oder **b** ist das Argument, die Funktion schlägt fehl und gibt mit dem Präfix **NULL**.

Weitere Informationen darüber, wie Sie Textmodus und Binärmodus in Unicode und im Multibyte-Stream-E/A verwenden, finden Sie unter [Text and Binary Mode File I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

Die folgenden Optionen können angehängt werden, um *Modus* zusätzliche Verhaltensweisen angeben.

|*Modus* Modifizierer|Verhalten|
|-|-|
| **c** | Aktivieren Sie das commitflag für den zugeordneten *Filename* , damit der Inhalt des Dateipuffers direkt, wenn entweder auf den Datenträger geschrieben werden **Fflush** oder **_flushall** aufgerufen wird. |
| **n** | Zurücksetzen der Commit-Flag für das zugeordnete *Filename* auf "No-Commit". Dies ist die Standardeinstellung. Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit COMMODE.OBJ verknüpfen. Der Standardwert des globalen Commitflags lautet "no-commit", es sei denn, Sie verknüpfen das Programm explizit mit COMMODE.OBJ (siehe [Link Options](../../c-runtime-library/link-options.md)). |
| **N** | Gibt an, dass die Datei nicht von untergeordneten Prozessen geerbt wird. |
| **S** | Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist. |
| **R** | Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist. |
| **T** | Gibt an, dass eine Datei temporär ist. Wenn möglich, wird sie nicht auf den Datenträger geschrieben. |
| **D** | Gibt an, dass eine Datei temporär ist. Sie wird gelöscht, wenn der letzte Dateizeiger geschlossen wird. |
| **CCS =**_Codierung_ | Gibt den codierten Zeichensatz verwenden (eines **UTF-8**, **UTF-16LE**, oder **UNICODE**) für diese Datei. Machen Sie keine Angabe, wenn Sie ANSI-Codierung wünschen. |

Gültige Zeichen für die *Modus* Zeichenfolge, die verwendet wird **Fopen** und **_fdopen** entsprechen *Oflag* Argumente, die in verwendetwerden[_open](open-wopen.md) und [_sopen](sopen-wsopen.md)wie folgt.

|Zeichen in *Modus* Zeichenfolge|Entsprechende *Oflag* Wert für _open/_sopen|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (in der Regel **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_APPEND **)|
|**a +**|**_O_RDWR** &#124; **_O_APPEND** (in der Regel **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**R +**|**_O_RDWR**|
|**W**|**_O_WRONLY** (in der Regel **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC **)|
|**w +**|**_O_RDWR** (in der Regel **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**c**|Keiner|
|**n**|Keiner|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**CCS = UNICODE**|**_O_WTEXT**|
|**CCS = UTF-8**|**"_O_UTF8"**|
|**CCS = UTF-16LE**|**"_O_UTF16"**|

Bei Verwendung von **Rb** Modus, Sie haben keinen zum Portieren von Code, und wenn Sie erwarten, dass die meisten einer großen Datei lesen oder sind keine Bedenken bezüglich der netzwerkleistung, Sie könnten auch erwägen, ob der arbeitsspeichernutzung Win32-Dateien als Option zugeordnet.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fopen**|\<stdio.h>|
|**_wfopen**|\<stdio.h> oder \<wchar.h>|

**_wfopen** ist eine Microsoft-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

Die **c**, **n**, **t**, **S**, **R**, **T**, und **D**  *Modus* Optionen sind Microsoft-Erweiterungen für **Fopen** und **_fdopen** und sollte nicht, wo ANSI-Portabilität gewünscht ist verwendet werden.

## <a name="example-1"></a>Beispiel 1

Das folgende Programm öffnet zwei Dateien.  Er verwendet **Fclose** um die erste Datei zu schließen und **_fcloseall** , alle übrige Dateien zu schließen.

```C
// crt_fopen.c
// compile with: /W3
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   int numclosed;

   // Open for read (will fail if file "crt_fopen.c" does not exist)
   if( (stream  = fopen( "crt_fopen.c", "r" )) == NULL ) // C4996
   // Note: fopen is deprecated; consider using fopen_s instead
      printf( "The file 'crt_fopen.c' was not opened\n" );
   else
      printf( "The file 'crt_fopen.c' was opened\n" );

   // Open for write
   if( (stream2 = fopen( "data2", "w+" )) == NULL ) // C4996
      printf( "The file 'data2' was not opened\n" );
   else
      printf( "The file 'data2' was opened\n" );

   // Close stream if it is not NULL
   if( stream)
   {
      if ( fclose( stream ) )
      {
         printf( "The file 'crt_fopen.c' was not closed\n" );
      }
   }

   // All other files are closed:
   numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="example-2"></a>Beispiel 2

Das folgende Programm erstellt eine Datei (oder überschreibt eine, sofern vorhanden) im Textmodus mit Unicode-Codierung.  Anschließend schreibt es zwei Zeichenfolgen in die Datei und schließt sie. Die Ausgabe ist eine Datei namens _wfopen_test.xml, die die Daten aus dem Ausgangsabschnitt enthält.

```C
// crt__wfopen.c
// compile with: /W3
// This program creates a file (or overwrites one if
// it exists), in text mode using Unicode encoding.
// It then writes two strings into the file
// and then closes the file.

#include <stdio.h>
#include <stddef.h>
#include <stdlib.h>
#include <wchar.h>

#define BUFFER_SIZE 50

int main(int argc, char** argv)
{
    wchar_t str[BUFFER_SIZE];
    size_t  strSize;
    FILE*   fileHandle;

    // Create an the xml file in text and Unicode encoding mode.
    if ((fileHandle = _wfopen( L"_wfopen_test.xml",L"wt+,ccs=UNICODE")) == NULL) // C4996
    // Note: _wfopen is deprecated; consider using _wfopen_s instead
    {
        wprintf(L"_wfopen failed!\n");
        return(0);
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"<xmlTag>\n");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Write a string into the file.
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"</xmlTag>");
    strSize = wcslen(str);
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)
    {
        wprintf(L"fwrite failed!\n");
    }

    // Close the file.
    if (fclose(fileHandle))
    {
        wprintf(L"fclose failed!\n");
    }
    return 0;
}
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
