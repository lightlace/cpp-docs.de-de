---
title: "vscanf_s, vwscanf_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vscanf_s"
  - "vwscanf_s"
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
  - "_vtscanf_s"
  - "vscanf_s"
  - "vwscanf_s"
dev_langs: 
  - "C++"
ms.assetid: 23a1c383-5b01-4887-93ce-534a1e38ed93
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# vscanf_s, vwscanf_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten aus dem Standardeingabestream.  Diese Versionen von [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
int vscanf_s(  
   const char *format,  
   va_list arglist  
);   
int vwscanf_s(  
   const wchar_t *format,  
   va_list arglist  
);  
```  
  
#### Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `arglist`  
 Variablenargumentenliste.  
  
## Rückgabewert  
 Gibt die Anzahl von Feldern zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden.  Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.  Der Rückgabewert ist im Fall eines Fehlers `EOF`. Dies gilt auch, wenn das Dateiendezeichen oder das Zeichenfolgeendezeichen beim ersten Versuch, das Zeichen zu lesen, erkannt wird.  Wenn `format` ein `NULL`\-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben `vscanf_s` und `vwscanf_s` den Wert `EOF` zurück und setzen `errno` auf `EINVAL`.  
  
 Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `vscanf_s`\-Funktion liest Daten aus dem Standardeingabestream `stdin` und schreibt die Daten in die Speicherorte, die durch die `arglist`\-Argumentliste angegeben werden.  Jedes Argument in der Liste muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer in `format` entspricht.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 `vwscanf_s` ist eine Breitzeichenversion von `vscanf_s`. Das `format`\-Argument für `vwscanf_s` ist eine Breitzeichenfolge.  `vwscanf_s` und `vscanf_s` verhalten sich identisch, wenn der Stream in ANSI\-Modus geöffnet ist.  `vscanf_s` unterstützt nicht die Eingabe aus einem UNICODE\-Stream.  
  
 Anders als `vscanf` und `vwscanf` erfordern `vscanf_s` und `vwscanf_s` eine Angabe der Puffergröße für alle Eingabeparameter vom Typ `c`, `C`, `s` und `S` oder Zeichenfolgensätze, die in `[]` enthalten sind.  Die Puffergröße in Zeichen wird als zusätzlicher Parameter direkt nach dem Zeiger auf den Puffer oder die Variable übergeben.  Die Puffergröße in Zeichen für eine `wchar_t`\-Zeichenfolge ist nicht identisch mit der Größe in Bytes.  
  
 Die Puffergröße enthält das abschließende NULL\-Zeichen.  Sie können ein Feld für die Breitenangabe verwenden, um sicherzustellen, dass das eingelesene Token in den Puffer passt.  Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`.  
  
 Weitere Informationen finden Sie unter [scanf\-Breitenangabe](../../c-runtime-library/scanf-width-specification.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_vtscanf_s`|`vscanf_s`|`vscanf_s`|`vwscanf_s`|  
  
 Weitere Informationen finden Sie unter [Formatangabefelder: scanf\- und wscanf\-Funktionen](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`vscanf_s`|\<stdio.h\>|  
|`wscanf_s`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_vscanf_s.c  
// compile with: /W3  
// This program uses the vscanf_s and vwscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vscanf_s(char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int call_vwscanf_s(wchar_t *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vwscanf_s(format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    int   i, result;  
    float fp;  
    char  c, s[81];  
    wchar_t wc, ws[81];  
    result = call_vscanf_s("%d %f %c %C %s %S", &i, &fp, &c, 1,  
                           &wc, 1, s, _countof(s), ws, _countof(ws) );  
    printf( "The number of fields input is %d\n", result );  
    printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c, wc, s, ws);  
    result = call_vwscanf_s(L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                            &wc, 1, s, _countof(s), ws, _countof(ws) );  
    wprintf( L"The number of fields input is %d\n", result );  
    wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp, c, wc, s, ws);  
}  
  
```  
  
 Wenn diesem Programm die Eingabe aus dem Beispiel übergeben wird, erzeugt es Folgendes:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
  **Die Anzahl der Feldeingaben ist 6.**  
**Der Inhalt ist: 71 98.599998 h z Byte characters**  
**Die Anzahl der Feldeingaben ist 6.**  
**Der Inhalt ist: 36 92.300003 y n Wide characters**   
## .NET Framework-Entsprechung  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   Siehe auch `Parse`\-Methoden wie [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [vscanf, vwscanf](../../c-runtime-library/reference/vscanf-vwscanf.md)