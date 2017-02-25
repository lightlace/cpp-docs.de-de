---
title: "freopen_s, _wfreopen_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfreopen_s"
  - "freopen_s"
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
  - "freopen_s"
  - "_tfreopen_s"
  - "_wfreopen_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tfreopen_s-Funktion"
  - "_wfreopen_s-Funktion"
  - "Dateizeiger [C++], Neuzuweisen"
  - "freopen_s-Funktion"
  - "tfreopen_s-Funktion"
  - "wfreopen_s-Funktion"
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# freopen_s, _wfreopen_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Weist einen Dateizeiger neu zu.  Diese Versionen von [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
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
  
#### Parameter  
 \[out\] `pFile`  
 Ein Zeiger auf den vom Aufruf bereitzustellenden Dateizeiger.  
  
 \[in\] `path`  
 Pfad der neuen Datei.  
  
 \[in\] `mode`  
 Zugriffstyp zulässig.  
  
 \[in\] `stream`  
 Zeiger zur `FILE`\-Struktur.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Fehlercode zurück.  Wenn ein Fehler auftritt, wird die ursprüngliche Datei geschlossen.  
  
## Hinweise  
 The `freopen_s`\-Funktion schließt die derzeit `stream` zugeordnete Datei und weist `stream` der durch `path.` angegebenen Datei erneut zu. `_wfreopen_s` ist eine Breitzeichenversion von `_freopen_s`. Die Argumente `path` und `mode` für `_wfreopen_s` sind Zeichenfolgen mit Breitzeichen.  `_wfreopen_s` und `_freopen_s` verhalten sich andernfalls identisch.  
  
 Wenn eines der Argumente `pFile`, `path`, `mode` oder `stream` den Wert `NULL` aufweist oder `path` eine leere Zeichenfolge ist, dann rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tfreopen_s`|`freopen_s`|`freopen_s`|`_wfreopen_s`|  
  
 `freopen_s` wird normalerweise verwendet, um die bereits geöffneten Dateien `stdin`, `stdout` und `stderr` zu den vom Benutzer angegebenen Dateien umzuleiten.  Die neue Datei, die `stream` zugeordnet ist, wird mit `mode` geöffnet. Dabei handelt es sich um eine Zeichenfolge, die den für die Datei angeforderten Zugriffstyp wie folgt angibt:  
  
 `"r"`  
 Öffnet zum Lesen.  Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `freopen_s`\-Aufruf fehl.  
  
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
  
 Wenn als Zugriffstyp `"r+",`, `"w+",` oder `"a+"` angegeben wird, sind sowohl Lese\- als auch Schreibvorgänge zulässig \(die Datei ist zum Aktualisieren geöffnet\).  Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) oder [rewind](../../c-runtime-library/reference/rewind.md) vorhanden sein.  Bei Bedarf kann die aktuelle Position für den Vorgang `fsetpos` oder `fseek` angegeben werden.  Zusätzlich zu den oben aufgeführten Werten kann eines der folgenden Zeichen in der `mode`\-Zeichenfolge enthalten sein, um den Übersetzungsmodus für neue Zeilen anzugeben.  
  
 `t`  
 Öffnet im \(übersetzten\) Textmodus. Wagenrücklauf\-\/Zeilenvorschub\(CR\-LF\)\-Kombinationen werden bei der Eingabe in einzelne Zeilenvorschubszeichen \(LF\-Zeichen\) übersetzt. LF\-Zeichen werden bei der Ausgabe in CR\-LF\-Kombinationen übersetzt.  Außerdem wird STRG\+Z bei der Eingabe als EOF\-Zeichen interpretiert.  In den Dateien, die für Lese\- oder Lese\- und Schreibvorgänge mit `"a+"` geöffnet sind, prüft die Laufzeitbibliothek, ob am Ende der Datei STRG\+Z vorhanden ist, und entfernt ggf. diesen Wert.  Dies geschieht, da ein Verwenden von `fseek` und `ftell` zum Navigieren innerhalb der Datei dazu führen kann, dass sich `fseek` in der Nähe von Dateiende nicht ordnungsgemäß verhält.  Die `t`\-Option ist eine Microsoft\-Erweiterung, die bei einer gewünschten ANSI\-Portabilität nicht verwendet werden sollte.  
  
 `b`  
 Öffnet im \(unübersetzten\) Binärmodus; die oben genannten Übersetzungen werden unterdrückt.  
  
 Wenn `t` oder `b` nicht in `mode` angegeben ist, wird der Standardübersetzungsmodus durch die globale Variable [\_fmode](../../c-runtime-library/fmode.md) definiert.  Wenn dem Argument `t` oder `b` vorangestellt wird, schlägt die Funktion fehl und gibt `NULL` zurück.  
  
 Eine Erörterung von Text\- und Binärmodi finden Sie unter [Text\- und Binärmodus\-Datei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`freopen_s`|\<stdio.h\>|  
|`_wfreopen_s`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
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
  
  **erfolgreich erneut zugeordnet.**  
**Für die Datei "freopen.out"**   
## .NET Framework-Entsprechung  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.#ctor*>  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [\_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)