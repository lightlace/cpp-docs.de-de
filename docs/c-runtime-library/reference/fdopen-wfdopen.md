---
title: "_fdopen, _wfdopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fdopen"
  - "_wfdopen"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tfdopen"
  - "_fdopen"
  - "_wfdopen"
  - "wfdopen"
  - "tfdopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fdopen-Funktion"
  - "_tfdopen-Funktion"
  - "_wfdopen-Funktion"
  - "fdopen-Funktion"
  - "Streams, Zuordnen mit Dateien"
  - "tfdopen-Funktion"
  - "wfdopen-Funktion"
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _fdopen, _wfdopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verknüpft einen Stream mit einer Datei, die zuvor für E\/A auf niedriger Ebene geöffnet war.  
  
## Syntax  
  
```  
FILE *_fdopen(    
   int fd,  
   const char *mode   
);  
FILE *_wfdopen(   
   int fd,  
   const wchar_t *mode   
);  
```  
  
#### Parameter  
 `fd`  
 Dateideskriptor der geöffneten Datei.  
  
 `mode`  
 Der Typ des Dateizugriffs.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf den geöffneten Stream zurück.  Ein NULL\-Zeigerwert gibt einen Fehler an.  Wenn ein Fehler auftritt, wird der ungültige Parameterhandler aufgerufen, so wie dies unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  Wenn Sie Ausführung weiterhin ausgeführt werden darf, wird `errno` entweder auf `EBADF`, was auf einen fehlerhaften Dateideskriptor hinweist, oder auf `EINVAL` festgelegt, was darauf hinweist, dass `mode` ein NULL\-Zeiger war.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die Funktion `_fdopen` verknüpft einen E\/A\-Stream mit der durch `fd` ermittelten Datei. Dadurch wird der für E\/A auf niedriger Ebene geöffneten Datei ermöglicht, gepuffert und formatiert zu werden.  `_wfdopen` ist eine Breitzeichenversion von `_fdopen`. Das `mode`\-Argument für `_wfdopen` ist eine Breitzeichenfolge.  Andernfalls verhalten sich `_wfdopen` und `_fdopen` identisch.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tfdopen`|`_fdopen`|`_fdopen`|`_wfdopen`|  
  
 Die `mode`\-Zeichenzeichenfolge gibt den Typ der Datei und den Dateizugriff an.  
  
 Die Zeichenfolge `mode` gibt den Typ des Zugriffs, der für die Datei angefordert wird, wie in der folgenden Tabelle gezeigt, an.  
  
 `"r"`  
 Öffnet zum Lesen.  Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `fopen`\-Aufruf fehl.  
  
 `"w"`  
 Öffnet eine leere Datei zum Schreiben.  Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a"`  
 Wird zum Schreiben geöffnet; am Ende der Datei \(anfügen\).  Erstellt die Datei, wenn sie nicht vorhanden ist.  
  
 `"r+"`  
 Öffnet sowohl zum Lesen als auch zum Schreiben.  \(Die Datei muss vorhanden sein.\)  
  
 `"w+"`  
 Öffnet eine leere Datei zum Lesen und Schreiben.  Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a+"`  
 Öffnet sich zum Lesen und Anfügen.  Erstellt die Datei, wenn sie nicht vorhanden ist.  
  
 Bei einer mit dem Zugriffstyp `"a"` oder `"a+"` geöffneten Datei erfolgen alle Schreibvorgänge am Ende der Datei.  Der Dateizeiger kann mit `fseek` oder `rewind` neu angeordnet werden, er wird jedoch immer wieder zurück an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird.  Folglich können vorhandene Daten nicht überschrieben werden.  Wenn als Zugriffstyp `"r+"`, `"w+"` oder `"a+"` angegeben wird, sind sowohl Lese\- als auch Schreibvorgänge zulässig \(die Datei ist zum Aktualisieren geöffnet\).  Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie `fflush`, `fsetpos`, `fseek` oder `rewind` vorhanden sein.  Sie können bei Bedarf die aktuelle Position für den `fsetpos`\- oder `fseek`\-Vorgang angeben.  
  
 Neben den obigen Werten können die folgenden Zeichen in `mode` enthalten sein, um den Übersetzungsmodus für Zeilenumbruchzeichen anzugeben.  
  
 `t`  
 Öffnen im Textmodus \(übersetzt\).  Im Textmodus werden Wagenrücklauf\-\/Zeilenvorschub\-Kombinationen \(CR\-LF\) bei der Eingabe in einzelne Zeilenvorschübe \(LF\) übersetzt. LF\-Zeichen werden bei der Ausgabe in CR\-LF\-Kombinationen übersetzt.  Außerdem wird STRG\+Z bei der Eingabe als EOF\-Zeichen interpretiert.  In den Dateien, die für das Lesen\/Schreiben geöffnet sind, überprüft `fopen` die Datei auf STRG\+Z am Dateiende, und entfernt sofern möglich die Markierung.  Dies geschieht, da die Verwendung von `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit STRG\+Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht ordnungsgemäß verhält.  
  
 `b`  
 Wird im binären \(nicht übersetzten\) Modus geöffnet.  Übersetzungen aus dem `t`\-Modus werden unterdrückt.  
  
 `c`  
 Aktivieren Sie das Commitflag für den zugeordneten Parameter `filename`, sodass der Inhalt des Dateipuffers direkt auf einen Datenträger geschrieben wird, wenn `fflush` oder `_flushall` aufgerufen wird.  
  
 `n`  
 Setzen Sie das Commitflag für den zugeordneten Parameter `filename` auf "no\-commit" zurück. Dies ist die Standardeinstellung.  Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit „Commode.obj“ verknüpfen.  Der Standardwert des globalen Commitflags lautet „no\-commit“, es sei denn, Sie verknüpfen das Programm explizit mit „Commode.obj“.  
  
 Bei den Optionen `t`, `c` und `n` `mode` handelt es sich um Microsoft\-Erweiterungen für `fopen` und `_fdopen`.  Verwenden Sie sie nicht, wenn Sie die ANSI\-Portabilität beibehalten möchten.  
  
 Wenn `t` oder `b` nicht in `mode` angegeben ist, wird der Standardübersetzungsmodus durch die globale Variable [\_fmode](../../c-runtime-library/fmode.md) definiert.  Wenn dem Argument `t` oder `b` vorangestellt wird, schlägt die Funktion fehl und gibt `NULL` zurück.  Eine Erörterung von Text\- und Binärmodi finden Sie unter [Text\- und Binärmodus\-Datei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 Gültige Zeichen für die `mode`\-Zeichenfolge, die in `fopen` und `_fdopen` verwendet wird, entsprechen `oflag`\-Argumenten, die in [\_open](../../c-runtime-library/reference/open-wopen.md) und [\_sopen](../../c-runtime-library/reference/sopen-wsopen.md) verwendet werden \(siehe unten\).  
  
|Zeichen in der `mode`\-Zeichenfolge|Der entsprechende `oflag`\-Wert für `_open`\/`_sopen`|  
|-----------------------------------------|-----------------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` \(meistens `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`\)|  
|`a+`|`_O_RDWR &#124; _O_APPEND`  \(meistens `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` \)|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` \(meistens `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`\)|  
|`w+`|`_O_RDWR` \(meistens `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`\)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Keine|  
|`n`|Keine|  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`_fdopen`|\<stdio.h\>|  
|`_wfdopen`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
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
  
## Eingabe: crt\_fdopen.txt  
  
```  
Line one  
Line two  
```  
  
### Ausgabe  
  
```  
Lines in file: 2  
```  
  
## .NET Framework-Entsprechung  
 <xref:System.IO.FileStream.#ctor*>  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)