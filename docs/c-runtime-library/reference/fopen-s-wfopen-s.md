---
title: fopen_s, _wfopen_s
ms.date: 11/04/2016
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 1309f991b8251bde7d614aa274d8d2e9da7a8ed3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333325"
---
# <a name="fopens-wfopens"></a>fopen_s, _wfopen_s

Öffnet eine Datei. Diese Versionen von [fopen, _wfopen](fopen-wfopen.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parameter

*pFile*<br/>
Ein Zeiger auf den Dateizeiger, der den Zeiger auf die geöffnete Datei erhält.

*filename*<br/>
Dateiname.

*mode*<br/>
Zugriffstyp zulässig.

## <a name="return-value"></a>Rückgabewert

Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt. Weitere Informationen zu diesen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Fehlerbedingungen

|*pFile*|*filename*|*mode*|Rückgabewert|Inhalt der *pFile*|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|any|any|**EINVAL**|unverändert|
|any|**NULL**|any|**EINVAL**|unverändert|
|any|any|**NULL**|**EINVAL**|unverändert|

## <a name="remarks"></a>Hinweise

Dateien, die durch das geöffnet werden **Fopen_s** und **_wfopen_s** können nicht freigegeben. Wenn eine Datei freigegeben werden soll, verwenden Sie [_fsopen, _wfsopen](fsopen-wfsopen.md) mit der entsprechenden freigabemoduskonstanten – z. B. **_SH_DENYNO** für Lese-/Schreibfreigabe.

Die **Fopen_s** -Funktion öffnet die Datei, die angegebenen *Filename*. **_wfopen_s** ist eine Breitzeichen-Version von **Fopen_s**; die Argumente für **_wfopen_s** sind Breitzeichen Zeichenfolgen. **_wfopen_s** und **Fopen_s** Verhalten sich andernfalls identisch.

**Fopen_s** akzeptiert Pfade, die im Dateisystem, zum Zeitpunkt der Ausführung; gültig sind UNC-Pfade und Pfade mit zugeordneten Netzwerklaufwerken akzeptiert werden, indem **Fopen_s** , solange das System, das der Code ausgeführt wird, Zugriff auf die Freigabe hat oder Netzlaufwerk zum Zeitpunkt der Ausführung zugeordnete. Beim Erstellen von Pfaden für **Fopen_s**, machen Sie keine Annahmen über die Verfügbarkeit von Laufwerken, Pfaden oder Netzwerkfreigaben in der ausführungsumgebung. Als Verzeichnistrennzeichen in einem Pfad können Sie entweder den Schrägstrich (/) oder den umgekehrten Schrägstrich (\\) verwenden.

Diese Funktionen überprüfen ihre Parameter. Wenn *pFile*, *Filename*, oder *Modus* ist ein null-Zeiger wie in beschrieben, generieren diese Funktionen eine Ausnahme für ungültige Parameter, wegen [Parametervalidierung ](../../c-runtime-library/parameter-validation.md).

Überprüfen Sie stets den Rückgabewert, um festzustellen, ob die Funktion erfolgreich war, bevor Sie mit der Datei andere Vorgänge ausführen. Der Fehlercode wird zurückgegeben, wenn ein Fehler auftritt, und die globale Variable **Errno** festgelegt ist. Weitere Informationen finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="unicode-support"></a>Unterstützung für Unicode

**Fopen_s** unterstützt Unicode-Dateistreams. Um eine neue oder vorhandene Unicode-Datei zu öffnen, geben eine *ccs* Flag, das angibt, das die gewünschte Codierung zu **Fopen_s**:

**fopen_s(&fp, "newfile.txt", "rw, ccs=**_encoding_**");**

Zulässige Werte von *Codierung* sind **UNICODE**, **UTF-8**, und **UTF-16LE**. Wenn es kein Wert angegeben wird, für die *Codierung*, **Fopen_s** ANSI-Codierung verwendet.

Wenn die Datei bereits vorhanden ist und zum Lesen oder Anhängen geöffnet ist, bestimmt die Bytereihenfolge-Marke (BOM), sofern in der Datei vorhanden, die Codierung. Die BOM-Codierung hat Vorrang vor der Codierung, die angegeben wird die *ccs* Flag. Die *ccs* -Codierung wird nur verwendet werden, wenn keine BOM vorhanden ist oder wenn die Datei eine neue Datei ist.

> [!NOTE]
> BOM-Erkennung gilt nur für Dateien, die im Unicode-Modus geöffnet werden; Das heißt durch Übergeben der *ccs* Flag.

Die folgende Tabelle fasst die Modi zusammen, für verschiedene *ccs* Flags, die auf erhalten **Fopen_s** und für die Bytereihenfolge-Marken in der Datei.

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Verwendete Codierungen auf Grundlage von ccs-Flag und BOM

|CCS-flag|Keine BOM (oder neue Datei)|BYTEREIHENFOLGE-MARKE: UTF-8|BYTEREIHENFOLGE-MARKE: UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**UTF-16LE**|
|**UTF-16LE**|**UTF-16LE**|**UTF-8**|**UTF-16LE**|

In Dateien, die zum Schreiben im Unicode-Modus geöffnet werden, wird automatisch eine BOM geschrieben.

Wenn *Modus* ist **"a, ccs =**_Codierung_**"**, **Fopen_s** versucht zuerst, die Datei mit Lese-öffnen und Schreibzugriff gewähren. Ist der Vorgang erfolgreich, liest die Funktion die BOM, um die Codierung für die Datei zu bestimmen. Schlägt der Vorgang fehl, verwendet die Funktion die Standardcodierung für die Datei. In beiden Fällen **Fopen_s** erneut öffnet, wird die Datei mit Schreibschutz. (Dies gilt für **eine** Modus nur nicht **a +**.)

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

Die Zeichenfolge *Modus* gibt die Art des Zugriffs, die wie folgt für die Datei angefordert wird.

|*mode*|Zugriff|
|-|-|
| **"r"** | Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder wurde nicht gefunden, die **Fopen_s** -Aufruf fehl. |
| **"w"** | Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a“** | Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei (Anfügen) geöffnet, ohne die EOF-Markierung (end-of-file, Dateiende) zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist. |
| **„r+“** | Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein. |
| **„w+“** | Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a+“** | Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen der EOF-Markierung, bevor neue Daten in die Datei geschrieben werden. Die EOF-Markierung wird nach Abschluss des Schreibvorgangs nicht wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist. |

Wenn eine Datei geöffnet wird, mithilfe der **"a"** oder **"a +"** Zugriffstyp am Ende der Datei erfolgen alle Schreibvorgänge. Der Dateizeiger kann mit [Fseek](fseek-fseeki64.md) oder [rewind](rewind.md), er wird jedoch immer verschoben zurück an das Ende der Datei, bevor ein Schreibvorgang durchgeführt wird, damit vorhandene Daten überschrieben werden können.

Die **"a"** Modus wird nicht die EOF-Markierung entfernt, bevor die Daten an die Datei angefügt. Nach dem Anfügen werden durch den MS-DOS-Befehl TYPE nur Daten bis zur ursprünglichen EOF-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Die **"a +"** Modus wird die EOF-Markierung entfernt, bevor Daten an die Datei angefügt. Nach dem Anhängen werden mit dem Befehl MS-DOS TYPE alle Daten in der Datei angezeigt. Die **"a +"** Modus ist erforderlich, zum Anfügen an eine streamdatei, die mithilfe der STRG + Z EOF-Markierung beendet wird.

Wenn die **"R +"**, **"w +"**, oder **"a +"** angegeben wird, sind Lese- und Schreibvorgänge zulässig. (Die Datei ist dann für ein "Update" geöffnet.) Wenn Sie jedoch vom Lesevorgang in den Schreibvorgang wechseln, muss die Eingabeoperation eine EOF-Markierung antreffen. Wenn keine EOF-Markierung vorhanden ist, müssen Sie einen zwischenzeitlichen Aufruf einer dateipositionierenden Funktion verwenden. Die dateipositionierenden Funktionen sind **Fsetpos**, [Fseek](fseek-fseeki64.md), und [rewind](rewind.md). Wenn Sie vom Schreibvorgang in den Lesevorgang wechseln, müssen Sie einen zwischenzeitlichen Aufruf von verwenden **Fflush** oder einer dateipositionierenden Funktion.

Zusätzlich zu den obigen Werten können können in die folgenden Zeichen enthalten sein *Modus* um den Übersetzungsmodus für Zeilenumbruchzeichen anzugeben:

|*Modus* Modifizierer|Commit-Modus|
|-|-|
| **t** | Öffnen im Textmodus (übersetzt). |
| **b** | Öffnen im binären (unübersetzten) Modus; Übersetzungen von Wagenrücklauf- und Zeilenvorschubzeichen werden unterdrückt. |

Im (übersetzten) Textmodus wird STRG + Z als EOF Zeichen bei Eingabe interpretiert. In den Dateien geöffnet zum Lesen/Schreiben mit **"a +"**, **Fopen_s** STRG + Z am Ende der Datei überprüft und entfernt, wenn möglich die Markierung. Dies geschieht, da mit [Fseek](fseek-fseeki64.md) und **Ftell** zum Navigieren innerhalb einer Datei, die mit STRG + Z, endet kann dazu führen, dass [Fseek](fseek-fseeki64.md) am Ende der Datei nicht ordnungsgemäß verhält.

Darüber hinaus wird im Textmodus Carriage Return-Zeilenvorschub-Kombinationen in einzelne Zeilenvorschübe bei Eingabe übersetzt, und Zeilenvorschubzeichen in Carriage Return-Zeilenvorschub-Kombinationen, bei der Ausgabe übersetzt werden. Wenn eine Stream-E/A-Funktion von Unicode im Textmodus (Standard) funktioniert, wird angenommen, dass es sich bei Quell- oder Zielstream um eine Sequenz von Multibytezeichen handelt. Daher konvertieren die Unicode-Streameingabefunktionen Multibytezeichen in Breitzeichen (wie bei einem Aufruf der **mbtowc**-Funktion). Aus demselben Grund konvertieren die Unicode-Streamausgabefunktionen Breitzeichen in Multibytezeichen (wie bei einem Aufruf der **wctomb**-Funktion).

Wenn **t** oder **b** nicht erhält, *Modus*, wird der standardübersetzungsmodus durch die globale Variable definiert [_fmode](../../c-runtime-library/fmode.md). Wenn **t** oder **b** ist das Argument, die Funktion schlägt fehl und gibt mit dem Präfix **NULL**.

Weitere Informationen zur Anwendung von Text- und Binärmodi in Unicode- und Multibyte-Stream-E/A finden Sie unter [Text- und Binärmodusdatei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicodestream-E/A im Text- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

|*Modus* Modifizierer|Verhalten|
|-|-|
| **c** | Aktivieren Sie das commitflag für den zugeordneten *Filename* , damit der Inhalt des Dateipuffers direkt, wenn entweder auf den Datenträger geschrieben werden **Fflush** oder **_flushall** aufgerufen wird. |
| **n** | Zurücksetzen der Commit-Flag für das zugeordnete *Filename* auf "No-Commit". Dies ist die Standardeinstellung. Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit COMMODE.OBJ verknüpfen. Der Standardwert des globalen Commitflags lautet "no-commit", es sei denn, Sie verknüpfen das Programm explizit mit COMMODE.OBJ (siehe [Link Options](../../c-runtime-library/link-options.md)). |
| **N** | Gibt an, dass die Datei nicht von untergeordneten Prozessen geerbt wird. |
| **S** | Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist. |
| **R** | Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist. |
| **T** | Gibt an, dass eine Datei temporär ist. Wenn möglich, wird sie nicht auf den Datenträger geschrieben. |
| **D** | Gibt an, dass eine Datei temporär ist. Sie wird gelöscht, wenn der letzte Dateizeiger geschlossen wird. |
| **ccs=**_encoding_ | Gibt den codierten Zeichensatz verwenden (eines **UTF-8**, **UTF-16LE**, oder **UNICODE**) für diese Datei. Machen Sie keine Angabe, wenn Sie ANSI-Codierung wünschen. |

Gültige Zeichen für die *Modus* in verwendete Zeichenfolge **Fopen_s** und [_fdopen](fdopen-wfdopen.md) entsprechen *Oflag* verwendeten Argumenten [_ Öffnen Sie](open-wopen.md) und [_sopen](sopen-wsopen.md)wie folgt.

|Zeichen in *Modus* Zeichenfolge|Entsprechende *Oflag* Wert für _open/_sopen|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_APPEND**)|
|**a+**|**_O_RDWR** &#124; **_O_APPEND** (usually **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r+**|**_O_RDWR**|
|**w**|**_O_WRONLY** (usually **_O_WRONLY** &#124; **_O_CREAT** &#124;** _O_TRUNC**)|
|**w+**|**_O_RDWR** (usually **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**c**|Keiner|
|**n**|Keiner|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**CCS = UNICODE**|**_O_WTEXT**|
|**ccs=UTF-8**|**_O_UTF8**|
|**ccs=UTF-16LE**|**_O_UTF16**|

Bei Verwendung von **Rb** Modus müssen nicht den Code und erwarten einen Großteil der Datei zu lesen bzw. nicht besonders wichtig Leistung des Netzwerks sind, im Speicher abgebildete Win32-Dateien möglicherweise auch eine Option.

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).

Die **c**, **n**, und **t** *Modus* Optionen sind Microsoft-Erweiterungen für **Fopen_s** und [_fdopen](fdopen-wfdopen.md) und sollte nicht, wo ANSI-Portabilität gewünscht ist verwendet werden.

## <a name="example"></a>Beispiel

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it is not NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
