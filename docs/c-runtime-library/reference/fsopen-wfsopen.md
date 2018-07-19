---
title: _fsopen, _wfsopen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wfsopen
- _fsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce69c6789ba65f61c54957dde3dfa6965bc32e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405152"
---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen

Ein Stream mit Dateifreigabe öffnen

## <a name="syntax"></a>Syntax

```C
FILE *_fsopen(
   const char *filename,
   const char *mode,
   int shflag
);
FILE *_wfsopen(
   const wchar_t *filename,
   const wchar_t *mode,
   int shflag
);
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Name der zu öffnenden Datei.

*mode*<br/>
Zugriffstyp zulässig.

*shflag*<br/>
Freigabetyp erlaubt.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger auf den Stream zurück. Ein NULL-Zeigerwert gibt einen Fehler an. Wenn *Filename* oder *Modus* ist **NULL** oder eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter an, wie in beschrieben [Parametervalidierung ](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, geben diese Funktionen zurück **NULL** und **Errno** auf **EINVAL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Die **_fsopen** -Funktion öffnet die Datei, die vom angegebenen *Filename* als Datenstrom und die Datei für nachfolgende Lese- oder Schreibfreigabe, vorbereitet werden, gemäß den Modus und *Shflag*Argumente. **_wfsopen** ist eine Breitzeichen-Version von **_fsopen**; das *Filename* und *Modus* Argumente **_wfsopen** sind Breitzeichen-Zeichenfolgen. **_wfsopen** und **_fsopen** Verhalten sich andernfalls identisch.

Die Zeichenfolge *Modus* gibt den Typ des Zugriffs für die Datei angefordert wird, wie in der folgenden Tabelle gezeigt.

|Begriff|Definition|
|----------|----------------|
|**"r"**|Öffnet zum Lesen. Wenn die Datei nicht vorhanden oder kann nicht gefunden werden, die **_fsopen** -Aufruf fehl.|
|**"w"**|Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.|
|**„a“**|Öffnet zum Schreiben am Ende der Datei (Anfügen); erstellt die Datei zuerst, wenn sie nicht vorhanden ist.|
|**„r+“**|Öffnet sowohl zum Lesen als auch zum Schreiben. (Die Datei muss vorhanden sein.)|
|**„w+“**|Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.|
|**„a+“**|Öffnet zum Lesen und Anhängen; erstellt die Datei zuerst, wenn sie nicht vorhanden ist.|

Verwenden der **"w"** und **"w +"** Typen mit Vorsicht zu verwenden, da sie vorhandene Dateien zerstören können.

Wenn eine Datei geöffnet wird, mit der **"a"** oder **"a +"** Zugriffstyp, am Ende der Datei erfolgen alle Schreibvorgänge. Der Dateizeiger kann mit neu angeordnet werden [Fseek](fseek-fseeki64.md) oder [zurückspulen](rewind.md), er wird jedoch immer verschoben zurück an das Ende der Datei, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden. Wenn die **"R +"**, **"w +"**, oder **"a +"** Zugriff angegeben wird, sind sowohl Lese-als auch Schreibvorgänge zulässig (die Datei ist dann zum Aktualisieren geöffnet). Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) oder [rewind](rewind.md) vorhanden sein. Die aktuelle Position kann angegeben werden, für die [Fsetpos](fsetpos.md) oder [Fseek](fseek-fseeki64.md) Vorgang, falls gewünscht. Zusätzlich zu den oben aufgeführten Werten kann eines der folgenden Zeichen kann einzuschließenden *Modus* um den Übersetzungsmodus für neue Zeilen und für dateiverwaltung anzugeben.

|Begriff|Definition|
|----------|----------------|
|**t**|Öffnet eine Datei im Textmodus (übersetzt). Klicken Sie in diesem Modus Carriage Return Line feed (CR-LF) Kombinationen bei der Eingabe in einzelne Zeilenvorschübe (LF) übersetzt, und bei Ausgabe in CR-LF-Kombinationen aus LF-Zeichen übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In den Dateien geöffnet zum Lesen oder Lesen/Schreiben **_fsopen** STRG + Z am Ende der Datei gesucht und entfernt, sofern möglich die Markierung. Dies geschieht, da mit [Fseek](fseek-fseeki64.md) und [Ftell](ftell-ftelli64.md) zum Navigieren innerhalb einer Datei, die mit STRG + Z endet verursachen können [Fseek](fseek-fseeki64.md) gegen Ende der Datei nicht ordnungsgemäß verhält.|
|**b**|Öffnet im (unübersetzten) Binärmodus eine Datei; die oben genannten Übersetzungen werden unterdrückt.|
|**S**|Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.|
|**R**|Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.|
|**T**|Gibt an, dass eine Datei temporär ist. Wenn möglich, wird sie nicht auf den Datenträger geschrieben.|
|**D**|Gibt an, dass eine Datei temporär ist. Sie wird gelöscht, wenn der letzte Dateizeiger geschlossen wird.|

Wenn **t** oder **b** nicht in *mode* angegeben ist, wird der Übersetzungsmodus durch die Standardmodusvariable **_fmode** definiert. Wenn **t** oder **b** vorangestellt wird das Argument, die Funktion fehl und gibt **NULL**. Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Das Argument *Shflag* ist ein konstanter Ausdruck, der aus einer der folgenden Manifestkonstanten besteht, die in Share.h definiert.

|Begriff|Definition|
|----------|----------------|
|**_SH_COMPAT**|Legt den Kompatibilitätsmodus für 16-Bit-Anwendungen fest.|
|**_SH_DENYNO**|Gestattet Lese- und Schreibzugriff.|
|**_SH_DENYRD**|Verweigert den Lesezugriff auf die Datei.|
|**_SH_DENYRW**|Verweigert den Lese- und Schreibzugriff auf die Datei.|
|**_SH_DENYWR**|Verweigert den Lesezugriff auf die Datei.|

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|Optionale Header|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h>|\<share.h><br /><br /> Für die manifestkonstante für *Shflag* Parameter.|
|**_wfsopen**|\<stdio.h> oder \<wchar.h>|\<share.h><br /><br /> Für die manifestkonstante für *Shflag* Parameter.|

## <a name="example"></a>Beispiel

```C
// crt_fsopen.c

#include <stdio.h>
#include <stdlib.h>
#include <share.h>

int main( void )
{
   FILE *stream;

   // Open output file for writing. Using _fsopen allows us to
   // ensure that no one else writes to the file while we are
   // writing to it.
    //
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )
   {
      fprintf( stream, "No one else in the network can write "
                       "to this file until we are done.\n" );
      fclose( stream );
   }
   // Now others can write to the file while we read it.
   system( "type outfile" );
}
```

```Output
No one else in the network can write to this file until we are done.
```

## <a name="see-also"></a>Siehe auch

[Stream-E/A](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
