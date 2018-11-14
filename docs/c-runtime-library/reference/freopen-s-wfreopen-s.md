---
title: freopen_s, _wfreopen_s
ms.date: 11/04/2016
apiname:
- _wfreopen_s
- freopen_s
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
- freopen_s
- _tfreopen_s
- _wfreopen_s
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
ms.openlocfilehash: 2cdc16f21882c32933868000c6fd1d66accc74b8
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326511"
---
# <a name="freopens-wfreopens"></a>freopen_s, _wfreopen_s

Weist einen Dateizeiger neu zu. Diese Versionen von [freopen, _wfreopen](freopen-wfreopen.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.

## <a name="syntax"></a>Syntax

```C
errno_t freopen(
   FILE** pFile,
   const char *path,
   const char *mode,
   FILE *stream
);
errno_t _wfreopen(
   FILE** pFile,
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*pFile-Datei*<br/>
Ein Zeiger auf den vom Aufruf bereitzustellenden Dateizeiger.

*path*<br/>
Pfad der neuen Datei.

*mode*<br/>
Zugriffstyp zulässig.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Fehlercode zurück. Wenn ein Fehler auftritt, wird die ursprüngliche Datei geschlossen.

## <a name="remarks"></a>Hinweise

Die **Freopen_s** -Funktion schließt die derzeit zugeordnete Datei *Stream* und weist *Stream* auf die angegebene Datei *Pfad* . **_wfreopen_s** ist eine Breitzeichen-Version von **_freopen_s**; die *Pfad* und *Modus* Argumente **_wfreopen_s** sind Zeichenfolgen mit Breitzeichen. **_wfreopen_s** und **_freopen_s** Verhalten sich andernfalls identisch.

Wenn eine der *pFile*, *Pfad*, *Modus*, oder *Stream* sind **NULL**, oder wenn *Pfad* ist eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter aus, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und zurückgeben **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**Freopen_s** wird normalerweise verwendet, um die bereits geöffneten Dateien umzuleiten **Stdin**, **"stdout"**, und **"stderr"** auf Dateien, die vom Benutzer angegeben wird. Die neue Datei mit dem zugeordneten *Stream* wird geöffnet, mit *Modus*, ist eine Zeichenfolge, die den Typ des angeforderten Zugriffstyp für die Datei wie folgt angibt:

|*mode*|Zugriff|
|-|-|
| **"r"** | Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder wurde nicht gefunden, die **Freopen_s** -Aufruf fehl. |
| **"w"** | Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a“** | Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei (Anfügen) geöffnet, ohne die EOF-Markierung (end-of-file, Dateiende) zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist. |
| **„r+“** | Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein. |
| **„w+“** | Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a+“** | Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen der EOF-Markierung, bevor neue Daten in die Datei geschrieben werden. Die EOF-Markierung wird nach Abschluss des Schreibvorgangs nicht wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist. |

Verwenden der **"w"** und **"w +"** Typen mit Bedacht, da sie vorhandene Dateien zerstören können.

Wenn eine Datei geöffnet wird, mit der **"a"** oder **"a +"** Zugriffstyp alle Schreibvorgänge erfolgen am Ende der Datei. Obwohl der Dateizeiger positioniert werden kann, mit [Fseek](fseek-fseeki64.md) oder [rewind](rewind.md), der Dateizeiger wird immer wieder zurück verschoben an das Ende der Datei, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden.

Die **"a"** Modus wird nicht die EOF-Markierung entfernt, bevor die Daten an die Datei angefügt. Nach dem Anfügen werden durch den MS-DOS-Befehl TYPE nur Daten bis zur ursprünglichen EOF-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Die **"a +"** Modus wird die EOF-Markierung entfernt, bevor Daten an die Datei angefügt. Nach dem Anhängen werden mit dem Befehl MS-DOS TYPE alle Daten in der Datei angezeigt. Die **"a +"** Modus ist erforderlich, zum Anfügen an eine streamdatei, die mit der STRG + Z EOF-Markierung beendet wird.

Wenn die **"R +"**, **"w +"**, oder **"a +"** angegeben wird, sind Lese- und Schreibvorgänge zulässig (die Datei gilt als für "Update" geöffnet). Wenn Sie jedoch zwischen Lese- und Schreibvorgängen wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) oder [rewind](rewind.md) vorhanden sein. Die aktuelle Position kann angegeben werden, für die [Fsetpos](fsetpos.md) oder [Fseek](fseek-fseeki64.md) Vorgang, bei Bedarf. Zusätzlich zu den oben aufgeführten Werten kann eines der folgenden Zeichen im enthalten sein kann die *Modus* Zeichenfolge, die den Übersetzungsmodus für neue Zeilen anzugeben.

|*Modus* Modifizierer|Commit-Modus|
|-|-|
| **t** | Öffnen im Textmodus (übersetzt). |
| **b** | Öffnen im binären (unübersetzten) Modus; Übersetzungen von Wagenrücklauf- und Zeilenvorschubzeichen werden unterdrückt. |

Im Textmodus (übersetzt) werden die Carriage Return-Zeilenvorschub (CR-LF) Kombinationen in Zeilenvorschubzeichen (LF) bei Eingabe übersetzt; LF-Zeichen werden bei der Ausgabe in CR-LF-Kombinationen aus übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In Dateien, die zum Lesen oder geöffnet werden, für Lese- und Schreibvorgänge mit **"a +"**, die Laufzeitbibliothek STRG + Z am Ende der Datei gesucht und entfernt, wenn möglich die Markierung. Dies geschieht, da mit [Fseek](fseek-fseeki64.md) und [Ftell](ftell-ftelli64.md) zum Navigieren innerhalb einer Datei verursachen [Fseek](fseek-fseeki64.md) am Ende der Datei nicht ordnungsgemäß verhält. Die **t** Option ist eine Microsoft-Erweiterung, die nicht verwendet werden soll, wo ANSI-Portabilität gewünscht wird.

Wenn **t** oder **b** nicht erhält, *Modus*, wird der standardübersetzungsmodus durch die globale Variable definiert [_fmode](../../c-runtime-library/fmode.md). Wenn **t** oder **b** ist das Argument, die Funktion schlägt fehl und gibt mit dem Präfix **NULL**.

Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**freopen_s**|\<stdio.h>|
|**_wfreopen_s**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps für universelle Windows-Plattform (UWP) nicht unterstützt. Standardstreamhandles, die mit der Konsole verknüpft sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in UWP-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_freopen_s.c
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   errno_t err;
   // Reassign "stderr" to "freopen.out":
   err = freopen_s( &stream, "freopen.out", "w", stderr );

   if( err != 0 )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
