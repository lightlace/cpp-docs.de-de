---
title: "printf, _printf_l, wprintf, _wprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_printf_l"
  - "wprintf"
  - "_wprintf_l"
  - "printf"
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
  - "printf"
  - "_tprintf"
  - "wprintf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_printf_l-Funktion"
  - "_tprintf-Funktion"
  - "_tprintf_l-Funktion"
  - "_wprintf_l-Funktion"
  - "Formatierter Text [C++]"
  - "printf-Funktion"
  - "printf-Funktion, Formatangabefelder"
  - "printf-Funktion, Verwenden"
  - "printf_l-Funktion"
  - "tprintf-Funktion"
  - "tprintf_l-Funktion"
  - "wprintf-Funktion"
  - "wprintf_l-Funktion"
  - "Schreiben zur Konsole"
ms.assetid: 77a854ae-5b48-4865-89f4-f2dc5cf80f52
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# printf, _printf_l, wprintf, _wprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Druckt eine formatierte Ausgabe an den Standardausgabestream.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md).  
  
## Syntax  
  
```  
int printf(  
   const char *format [,  
   argument]...   
);  
int _printf_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Parameter  
 `format`  
 Formatsteuerung  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Gibt die Anzahl gedruckter Zeichen oder einen negativen Wert zurück, wenn ein Fehler auftritt.  Wenn `format` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion – 1 zurück und stellt `errno` auf `EINVAL` ein.  Wenn **EOF** \(0xFFFF\) in `argument` auftritt, gibt die Funktion "– 1" zurück.  
  
 Weitere Informationen zu `errno` und Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `printf`\-Funktion formatiert eine Reihe von Zeichen und Werten für den Standardausgabestream `stdout` und gibt sie aus.  Wenn Argumente der `format` Zeichenfolge folgen, muss die `format`\-Zeichenfolge Spezifikationen enthalten, die das Ausgabeformat für die Argumente bestimmen.  `printf` und [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) verhalten sich identisch, außer dass `printf` die Ausgabe an `stdout` anstelle eines Ziels vom Typ `FILE` schreibt.  
  
 `wprintf` ist eine Breitzeichen\-Version von `printf`; `format` ist eine Zeichenfolge mit Breitzeichen.  `wprintf` und `printf` verhalten sich identisch, wenn der Stream in ANSI\-Modus geöffnet ist.  `printf` unterstützt die Ausgabe in einen UNICODE\-Stream augenblicklich nicht.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_unicode definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tprintf`|`printf`|`printf`|`wprintf`|  
  
 Das `format`\-Argument besteht aus normalen Zeichen, Escapesequenzen und \(wenn Argumente `format` folgen\) aus Formatangaben.  Die normalen Zeichen und die Escapesequenzen werden in der Reihenfolge ihrer Darstellung auf `stdout` kopiert.  Zum Beispiel die Zeile:  
  
```  
printf("Line one\n\t\tLine two\n");   
```  
  
 erzeugt die Ausgabe:  
  
```  
Line one  
        Line two  
```  
  
 [Formatspezifikationen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) beginnen immer mit einem Prozentzeichen \(`%`\) und werden von links nach rechts gelesen.  Wenn `printf` auf die erste Formatspezifikation \(falls vorhanden\) trifft, konvertiert sie den Wert des ersten Arguments in `format` und gibt ihn entsprechend aus.  Mit der zweiten Formatspezifikation wird das zweite Argument konvertiert und ausgegeben, usw.  Wenn es mehrere Argumente als Formatspezifikationen gibt, werden die zusätzlichen Argumente ignoriert.  Die Ergebnisse sind nicht definiert, wenn nicht genügend Argumente für alle Formatspezifikationen vorhanden sind.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tprintf`|`printf`|`printf`|`wprintf`|  
|`_tprintf_l`|`_printf_l`|`_printf_l`|`_wprintf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`printf`, `_printf_l`|\<stdio.h\>|  
|`wprintf`, `_wprintf_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Die Konsole wird in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps nicht unterstützt.  Die mit der Konsole verknüpften Standardstreamhandles, `stdin`, `stdout` und `stderr`, müssen umgeleitet werden, bevor sie von C\-Laufzeitfunktionen in [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-Apps verwendet werden können.  Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_printf.c  
// This program uses the printf and wprintf functions  
// to produce formatted output.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char     ch = 'h',   
            *string = "computer";  
   wchar_t  wch = L'w',   
            *wstring = L"Unicode";  
   int      count = -9234;  
   double   fp = 251.7366;  
  
   // Display integers  
   printf( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  "  
           "Unsigned: %u\n",  
           count, count, count, count );  
  
   // Display decimals  
   printf( "Decimal %d as:\n   Hex: %Xh  "  
           "C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   // Display in different radixes  
   printf( "Digits 10 equal:\n   Hex: %i  "  
           "Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   // Display characters  
   printf("Characters in field (1):\n"  
          "%10c%5hc%5C%5lc\n",  
          ch, ch, wch, wch);  
   wprintf(L"Characters in field (2):\n"  
           L"%10C%5hc%5c%5lc\n",  
           ch, ch, wch, wch);  
  
   // Display strings  
   printf("Strings in field (1):\n%25s\n"  
          "%25.4hs\n   %S%25.3ls\n",  
          string, string, wstring, wstring);  
   wprintf(L"Strings in field (2):\n%25S\n"  
           L"%25.4hs\n   %s%25.3ls\n",  
           string, string, wstring, wstring);  
  
   // Display real numbers  
   printf("Real numbers:\n   %f %.2f %e %E\n",  
          fp, fp, fp, fp );  
  
   // Display pointer  
   printf( "\nAddress as:   %p\n", &count);  
}  
```  
  
## Beispielausgabe  
  
```  
Integer formats:  
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062  
Decimal -9234 as:  
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756  
Digits 10 equal:  
   Hex: 16  Octal: 8  Decimal: 10  
Characters in field (1):  
         h    h    w    w  
Characters in field (2):  
         h    h    w    w  
Strings in field (1):  
                 computer  
                     comp  
   Unicode                      Uni  
Strings in field (2):  
                 computer  
                     comp  
   Unicode                      Uni  
Real numbers:  
   251.736600 251.74 2.517366e+002 2.517366E+002  
  
Address as:   0012FF3C  
```  
  
## .NET Framework-Entsprechung  
  
-   [System::Console::Write](https://msdn.microsoft.com/en-us/library/system.console.write.aspx)  
  
-   [System::Console::WriteLine](https://msdn.microsoft.com/en-us/library/system.console.writeline.aspx)  
  
## Siehe auch  
 [Gleitkommaunterstützung](../../c-runtime-library/floating-point-support.md)   
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [\_set\_output\_format](../../c-runtime-library/set-output-format.md)