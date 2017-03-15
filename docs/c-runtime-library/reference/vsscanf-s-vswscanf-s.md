---
title: "vsscanf_s, vswscanf_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vswscanf_s"
  - "vsscanf_s"
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
  - "vsscanf_s"
  - "vswscanf_s"
  - "_vstscanf_s"
dev_langs: 
  - "C++"
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# vsscanf_s, vswscanf_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten aus einer Zeichenfolge.  Diese Versionen von [vsscanf, vswscanf](../../c-runtime-library/reference/vsscanf-vswscanf.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
int vsscanf_s(  
   const char *buffer,  
   const char *format,  
   va_list argptr  
);   
int vswscanf_s(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   va_list arglist  
);   
```  
  
#### Parameter  
 `buffer`  
 Gespeicherte Daten  
  
 `format`  
 Formatsteuerzeichenfolge.  Weitere Informationen finden Sie unter [Formatangabefelder: scanf\- und wscanf\-Funktionen](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `arglist`  
 Variablenargumentenliste.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt die Anzahl der Felder zurück, die erfolgreich konvertiert und zugewiesen wurden; der Rückgabewert umfasst keine Felder, die gelesen, aber nicht zugewiesen wurden.  Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.  Der Rückgabewert bei einem Fehler oder beim Erreichen des Endes der Zeichenfolge vor der ersten Konvertierung lautet `EOF`.  
  
 Wenn `buffer` oder `format` ein `NULL`\-Zeiger ist, wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `vsscanf_s`\-Funktion liest Daten von `buffer` in die Speicherorte, die in der `arglist`\-Argumentliste von jedem Argument angegeben werden.  Die Argumente in der Argumentliste geben Zeiger zu den Variablen an, die einen Typ haben, der einem Typspezifizierer in `format` entspricht.  Im Gegensatz zu den weniger sicheren `vsscanf`\-Versionen ist bei der Verwendung der Typfeldzeichen `c`, `C`, `s`, `S` oder von in `[]` enthaltenen Zeichenfolgensteuerungssätzen ein Puffergrößenparameter erforderlich.  Nach jedem Pufferparameter, der dies erfordert, muss die Puffergröße in Zeichen als zusätzlicher Parameter angegeben werden.  
  
 Die Puffergröße enthält das abschließende NULL\-Zeichen.  Ein Feld für die Breitenangabe muss verwendet werden, um sicherzustellen, dass das eingelesene Token in den Puffer passt.  Wenn kein Feld für die Breiteangabe verwendet wird und das eingelesen Token zu groß für den Puffer ist, wird nichts in diesen Puffer geschrieben.  
  
 Weitere Informationen finden Sie unter [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) und [scanf\-Typenfeldzeichen](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Der Größenparameter ist vom Typ `unsigned` und nicht vom Typ `size_t`.  
  
 Das `format`\-Argument steuert die Interpretation der Eingabefelder und hat die gleiche Form und Funktion wie das `format`\-Argument für die `scanf_s`\-Funktion.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
 `vswscanf_s` ist eine Breitzeichenversion von `vsscanf_s`. Die Argumente für `vswscanf_s` sind Zeichenfolgen mit Breitzeichen.  `vsscanf_s` verarbeitet keine Multibyte\-Hexadezimalzeichen.  `vswscanf_s` verarbeitet keine Unicode\-Hexadezimalzeichen in voller Breite \(Kompatibilitätszonenzeichen\).  Andernfalls verhalten sich `vswscanf_s` und `vsscanf_s` identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_vstscanf_s`|`vsscanf_s`|`vsscanf_s`|`vswscanf_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`vsscanf_s`|\<stdio.h\>|  
|`vswscanf_s`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_vsscanf_s.c  
// compile with: /W3  
// This program uses vsscanf_s to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
#include <stdlib.h>  
  
int call_vsscanf_s(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf_s(tokenstring, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    char  tokenstring[] = "15 12 14...";  
    char  s[81];  
    char  c;  
    int   i;  
    float fp;  
  
    // Input various data from tokenstring:  
    // max 80 character string:  
    call_vsscanf_s(tokenstring, "%80s", s, _countof(s));  
    call_vsscanf_s(tokenstring, "%c", &c, sizeof(char));  
    call_vsscanf_s(tokenstring, "%d", &i);  
    call_vsscanf_s(tokenstring, "%f", &fp);  
  
    // Output the data read  
    printf("String    = %s\n", s);  
    printf("Character = %c\n", c);  
    printf("Integer:  = %d\n", i);  
    printf("Real:     = %f\n", fp);  
}  
```  
  
  **Zeichenfolge    \= 15**  
**Zeichen \= 1**  
**Ganze Zahl:  \= 15**  
**Real:     \= 15.000000**   
## .NET Framework-Entsprechung  
 Siehe `Parse`\-Methoden wie [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf, vswscanf](../../c-runtime-library/reference/vsscanf-vswscanf.md)