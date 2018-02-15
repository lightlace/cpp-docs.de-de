---
title: _fdopen, _wfdopen | Microsoft-Dokumentation
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fdopen
- _wfdopen
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
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2474c25d30415d48252a2621ae5f7e69e5fed4d3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen

Verknüpft einen Stream mit einer Datei, die zuvor für E/A auf niedriger Ebene geöffnet war.

## <a name="syntax"></a>Syntax

```c
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>Parameter

*fd*  
Dateideskriptor der geöffneten Datei.

*mode*  
Der Typ des Dateizugriffs.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf den geöffneten Stream zurück. Ein NULL-Zeigerwert gibt einen Fehler an. Wenn ein Fehler auftritt, wird der ungültige Parameterhandler aufgerufen, so wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn Sie Ausführung weiterhin ausgeführt werden darf, wird `errno` entweder auf `EBADF`, was auf einen fehlerhaften Dateideskriptor hinweist, oder auf `EINVAL` festgelegt, was darauf hinweist, dass `mode` ein NULL-Zeiger war.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die `_fdopen` Funktion ordnet einen e/a-Stream mit der Datei, die identifizierte *fd*, und auf diese Weise eine Datei, die geöffnet wird, für die Low-Level-e/a, gepuffert und formatiert werden. `_wfdopen` ist eine Breitzeichen-Version von `_fdopen`; das *Modus* Argument `_wfdopen` ist eine Breitzeichen-Zeichenfolge. Andernfalls verhalten sich `_wfdopen` und `_fdopen` identisch.

Dateideskriptoren übergebenen `_fdopen` gehören durch das zurückgegebene `FILE *` Stream. Wenn `_fdopen` erfolgreich ist, rufen Sie nicht [ \_schließen](../../c-runtime-library/reference/close.md) auf den Dateideskriptor. Aufrufen von [Fclose](../../c-runtime-library/reference/fclose-fcloseall.md) für das zurückgegebene `FILE *` schließt auch den Dateideskriptor.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tfdopen`|`_fdopen`|`_fdopen`|`_wfdopen`|

Die *Modus* Zeichenfolge gibt den Typ des Dateizugriffs, die für die Datei angefordert:  

`"r"`  
Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `fopen` -Aufruf fehl.

`"w"`  
Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.

`"a"`  
Wird zum Schreiben geöffnet; am Ende der Datei (anfügen). Erstellt die Datei, wenn sie nicht vorhanden ist.

`"r+"`  
Öffnet sowohl zum Lesen als auch zum Schreiben. (Die Datei muss vorhanden sein.)

`"w+"`  
Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.

`"a+"`  
Öffnet sich zum Lesen und Anfügen. Erstellt die Datei, wenn sie nicht vorhanden ist.

Bei einer mit dem Zugriffstyp `"a"` oder `"a+"` geöffneten Datei erfolgen alle Schreibvorgänge am Ende der Datei. Der Dateizeiger kann mit `fseek` oder `rewind` neu angeordnet werden, er wird jedoch immer wieder zurück an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden. Wenn als Zugriffstyp `"r+"`, `"w+"` oder `"a+"` angegeben wird, sind sowohl Lese- als auch Schreibvorgänge zulässig (die Datei ist zum Aktualisieren geöffnet). Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie `fflush`, `fsetpos`, `fseek` oder `rewind` vorhanden sein. Sie können bei Bedarf die aktuelle Position für den `fsetpos`- oder `fseek`-Vorgang angeben.

Zusätzlich zu den oben aufgeführten Werten kann die folgenden Zeichen enthalten sein *Modus* um den Übersetzungsmodus für Zeilenumbruchzeichen anzugeben:

`t`  
Öffnen im Textmodus (übersetzt). Im Textmodus werden Wagenrücklauf-/Zeilenvorschub-Kombinationen (CR-LF) bei der Eingabe in einzelne Zeilenvorschübe (LF) übersetzt. LF-Zeichen werden bei der Ausgabe in CR-LF-Kombinationen übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In den Dateien, die für das Lesen/Schreiben geöffnet sind, überprüft `fopen` die Datei auf STRG+Z am Dateiende, und entfernt sofern möglich die Markierung. Dies geschieht, da die Verwendung von `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit STRG+Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht ordnungsgemäß verhält.

`b`  
Wird im binären (nicht übersetzten) Modus geöffnet. Übersetzungen aus dem `t`-Modus werden unterdrückt.

`c`  
Aktivieren Sie das Commitflag für den zugeordneten Parameter `filename` , sodass der Inhalt des Dateipuffers direkt auf einen Datenträger geschrieben wird, wenn `fflush` oder `_flushall` aufgerufen wird.

`n`  
Setzen Sie das Commitflag für den zugeordneten Parameter `filename` auf "no-commit" zurück. Dies ist die Standardeinstellung. Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit „Commode.obj“ verknüpfen. Der Standardwert des globalen Commitflags lautet „no-commit“, es sei denn, Sie verknüpfen das Programm explizit mit „Commode.obj“.

Die `t`, `c`, und `n` *Modus* Optionen sind Microsoft-Erweiterungen für `fopen` und `_fdopen`. Verwenden Sie sie nicht, wenn Sie die ANSI-Portabilität beibehalten möchten.

Wenn `t` oder `b` nicht Situation, in der *Modus*, wird der standardübersetzungsmodus durch die globale Variable definiert [ \_Fmode](../../c-runtime-library/fmode.md). Wenn `t` oder `b` wird das Argument, schlägt die Funktion vorangestellt und gibt NULL zurück. Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Gültige Zeichen für die *Modus* Zeichenfolge im `fopen` und `_fdopen` entsprechen *Oflag* in verwendeten Argumente [ \_öffnen](../../c-runtime-library/reference/open-wopen.md) und [ \_Sopen](../../c-runtime-library/reference/sopen-wsopen.md), wie in dieser Tabelle dargestellt:

|Zeichen in *Modus* Zeichenfolge|Entsprechende *Oflag* Wert für `_open` und `_sopen`|
|---------------------------------|---------------------------------------------------|
|`a`|**\_O\_WRONLY &#124; \_O\_APPEND** (in der Regel  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_APPEND**)|
|`a+`|**\_O\_RDWR &#124; \_O\_APPEND** (usually **\_O\_RDWR &#124; \_O\_APPEND &#124; \_O\_CREAT** )|
|`r`|**\_O\_RDONLY**|
|`r+`|**\_O\_RDWR**|
|`w`|**\_O\_WRONLY** (in der Regel  **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|`w+`|**\_O\_RDWR** (in der Regel  **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|`b`|**\_O\_BINARY**|
|`t`|**\_O\_TEXT**|
|`c`|Keiner|
|`n`|Keiner|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|`_fdopen`|\<stdio.h>|
|`_wfdopen`|\<stdio.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crtfdopentxt"></a>Eingabe: crt_fdopen.txt

```
Line one
Line two
```

### <a name="output"></a>Ausgabe

```
Lines in file: 2
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)   
[\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
[fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
[Fopen, \_Wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
[freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
[\_Öffnen von \_Wopen](../../c-runtime-library/reference/open-wopen.md)
