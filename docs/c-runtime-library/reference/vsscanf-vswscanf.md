---
title: "vsscanf, vswscanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "vsscanf"
  - "vswscanf"
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
  - "_vstscanf"
  - "vsscanf"
  - "vswscanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vsscanf-Funktion"
  - "vswscanf-Funktion"
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# vsscanf, vswscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Liest formatierte Daten aus einer Zeichenfolge.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [vsscanf\_s, vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md).  
  
## Syntax  
  
```  
int vsscanf(  
   const char *buffer,  
   const char *format,  
   va_list arglist  
);  
int vswscanf(  
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
 Die `vsscanf`\-Funktion liest Daten von `buffer` in die Speicherorte, die in der `arglist`\-Argumentliste von jedem Argument angegeben werden.  Jedes Argument in der Liste muss ein Zeiger auf eine Variable sein, deren Typ einem Typspezifizierer in `format` entspricht.  Das `format`\-Argument steuert die Interpretation der Eingabefelder und hat die gleiche Form und Funktion wie das `format`\-Argument für die `scanf`\-Funktion.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
> [!IMPORTANT]
>  Wenn Sie `vsscanf` verwenden, um eine Zeichenfolge zu lesen, müssen Sie immer einer Breite für das `%s`\-Format angeben \(beispielsweise `"%32s"` anstelle von `"%s"`\). Anderenfalls kann eine falsch formatierte Eingabe zu einem Pufferüberlauf führen.  
  
 `vswscanf` ist eine Breitzeichenversion von `vsscanf`. Die Argumente für `vswscanf` sind Zeichenfolgen mit Breitzeichen.  `vsscanf` verarbeitet keine Multibyte\-Hexadezimalzeichen.  `vswscanf` verarbeitet keine Unicode\-Hexadezimalzeichen in voller Breite \(Kompatibilitätszonenzeichen\).  Andernfalls verhalten sich `vswscanf` und `vsscanf` identisch.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_vstscanf`|`vsscanf`|`vsscanf`|`vswscanf`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`vsscanf`|\<stdio.h\>|  
|`vswscanf`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_vsscanf.c  
// compile with: /W3  
// This program uses vsscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vsscanf(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf(tokenstring, format, arglist);  
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
    call_vsscanf(tokenstring, "%80s", s);  
    call_vsscanf(tokenstring, "%c", &c);  
    call_vsscanf(tokenstring, "%d", &i);  
    call_vsscanf(tokenstring, "%f", &fp);  
  
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
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf\_s, vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)