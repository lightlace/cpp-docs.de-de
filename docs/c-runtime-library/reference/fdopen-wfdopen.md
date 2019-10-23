---
title: _fdopen, _wfdopen
ms.date: 12/12/2017
api_name:
- _fdopen
- _wfdopen
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
ms.openlocfilehash: 5202c84cd1a9038faf68587f9207d376ed8c0af1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941262"
---
# <a name="_fdopen-_wfdopen"></a>_fdopen, _wfdopen

Verknüpft einen Stream mit einer Datei, die zuvor für E/A auf niedriger Ebene geöffnet war.

## <a name="syntax"></a>Syntax

```C
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

*fd*<br/>
Dateideskriptor der geöffneten Datei.

*mode*<br/>
Der Typ des Dateizugriffs.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf den geöffneten Stream zurück. Ein NULL-Zeigerwert gibt einen Fehler an. Wenn ein Fehler auftritt, wird der ungültige Parameterhandler aufgerufen, so wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, wird **errno** entweder auf **EBADF**festgelegt, was auf einen fehlerhaften Dateideskriptor hinweist, oder auf **EINVAL**, das angibt, dass der *Modus* ein NULL-Zeiger war.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_fdopen** -Funktion ordnet einen e/a-Datenstrom mit der von *FD*identifizierten Datei zu und ermöglicht so, dass eine Datei, die für e/a auf niedriger Ebene geöffnet ist, gepuffert und formatiert wird. **_wfdopen** ist eine breit Zeichen Version von **_fdopen**. Das *Mode* -Argument für **_wfdopen** ist eine Zeichenfolge mit breit Zeichen. **_wfdopen** und **_fdopen** Verhalten sich andernfalls identisch.

An **_fdopen** übertrage Dateideskriptoren sind im Besitz des zurückgegebenen **Datei Daten &#42;** Stroms. Wenn **_fdopen** erfolgreich ist, sollten Sie nicht [ \_close](close.md) für den Dateideskriptor aufzurufen. Wenn Sie [fclose](fclose-fcloseall.md) für die zurückgegebene **Datei &#42;** aufrufen, wird auch der Dateideskriptor geschlossen.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|\_Unicode und \_MBCS sind nicht definiert.|\_Definierte MBCS|\_Unicode definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

Die Zeichenfolge im *Modus* gibt den Typ des Datei Zugriffs an, der für die Datei angefordert wird:

| *mode* | Zugriff |
|--------|--------|
| **"r"** | Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der **fopen** -Befehl fehl. |
| **"w"** | Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a“** | Öffnet zum Schreiben am Ende der Datei (Anhängen). Erstellt die Datei, wenn sie nicht vorhanden ist. |
| **„r+“** | Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein. |
| **„w+“** | Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört. |
| **„a+“** | Öffnet sich zum Lesen und Anfügen. Erstellt die Datei, wenn sie nicht vorhanden ist. |

Wenn eine Datei mit dem Zugriffstyp **"a"** oder **"a +"** geöffnet wird, erfolgen alle Schreibvorgänge am Ende der Datei. Der Dateizeiger kann mithilfe von [fseek](fseek-fseeki64.md) oder [Rewind](rewind.md)neu positioniert werden. er wird jedoch immer wieder zurück an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden. Wenn der Zugriffstyp **"r +"** , **"w +"** oder **"a +** " angegeben wird, sind sowohl Lese-als auch Schreibvorgänge zulässig (die Datei ist zum Aktualisieren geöffnet). Wenn Sie jedoch zwischen lesen und schreiben wechseln, muss ein dazwischenliegende [fflush](fflush.md)-, [fsetpos](fsetpos.md)-, [fseek](fseek-fseeki64.md)-oder [Rewind](rewind.md) -Vorgang vorhanden sein. Wenn Sie möchten, können Sie die aktuelle Position für den [fsetpos](fsetpos.md) -oder [fseek](fseek-fseeki64.md) -Vorgang angeben.

Zusätzlich zu den obigen Werten können die folgenden Zeichen auch im- *Modus* enthalten sein, um den Übersetzungsmodus für Zeilen Umleitungs Zeichen anzugeben:

| *modus*modifizierer | Verhalten |
|-----------------|----------|
| **t** | Öffnen im Textmodus (übersetzt). Im Textmodus werden Wagenrücklauf-/Zeilenvorschub-Kombinationen (CR-LF) bei der Eingabe in einzelne Zeilenvorschübe (LF) übersetzt. LF-Zeichen werden bei der Ausgabe in CR-LF-Kombinationen übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. |
| **b** | Wird im binären (nicht übersetzten) Modus geöffnet. Alle Übersetzungen aus dem **t** -Modus werden unterdrückt. |
| **c** | Aktivieren Sie das commitflag für den zugeordneten *Dateinamen* , damit der Inhalt des Datei Puffers direkt auf den Datenträger geschrieben wird, wenn **fflush** oder **_flushall** aufgerufen wird. |
| **n** | Setzen Sie das commitflag für den zugeordneten *Dateinamen* auf "No-Commit" zurück. Dies ist die Standardeinstellung. Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit „Commode.obj“ verknüpfen. Der Standardwert des globalen Commitflags lautet „no-commit“, es sei denn, Sie verknüpfen das Programm explizit mit „Commode.obj“. |

Die *Optionen "* **t**", " **c**" und " **n** " sind **Microsoft-Erweiterungen** für " **_fdopen**". Verwenden Sie sie nicht, wenn Sie die ANSI-Portabilität beibehalten möchten.

Wenn " **t** " oder " **b** " im *Modus*nicht angegeben wird, wird der Standard Übersetzungsmodus durch die globale Variable [ \_"f Mode](../../c-runtime-library/fmode.md)" definiert. Wenn **t** oder **b** dem Argument vorangestellt wird, schlägt die Funktion fehl und gibt NULL zurück. Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Gültige Zeichen für die in **fopen** und **_fdopen** verwendete *modus*zeichenfolge entsprechen *Oflag* -Argumenten, die in [ \_Open](open-wopen.md) und [ \_sopen](sopen-wsopen.md)verwendet werden, wie in dieser Tabelle dargestellt:

|Zeichen in der *Mode* -Zeichenfolge|Entsprechender *Oflag* -Wert für **_open** und **_sopen**|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_ wronly &#124; \_oAppend\_(normalerweise o wronly o** **\_ &#124; \_\_\_ &#124; \_\_ Anfügen**)|
|**a+**|**\_&#124; O\_ rdwr\_o\_Append** (Normal **\_erweiseo\_rdwr &#124; \_ &#124; o Append\_oup\_\_** )|
|**r**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**w**|**\_O\_wronly** ( **\_ &#124; \_\_i.d. a. &#124; " \_ owronly\_o" o trunc)\_**|
|**w +**|**\_O\_rdwr** **\_ &#124; \_ &#124; \_\_(i. d. r. o\_rdwr o up o trunc)\_**|
|**b**|**\_O\_-BINÄRDATEI**|
|**t**|**\_O\_TEXT**|
|**c**|None|
|**n**|None|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> oder \<wchar.h>|

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

### <a name="input-crt_fdopentxt"></a>Eingabe: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>Ausgabe

```Output
Lines in file: 2
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[\_DUP, \_dup2](dup-dup2.md)<br/>
["f" \_, "vollständig"](fclose-fcloseall.md)<br/>
["Open" \_, "WF"](fopen-wfopen.md)<br/>
[freopen, \_wfreopen](freopen-wfreopen.md)<br/>
[\_Öffnen, \_Wopen](open-wopen.md)<br/>
