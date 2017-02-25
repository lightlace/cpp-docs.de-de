---
title: "fopen, _wfopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfopen"
  - "fopen"
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
  - "fopen"
  - "_wfopen"
  - "_tfopen"
  - "corecrt_wstdio/_wfopen"
  - "stdio/fopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Öffnen von Dateien, für Datei-e/a"
  - "wfopen-Funktion"
  - "tfopen-Funktion"
  - "_tfopen-Funktion"
  - "_wfopen-Funktion"
  - "Dateien [C++], öffnen"
  - "fopen-Funktion"
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
caps.latest.revision: 56
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 56
---
# fopen, _wfopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet eine Datei. Es sind sicherere Versionen dieser Funktionen verfügbar, die eine zusätzliche Parameterüberprüfung durchführen und Fehlercodes zurückgeben. Siehe dazu [fopen\_s, \_wfopen\_s](../../c-runtime-library/reference/fopen-s-wfopen-s.md).  
  
## Syntax  
  
```  
FILE *fopen(   
   const char *filename,  
   const char *mode   
);  
FILE *_wfopen(   
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### Parameter  
 `filename`  
 Dateiname  
  
 `mode`  
 Art des Zugriffs, der aktiviert ist.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf die geöffnete Datei zurück. Ein NULL\-Zeigerwert gibt einen Fehler an. Wenn `filename` oder `mode``NULL` oder eine leere Zeichenfolge ist, lösen diese Funktionen den Handler für ungültige Parameter aus, der in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `NULL` zurück und stellen `errno` auf `EINVAL` ein.  
  
 Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `fopen`\-Funktion öffnet die Datei, die von `filename` angegeben wird. Standardmäßig wird bei einer schmalen `filename`\-Zeichenfolge angenommen, dass sie die ANSI\-Codepage \(CP\_ACP\) verwendet. In Windows\-Desktopanwendungen kann dies in die OEM\-Codepage \(CP\_OEMCP\) geändert werden, indem Sie die [SetFileApisToOEM](https://msdn.microsoft.com/library/windows/desktop/aa365534\(v=vs.85\).aspx)\-Funktion verwenden. Mit der [AreFileApisANSI](https://msdn.microsoft.com/library/windows/desktop/aa363781\(v=vs.85\).aspx)\-Funktion können Sie ermitteln, ob für `filename` die Verwendung der ANSI\-Codepage oder der OEM\-Codepage \(Systemvorgabe\) angenommen wird.`_wfopen` ist eine Breitzeichenversion von `fopen`. Die Argumente für `_wfopen` sind Zeichenfolgen mit Breitzeichen. Andernfalls verhalten sich `_wfopen` und `fopen` identisch. Die alleinige Verwendung von `_wfopen` wirkt sich nicht auf den programmierten Zeichensatz aus, der für den Dateistream verwendet wird.  
  
 `fopen` akzeptiert Pfade, die zum Zeitpunkt der Ausführung im Dateisystem gültig sind. `fopen` akzeptiert UNC\-Pfade und Pfade mit zugeordneten Netzlaufwerken, solange das System, das den Code ausführt, zum Zeitpunkt der Ausführung Zugriff auf die Freigabe oder das zugeordnete Netzlaufwerk hat. Wenn Sie Pfade für `fopen` erstellen, überprüfen Sie, ob Laufwerke, Pfade oder Netzwerkfreigaben in der Ausführungsumgebung verfügbar sind. Als Verzeichnistrennzeichen in einem Pfad können Sie entweder den Schrägstrich \(\/\) oder den umgekehrten Schrägstrich \(\\\) verwenden.  
  
 Überprüfen Sie stets den Rückgabewert, um zu ermitteln, ob der Zeiger NULL ist, bevor Sie weitere Vorgänge mit der Datei ausführen. Wenn ein Fehler auftritt, wird die globale Variable `errno` festgelegt. Sie kann verwendet werden, um bestimmte Fehlerinformationen abzurufen. Weitere Informationen finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Unterstützung für Unicode  
 `fopen` unterstützt Unicode\-Dateistreams. Um eine Unicode\-Datei zu öffnen, geben Sie ein `ccs`\-Flag, das die gewünschte Codierung angibt, wie folgt an `fopen` weiter.  
  
 `FILE *fp = fopen("newfile.txt", "rt+, ccs=encoding");`  
  
 Zulässige Werte von `encoding` sind `UNICODE`, `UTF-8` und `UTF-16LE`.  
  
 Wenn eine Datei im Unicode\-Modus geöffnet wird, übersetzen die Eingabefunktionen die aus der Datei gelesenen Daten in UTF\-16\-Daten, die als Datentyp `wchar_t` gespeichert werden. Funktionen, die in eine im Unicode\-Modus geöffnete Datei schreiben, erwarten Puffer, die UTF\-16\-Daten, die als Datentyp `wchar_t` gespeichert sind. Wenn eine Datei als UTF\-8 kodiert ist, dann werden UTF\-16\-Daten beim Schreiben in UTF\-8 übersetzt, und die UTF\-8\-kodierten Inhalte der Datei werden beim Lesen in UTF\-16 übersetzt. Der Versuch, eine ungerade Anzahl von Bytes im Unicode\-Modus zu lesen oder zu schreiben, führt zu einem [Parametervalidierungsfehler](../../c-runtime-library/parameter-validation.md). Wenn Sie Daten lesen oder schreiben möchten, die in Ihrem Programm als UTF\-8 gespeichert sind, verwenden Sie den Text\- oder Binärdateienmodus anstelle eines Unicode\-Modus. Sie sind für jede erforderliche Kodierungsübersetzung verantwortlich.  
  
 Wenn die Datei bereits vorhanden ist und zum Lesen oder Anhängen geöffnet ist, bestimmt die Bytereihenfolge\-Marke \(BOM\), sofern in der Datei vorhanden, die Codierung. Die BOM\-Codierung hat Vorrang vor der durch das `ccs`\-Flag angegebenen Codierung. Die `ccs`\-Codierung wird nur verwendet, wenn keine BOM vorhanden ist oder wenn die Datei neu ist.  
  
> [!NOTE]
>  Die BOM\-Erkennung gilt nur für Dateien, die im Unicode\-Modus geöffnet sind \(das heißt durch Übergeben des `ccs`\-Flags\).  
  
 Die folgende Tabelle fasst die Modi zusammen, die für verschiedene `ccs`\-Flags für `fopen` sowie für die Bytereihenfolge\-Marken in der Datei verwendet werden.  
  
### Verwendete Codierungen auf Grundlage von ccs\-Flag und BOM  
  
|`ccs`\-Flag|Keine BOM \(oder neue Datei\)|BOM: UTF\-8|BOM: UTF\-16|  
|-----------------|-----------------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 In Dateien, die zum Schreiben im Unicode\-Modus geöffnet sind, wird automatisch eine BOM geschrieben.  
  
 Wenn `mode` „`a, ccs=<encoding>`“ ist, versucht `fopen` zuerst, die Datei mit Lesezugriff und Schreibzugriff zu öffnen. Ist der Vorgang erfolgreich, liest die Funktion die BOM, um die Codierung für die Datei zu bestimmen. Schlägt der Vorgang fehl, verwendet die Funktion die Standardcodierung für die Datei. In jedem Fall öffnet `fopen` die Datei dann nur mit Schreibzugriff erneut. \(Dies gilt nur für den `a`\-Modus, nicht für den `a+`\-Modus.\)  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tfopen`|`fopen`|`fopen`|`_wfopen`|  
  
 Die Zeichenfolge `mode` gibt die Art des Zugriffs, der für die Datei angefordert wird, wie folgt an.  
  
 `"r"`  
 Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, schlägt der `fopen`\-Aufruf fehl.  
  
 `"w"`  
 Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a"`  
 Wird vor dem Schreiben neuer Daten in die Datei zum Schreiben am Ende der Datei \(Anfügen\) geöffnet, ohne die EOF\-Markierung \(end\-of\-file, Dateiende\) zu entfernen. Erstellt die Datei, wenn sie nicht vorhanden ist.  
  
 `"r+"`  
 Öffnet sowohl zum Lesen als auch zum Schreiben. Die Datei muss vorhanden sein.  
  
 `"w+"`  
 Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 `"a+"`  
 Öffnet sich zum Lesen und Anfügen. Der Anfügevorgang umfasst das Entfernen der EOF\-Markierung, bevor neue Daten in die Datei geschrieben werden. Die EOF\-Markierung wird nach Abschluss des Schreibvorgangs nicht wiederhergestellt. Erstellt die Datei, wenn sie nicht vorhanden ist.  
  
 Bei einer mit dem Zugriffstyp `"a"` oder `"a+"` geöffneten Datei erfolgen alle Schreibvorgänge am Ende der Datei. Der Dateizeiger kann mit `fseek` oder `rewind` neu angeordnet werden, er wird jedoch immer wieder zurück an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird. Daher können vorhandene Daten nicht überschrieben werden.  
  
 Der Modus `"a"` entfernt die EOF\-Markierung nicht, bevor sie an die Datei angefügt wird. Nach dem Anfügen werden durch den MS\-DOS\-Befehl TYPE nur Daten bis zur ursprünglichen EOF\-Markierung angezeigt, aber keine Daten, die an die Datei angefügt wurden. Bevor sie an die Datei angefügt wird, entfernt der `"a+"`\-Modus die EOF\-Markierung. Nach dem Anhängen werden mit dem Befehl MS\-DOS TYPE alle Daten in der Datei angezeigt. Der Modus `"a+"` ist für das Anfügen von Daten an eine Streamdatei erforderlich, die mit der EOF\-Markierung STRG\+Z beendet wird.  
  
 Wenn als Zugriffstyp `"r+"`, `"w+"` oder `"a+"` angegeben wird, sind sowohl Lese\- als auch Schreibvorgänge zulässig \(die Datei ist zum Aktualisieren geöffnet\). Wenn Sie jedoch vom Lesevorgang in den Schreibvorgang wechseln, muss die Eingabeoperation eine EOF\-Markierung antreffen. Wenn keine EOF\-Markierung vorhanden ist, müssen Sie einen zwischenzeitlichen Aufruf einer dateipositionierenden Funktion verwenden. Die dateipositionierenden Funktionen sind `fsetpos`, `fseek` und `rewind`. Wenn Sie vom Schreibvorgang in den Lesevorgang wechseln, müssen Sie einen zwischenzeitlichen Aufruf von `fflush` oder einer dateipositionierenden Funktion ausführen.  
  
 Neben früheren Werte können die folgenden Zeichen an `mode` angefügt werden, um den Übersetzungsmodus für Zeilenumbruchzeichen anzugeben.  
  
 `t`  
 Öffnen im Textmodus \(übersetzt\). In diesem Modus wird STRG\+Z als EOF\-Zeichen bei Eingabe interpretiert. In den Dateien, die für das Lesen\/Schreiben mit `"a+"` geöffnet sind, überprüft `fopen` die Datei auf STRG\+Z am Dateiende, und entfernt die Markierung, soweit möglich. Dies geschieht, da ein Verwenden von `fseek` und `ftell` zum Navigieren innerhalb einer Datei, die mit Strg\+Z endet, dazu führen kann, dass sich `fseek` in der Nähe des Dateiendes nicht richtig verhält.  
  
 Im Textmodus werden Kombinationen aus Wagenrücklauf\- und Zeilenvorschubzeichen in einzelne Zeilenvorschübe bei Eingabe übersetzt, und Zeilenvorschubzeichen werden bei der Ausgabe in Kombinationen aus Wagenrücklauf\- und Zeilenvorschubzeichen übersetzt. Wenn eine Stream\-E\/A\-Funktion von Unicode im Textmodus \(Standard\) funktioniert, wird angenommen, dass es sich bei Quell\- oder Zielstream um eine Sequenz von Multibytezeichen handelt. Daher konvertieren die Unicode Streameingabefunktionen Multibytezeichen in Breitzeichen \(wie bei einem Aufruf der `mbtowc`\-Funktion\). Aus demselben Grund konvertieren die Unicode\-Streamausgabefunktionen Breitzeichen in Multibytezeichen \(wie bei einem Aufruf der `wctomb`\-Funktion\).  
  
 `b`  
 Öffnen im binären \(unübersetzten\) Modus; Übersetzungen von Wagenrücklauf\- und Zeilenvorschubzeichen werden unterdrückt.  
  
 Wenn `t` oder `b` nicht in `mode` angegeben ist, wird der Standardübersetzungsmodus durch die globale Variable [\_fmode](../../c-runtime-library/fmode.md) definiert. Wenn dem Argument `t` oder `b` vorangestellt wird, schlägt die Funktion fehl und gibt `NULL` zurück.  
  
 Weitere Informationen darüber, wie Sie Textmodus und Binärmodus in Unicode und im Multibyte\-Stream\-E\/A verwenden, finden Sie unter [Text\- und Binärmodusdatei\-E\/A](../../c-runtime-library/text-and-binary-mode-file-i-o.md) und [Unicodestream\-E\/A im Text\- und Binärmodus](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
 `c`  
 Aktivieren Sie das Commitflag für den zugeordneten Parameter `filename`, sodass der Inhalt des Dateipuffers direkt auf einen Datenträger geschrieben wird, wenn `fflush` oder `_flushall` aufgerufen wird.  
  
 `n`  
 Setzen Sie das Commitflag für den zugeordneten Parameter `filename` auf "no\-commit" zurück. Dies ist die Standardeinstellung. Dabei wird auch das globale Commitflag überschrieben, wenn Sie das Programm mit COMMODE.OBJ verknüpfen. Der Standardwert des globalen Commitflags lautet "no\-commit", es sei denn, Sie verknüpfen das Programm explizit mit COMMODE.OBJ \(siehe [Linkoptionen](../../c-runtime-library/link-options.md)\).  
  
 `N`  
 Gibt an, dass die Datei nicht von untergeordneten Prozessen geerbt wird.  
  
 `S`  
 Gibt an, dass das Zwischenspeichern für den sequenziellen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.  
  
 `R`  
 Gibt an, dass das Zwischenspeichern für den zufälligen Zugriff vom Datenträger optimiert, aber nicht darauf beschränkt ist.  
  
 `T`  
 Gibt an, dass eine Datei temporär ist. Wenn möglich, wird sie nicht auf den Datenträger geschrieben.  
  
 `D`  
 Gibt an, dass eine Datei temporär ist. Sie wird gelöscht, wenn der letzte Dateizeiger geschlossen wird.  
  
 `ccs=ENCODING`  
 Gibt den codierten Zeichensatz an, der für diese Datei verwendet werden soll \(`UTF-8`, `UTF-16LE` oder `UNICODE`\). Machen Sie keine Angabe, wenn Sie ANSI\-Codierung wünschen.  
  
 Gültige Zeichen für die `mode`\-Zeichenfolge, die in `fopen` und `_fdopen` verwendet wird, entsprechen wie folgt den `oflag`\-Argumenten, die in [\_open](../../c-runtime-library/reference/open-wopen.md) und [\_sopen](../../c-runtime-library/reference/sopen-wsopen.md) verwendet werden.  
  
|Zeichen in der mode\-Zeichenfolge|Der entsprechende `oflag`\-Wert für `_open`\/`_sopen`|  
|---------------------------------------|-----------------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND`  \(meistens `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`\)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` \(meistens `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` \)|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` \(meistens `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`\)|  
|`w+`|`_O_RDWR` \(meistens `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`\)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Keine|  
|`n`|Keine|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 Wenn Sie den `rb`\-Modus verwenden, keinen Code portieren müssen und davon ausgehen, den Großteil einer großen Datei zu lesen, oder die Netzwerkleistung nicht relevant ist, sind möglicherweise Win32\-Dateien mit Speicherzuordnung auch eine Option.  
  
## Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------------|  
|`fopen`|\<stdio.h\>|  
|`_wfopen`|\<stdio.h\> oder \<wchar.h\>|  
  
 `_wfopen` ist eine Microsoft\-Erweiterung. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
 Die `c`\-Optionen `n`, `t`, `S`, `R`, `T`, `D` und `mode` sind Microsoft\-Erweiterungen für `fopen` und `_fdopen` und sollten nicht dort verwendet werden, wo ANSI\-Portabilität gewünscht wird.  
  
## Beispiel  
 Das folgende Programm öffnet zwei Dateien.  Es verwendet `fclose`, um die erste Datei zu schließen, und `_fcloseall`, um alle übrigen Dateien zu schließen.  
  
```  
  
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
Die Datei 'crt_fopen.c' wurde geöffnet Die Datei 'data2' wurde geöffnet Anzahl der von '_fcloseall' geschlossenen Dateien: 1  
```  
  
## Beispiel  
 Das folgende Programm erstellt eine Datei \(oder überschreibt eine, sofern vorhanden\) im Textmodus mit Unicode\-Codierung.  Anschließend schreibt es zwei Zeichenfolgen in die Datei und schließt sie. Die Ausgabe ist eine Datei namens \_wfopen\_test.xml, die die Daten aus dem Ausgangsabschnitt enthält.  
  
```  
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
  
## .NET Framework-Entsprechung  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [\_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)