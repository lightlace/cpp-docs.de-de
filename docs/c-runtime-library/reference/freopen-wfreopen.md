---
title: "freopen, _wfreopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "freopen"
  - "_wfreopen"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wfreopen"
  - "_tfreopen"
  - "freopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tfreopen-Funktion"
  - "_wfreopen-Funktion"
  - "Dateizeiger [C++], Neuzuweisen"
  - "freopen-Funktion"
  - "tfreopen-Funktion"
  - "wfreopen-Funktion"
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# freopen, _wfreopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Weist einen Dateizeiger neu zu.  Weitere sichere Versionen dieser Funktionen finden Sie unter [freopen\_s, \_wfreopen\_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
## Syntax  
  
```  
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
  
#### Parameter  
 `path`  
 Pfad der neuen Datei.  
  
 `mode`  
 Zugriffstyp zulässig.  
  
 `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger an die gerade geöffnete Datei zurück.  Wenn ein Fehler auftritt, wird die ursprüngliche Datei geschlossen und die Funktion gibt einen `NULL`\-Zeigerwert zurück.  Wenn `path`, `mode`, oder `stream` ein NULL\-Zeiger oder `filename` eine leere Zeichenfolge ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `NULL` zurück.  
  
 Weitere Informationen zu diesen und anderen Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [freopen\_s, \_wfreopen\_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
 Die Funktion `freopen` schließt die derzeit `stream` zugeordnete Datei und weist `stream` der durch `path` *angegebenen Datei erneut zu.* `_wfreopen` ist eine Breitzeichenversion von `_freopen`; Die Argumente `path` und `mode` für `_wfreopen` sind Zeichenfolgen mit Breitzeichen.  `_wfreopen` und `_freopen` verhalten sich andernfalls identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tfreopen`|`freopen`|`freopen`|`_wfreopen`|  
  
 `freopen` wird normalerweise verwendet, um die bereits geöffneten Dateien `stdin`, `stdout` und `stderr` zu den vom Benutzer angegebenen Dateien umzuleiten.  Die neue Datei, die `stream` zugeordnet ist, wird mit `mode`geöffnet. Dabei handelt es sich um eine Zeichenfolge, die den für die Datei angeforderten Zugriffstyp wie folgt angibt:  
  
 `"r"`  
 Öffnet zum Lesen.  Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `freopen`\-Aufruf fehl.  
  
 `"w"`  
 Öffnet eine leere Datei zum Schreiben.  Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a"`  
 Öffnet zum Schreiben \(Anhängen\), ohne dass vor dem Schreiben neuer Daten in die Datei die EOF\-Markierung entfernt wird. Falls die Datei nicht vorhanden ist, wird sie erstellt.  
  
 `"r+"`  
 Öffnet sowohl zum Lesen als auch zum Schreiben.  \(Die Datei muss vorhanden sein.\)  
  
 `"w+"`  
 Öffnet eine leere Datei zum Lesen und Schreiben.  Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a+"`  
 Öffnet zum Lesen und Anfügen. Beim Anfügevorgang wird vor dem Schreiben neuer Daten in die Datei die EOF\-Markierung entfernt und nach Abschluss des Schreibvorgangs wiederhergestellt. Falls die Datei nicht vorhanden ist, wird sie erstellt.  
  
 Die Typen `"w"` und `"w+"` sind mit Vorsicht zu verwenden, da sie vorhandene Dateien zerstören können.  
  
 Bei einer mit dem Zugriffstyp `"a"` oder `"a+"` geöffneten Datei erfolgen alle Schreibvorgänge am Ende der Datei.  Obwohl der Dateizeiger mithilfe von `fseek` oder `rewind` neu positioniert werden kann, wird der Dateizeiger immer wieder an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird.  Folglich können vorhandene Daten nicht überschrieben werden.  
  
 Bei dem Modus `"a"` wird die EOF\-Markierung nicht entfernt, bevor Daten an die Datei angefügt werden.  Nach dem Anfügen werden durch den MS\-DOS\-Befehl TYPE nur Daten bis zur ursprünglichen EOF\-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden.  Bei dem Modus `"a+"` wird die EOF\-Markierung entfernt, bevor Daten an die Datei angefügt werden.  Nach dem Anhängen werden mit dem Befehl MS\-DOS TYPE alle Daten in der Datei angezeigt.  Der Modus `"a+"` ist für das Anfügen von Daten an eine Streamdatei erforderlich, die mit der EOF\-Markierung STRG\+Z beendet wird.  
  
 Wenn als Zugriffstyp `"r+"`, `"w+"` oder `"a+"` angegeben wird, sind sowohl Lese\- als auch Schreibvorgänge zulässig \(die Datei ist zum Aktualisieren geöffnet\).  Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) oder [rewind](../../c-runtime-library/reference/rewind.md) vorhanden sein.  Bei Bedarf kann die aktuelle Position für den Vorgang `fsetpos` oder `fseek` angegeben werden.  Zusätzlich zu den oben aufgeführten Werten kann eines der folgenden Zeichen in der `mode`\-Zeichenfolge enthalten sein, um den Übersetzungsmodus für neue Zeilen anzugeben.  
  
 `t`  
 Öffnet im \(übersetzten\) Textmodus. Wagenrücklauf\-\/Zeilenvorschub\(CR\-LF\)\-Kombinationen werden bei der Eingabe in einzelne Zeilenvorschubszeichen \(LF\-Zeichen\) übersetzt. LF\-Zeichen werden bei der Ausgabe in CR\-LF\-Kombinationen übersetzt.  Außerdem wird STRG\+Z bei der Eingabe als EOF\-Zeichen interpretiert.  In den Dateien, die für Lese\- oder Lese\- und Schreibvorgänge mit `"a+"` geöffnet sind, prüft die Laufzeitbibliothek, ob am Ende der Datei STRG\+Z vorhanden ist, und entfernt ggf. diesen Wert.  Dies geschieht, da ein Verwenden von `fseek` und `ftell` zum Navigieren innerhalb der Datei dazu führen kann, dass sich `fseek` in der Nähe von Dateiende nicht ordnungsgemäß verhält.  Die `t`\-Option ist eine Microsoft\-Erweiterung, die bei einer gewünschten ANSI\-Portabilität nicht verwendet werden sollte.  
  
 `b`  
 Öffnet im \(unübersetzten\) Binärmodus; die oben genannten Übersetzungen werden unterdrückt.  
  
 Wenn `t` oder `b` nicht in `mode` angegeben ist, wird der Standardübersetzungsmodus durch die globale Variable [\_fmode](../../c-runtime-library/fmode.md) definiert.  Wenn dem Argument `t` oder `b` vorangestellt wird, schlägt die Funktion fehl und gibt `NULL` zurück.  
  
 Eine Erörterung von Text\- und Binärmodi finden Sie unter [Text\- und Binärmodus\-Datei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`freopen`|\<stdio.h\>|  
|`_wfreopen`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
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
  
  **erfolgreich erneut zugeordnet.**  
**Für die Datei "freopen.out"**   
## .NET Framework-Entsprechung  
  
-   <xref:System.IO.File.Open*>  
  
-   <xref:System.IO.FileStream.#ctor*>  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [\_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)