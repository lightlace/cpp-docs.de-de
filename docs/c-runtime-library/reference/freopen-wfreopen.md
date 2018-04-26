---
title: freopen, _wfreopen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
dev_langs:
- C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e371076ce095116930908174d4fa29e9cfd876e5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen

Weist einen Dateizeiger neu zu. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

## <a name="syntax"></a>Syntax

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>Parameter

*path*<br/>
Pfad der neuen Datei.

*mode*<br/>
Zugriffstyp zulässig.

*Stream*<br/>
Zeiger auf die **FILE**-Struktur.

## <a name="return-value"></a>Rückgabewert

Jede dieser Funktionen gibt einen Zeiger an die gerade geöffnete Datei zurück. Wenn ein Fehler auftritt, die ursprüngliche Datei geschlossen wird und die Funktion gibt eine **NULL** Zeigerwert. Wenn *Pfad*, *Modus*, oder *Stream* ein null-Zeiger ist oder wenn *Filename* ist eine leere Zeichenfolge, rufen diese Funktionen den ungültigen Parameter Handler, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** auf **EINVAL** inventurüberprüfung **NULL**.

Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Hinweise

Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

Die **Freopen** -Funktion schließt die derzeit zugeordnete Datei *Stream* und weist *Stream* in die Datei, die vom angegebenen *Pfad*. **_wfreopen** ist eine Breitzeichen-Version von **_freopen**; das *Pfad* und *Modus* Argumente **_wfreopen** sind Breitzeichen-Zeichenfolgen. **_wfreopen** und **_freopen** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**Freopen** dient normalerweise zum Umleiten der bereits geöffneten Dateien **Stdin**, **"stdout"**, und **"stderr"** auf Dateien, die vom Benutzer angegeben wird. Die neue Datei zugeordneten *Stream* wird geöffnet, mit *Modus*, was ist eine Zeichenfolge, die den Typ des Zugriffs für die Datei angefordert wird wie folgt angeben:

|*mode*|Zugriff|
|-|-|
**"r"**|Öffnet zum Lesen. Wenn die Datei nicht vorhanden oder kann nicht gefunden werden, die **Freopen** -Aufruf fehl.
**"w"**|Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.
**„a“**|Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei (Anfügen) geöffnet, ohne die EOF-Markierung (end-of-file, Dateiende) zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist.
**„r+“**|Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein.
**„w+“**|Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört.
**„a+“**|Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen der EOF-Markierung, bevor neue Daten in die Datei geschrieben werden. Die EOF-Markierung wird nach Abschluss des Schreibvorgangs nicht wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist.

Verwenden der **"w"** und **"w +"** Typen mit Vorsicht zu verwenden, da sie vorhandene Dateien zerstören können.

Wenn eine Datei geöffnet wird, mit der **"a"** oder **"a +"** Zugriffstyp, alle Schreibvorgänge am Ende der Datei erfolgen. Obwohl der Dateizeiger werden können mithilfe von [Fseek](fseek-fseeki64.md) oder [zurückspulen](rewind.md), der Dateizeiger wird bis zum Ende der Datei immer umgelagert, bevor ein Schreibvorgang durchgeführt wird. Folglich können vorhandene Daten nicht überschrieben werden.

Die **"a"** Modus wird nicht die EOF-Markierung entfernt, bevor Daten an die Datei angefügt. Nach dem Anfügen werden durch den MS-DOS-Befehl TYPE nur Daten bis zur ursprünglichen EOF-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Die **"a +"** Modus wird die EOF-Markierung entfernt, bevor Daten an die Datei angefügt. Nach dem Anhängen werden mit dem Befehl MS-DOS TYPE alle Daten in der Datei angezeigt. Die **"a +"** Modus ist erforderlich, damit das Anfügen an eine streamdatei, die mit STRG + Z EOF-Markierung beendet wird.

Wenn die **"R +"**, **"w +"**, oder **"a +"** Zugriff angegeben wird, sind sowohl Lese-als auch Schreibvorgänge zulässig (die Datei ist dann für "Update" geöffnet sein). Wenn Sie jedoch zwischen Lese- und Schreibvorgängen wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md) oder [rewind](rewind.md) vorhanden sein. Die aktuelle Position kann angegeben werden, für die [Fsetpos](fsetpos.md) oder [Fseek](fseek-fseeki64.md) Vorgang, falls gewünscht. Zusätzlich zu den oben angegebenen Werten kann eines der folgenden Zeichen enthalten der *Modus* Zeichenfolge, die den Übersetzungsmodus für neue Zeilen anzugeben.

|*Modus* Modifizierer|Übersetzungsmodus|
|-|-|
**t**|Öffnen im Textmodus (übersetzt).
**b**|Öffnen im binären (unübersetzten) Modus; Übersetzungen von Wagenrücklauf- und Zeilenvorschubzeichen werden unterdrückt.

Im Textmodus (übersetzt) werden die Carriage Return-Zeilenvorschub (CR-LF) Kombinationen in einzelne Zeilenvorschubszeichen (LF) Zeichen bei Eingabe übersetzt; LF-Zeichen werden bei der Ausgabe in CR-LF-Kombinationen aus übersetzt. Außerdem wird STRG+Z bei der Eingabe als EOF-Zeichen interpretiert. In Dateien geöffnet zum Lesen oder für Lese- und Schreibvorgänge mit **"a +"**, die Laufzeitbibliothek STRG + Z am Ende der Datei gesucht und entfernt, sofern möglich die Markierung. Dies geschieht, da mit [Fseek](fseek-fseeki64.md) und [Ftell](ftell-ftelli64.md) zum Navigieren innerhalb einer Datei verursachen [Fseek](fseek-fseeki64.md) gegen Ende der Datei nicht ordnungsgemäß verhält. Die **t** -Option ist eine Microsoft-Erweiterung, die nicht verwendet werden soll, wo ANSI-Portabilität gewünscht wird.

Wenn **t** oder **b** nicht Situation, in der *Modus*, wird der standardübersetzungsmodus durch die globale Variable definiert [_fmode](../../c-runtime-library/fmode.md). Wenn **t** oder **b** vorangestellt wird das Argument, die Funktion fehl und gibt **NULL**.

Eine Erörterung von Text- und Binärmodi finden Sie unter [Text- und Binärmodus-Datei-E/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Anforderungen

|Funktion|Erforderlicher Header|
|--------------|---------------------|
|**freopen**|\<stdio.h>|
|**_wfreopen**|\<stdio.h> oder \<wchar.h>|

Die Konsole wird in apps der universellen Windows-Plattform (UWP) nicht unterstützt. Standardstream Handles, die mit der Konsole verknüpften sind **Stdin**, **"stdout"**, und **"stderr"**, müssen umgeleitet werden, bevor sie C-Laufzeitfunktionen in uwp-apps verwenden können . Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
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
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
