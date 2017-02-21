---
title: "scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wscanf_s"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_scanf_s_l"
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
  - "wscanf_s"
  - "_tscanf_s_l"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_tscanf_s"
  - "_scanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lesen von Daten [C++] aus Eingabestreams"
  - "Puffer [C++], Pufferüberlauf"
  - "_scanf_s_l-Funktion"
  - "_wscanf_s_l-Funktion"
  - "tscanf_s_l-Funktion"
  - "tscanf_s-Funktion"
  - "scanf_s-Funktion"
  - "aus dem Eingabedatenstrom lesen von Daten [C++]"
  - "wscanf_s-Funktion"
  - "_tscanf_s_l-Funktion"
  - "_tscanf_s-Funktion"
  - "scanf_s_l-Funktion"
  - "formatierte Daten [C++] aus Eingabestreams"
  - "wscanf_s_l-Funktion"
  - "Puffer [C++], Vermeiden von Überläufen"
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten aus dem Standardeingabestream. Diese Versionen von [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) wurde die Sicherheit wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntax  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Parameter  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Gibt die Anzahl von Feldern zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden. Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden. Der Rückgabewert ist im Fall eines Fehlers `EOF`. Dies gilt auch, wenn das Dateiendezeichen oder das Zeichenfolgeendezeichen beim ersten Versuch, das Zeichen zu lesen, erkannt wird. Wenn `format` ist eine `NULL` \-Zeiger, der Handler für ungültige Parameter aufgerufen, wie in beschrieben [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, geben `scanf_s` und `wscanf_s` den Wert `EOF` zurück und setzen `errno` auf `EINVAL`.  
  
 Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `scanf_s`\-Funktion liest Daten aus dem Standardeingabestream `stdin` und schreibt die Daten in den Speicherort, der von `argument` angegeben wird. Jedes `argument` muss ein Zeiger auf einen Variablentyp sein, der einem Typspezifizierer im `format` entspricht. Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 `wscanf_s` ist eine Breitzeichenversion von `scanf_s`. Das `format`\-Argument für `wscanf_s` ist eine Breitzeichenfolge.`wscanf_s` und `scanf_s` verhalten sich identisch, wenn der Stream in ANSI\-Modus geöffnet ist.`scanf_s` unterstützt derzeit nicht die Eingabe aus einem UNICODE\-Stream.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Threadgebietsschemas übergeben wurde.  
  
 Anders als `scanf` und `wscanf` erfordern `scanf_s` und `wscanf_s` eine Angabe der Puffergröße für alle Eingabeparameter vom Typ `c`, `C`, `s` und `S` oder Zeichenfolgensätze, die in `[]` enthalten sind. Die Puffergröße in Zeichen wird als zusätzlicher Parameter direkt nach dem Zeiger auf den Puffer oder die Variable übergeben. Beim Lesen einer Zeichenfolge wird beispielsweise die Puffergröße für diese Zeichenfolge wie folgt übergeben:  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 Die Puffergröße enthält das abschließende NULL\-Zeichen. Sie können ein Feld für die Breitenangabe verwenden, um sicherzustellen, dass das eingelesene Token in den Puffer passt. Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`. Eine statische Umwandlung verwenden, um das Konvertieren einer `size_t` Wert `unsigned` für 64\-Bit\-Buildkonfigurationen.  
  
 Im folgenden Beispiel wird gezeigt, dass der Puffergrößenparameter die maximale Anzahl von Zeichen, aber nicht von Bytes beschreibt. Im Aufruf von `wscanf_s`, stimmt die Zeichenbreite, die von dem Puffertyp angegeben ist, nicht mit der Zeichenbreite überein, die im Formatbezeichner angegeben ist.  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 Der Formatbezeichner `S` gibt die Verwendung der Zeichenbreite an, die zu der von der Funktion unterstützten Standardbreite einen "Gegensatz" darstellt. Die Zeichen sind ein Byte breit, aber die Funktion unterstützt Doppelbytezeichen. In diesem Beispiel wird eine Zeichenfolge bis maximal 9 Einzelbytezeichen eingelesen und an einen Puffer für Doppelbytezeichen übergeben. Die Zeichen werden als Einzelbytewerte behandelt; die ersten zwei Zeichen werden in `ws[0]` gespeichert, die zweiten zwei Zeichen in `ws[1]` usw.  
  
 Im Fall von Zeichen wird ein einzelnes Zeichen wie folgt gelesen:  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 Wenn mehrere Zeichen für Zeichenfolgen gelesen werden, die nicht mit NULL abschließen, werden ganze Zahlen für die Breitenangabe und die Puffergröße verwendet.  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Weitere Informationen finden Sie unter [scanf\-Breitenangabe](../../c-runtime-library/scanf-width-specification.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 Weitere Informationen finden Sie unter [Formatangabefelder: scanf\- und wscanf\-Funktionen](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h\>|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt. Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können. Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 Dieses Programm generiert bei dieser Eingabe die folgende Ausgabe:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
Die Anzahl der Feldeingaben ist 6 der Inhalt ist: 71 98.599998 h Z Byte Zeichen die Anzahl der Felder, die Eingabe ist der Inhalt ist 6: 36 92.300003 y n Wide Characters  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console::ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   Siehe auch `Parse` Methoden, wie z. B. [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)