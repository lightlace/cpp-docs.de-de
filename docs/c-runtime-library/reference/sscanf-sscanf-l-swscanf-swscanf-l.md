---
title: "sscanf, _sscanf_l, swscanf, _swscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "swscanf"
  - "sscanf"
  - "_sscanf_l"
  - "_swscanf_l"
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
  - "_sscanf_l"
  - "_stscanf"
  - "swscanf"
  - "_stscanf_l"
  - "sscanf"
  - "_swscanf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_sscanf_l-Funktion"
  - "_stscanf-Funktion"
  - "_stscanf_l-Funktion"
  - "_swscanf_l-Funktion"
  - "Lesen von Daten, Zeichenfolgen"
  - "sscanf-Funktion"
  - "sscanf_l-Funktion"
  - "Zeichenfolgen [C++], Lesen"
  - "Zeichenfolgen [C++], Lesen von Daten aus"
  - "stscanf-Funktion"
  - "stscanf_l-Funktion"
  - "swscanf-Funktion"
  - "swscanf_l-Funktion"
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# sscanf, _sscanf_l, swscanf, _swscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lesen formatierte Daten von einer Zeichenfolge.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).  
  
## Syntax  
  
```  
int sscanf(  
   const char *buffer,  
   const char *format [,  
   argument ] ...   
);  
int _sscanf_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...   
);  
int swscanf(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...   
);  
int _swscanf_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...   
);  
```  
  
#### Parameter  
 `buffer`  
 Gespeicherte Daten  
  
 `format`  
 Formatsteuerzeichenfolge.  Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `argument`  
 Optionale Argumente  
  
 `locale`  
 Das zu verwendende Gebietsschema  
  
## Rückgabewert  
 Jede dieser Funktionen gibt die Anzahl der erfolgreichen konvertierten und zugewiesenen Felder zurück; der Rückgabewert enthält Felder, die nicht gelesen wurden, jedoch nicht zugewiesen.  Ein Rückgabewert von 0 gibt an, dass keine Felder zugewiesen wurden.  Der Rückgabewert bei einem Fehler oder beim Erreichen des Endes der Zeichenfolge vor der ersten Konvertierung lautet `EOF`.  
  
 Wenn `buffer` oder `format` ein `NULL`\-Zeiger ist, wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 Weitere Informationen über diese und andere Fehlercodes finden Sie unter [\_doserrno, errno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `sscanf`\-Funktion liest Daten aus `buffer` in den Speicherort, der durch ein `argument` angegeben wird.  Jedes `argument` muss ein Zeiger auf eine Variable mit einem Typ sein, der einem Typspezifizierer in `format` entspricht.  Das `format`\-Argument steuert die Interpretation der Eingabefelder und hat die gleiche Form und Funktion wie das `format`\-Argument für die `scanf`\-Funktion.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
> [!IMPORTANT]
>  Beim Lesen einer Zeichenfolge mit `sscanf` sollten Sie immer einer Breite für das `%s`\-Format angeben \(z. B. `"%32s"` anstelle von `"%s"`\). Anderenfalls kann eine nicht richtig formatierte Eingabe leicht einen Pufferüberlauf verursachen.  
  
 `swscanf` ist eine Breitzeichenversion von `sscanf`. Die Argumente für `swscanf` sind Zeichenfolgen mit Breitzeichen.  `sscanf` verarbeitet keine Mehrbytehexadezimalzeichen.  `swscanf` verarbeitet keine Unicode\-Hexadezimalzeichen in voller Breite \(Kompatibilitätszonenzeichen\).  Andernfalls verhalten sich `swscanf` und `sscanf` identisch.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_stscanf`|`sscanf`|`sscanf`|`swscanf`|  
|`_stscanf_l`|`_sscanf_l`|`_sscanf_l`|`_swscanf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`sscanf`, `_sscanf_l`|\<stdio.h\>|  
|`swscanf`, `_swscanf_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_sscanf.c  
// compile with: /W3  
// This program uses sscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string:  
   sscanf( tokenstring, "%80s", s ); // C4996  
   sscanf( tokenstring, "%c", &c );  // C4996  
   sscanf( tokenstring, "%d", &i );  // C4996  
   sscanf( tokenstring, "%f", &fp ); // C4996  
   // Note: sscanf is deprecated; consider using sscanf_s instead  
  
   // Output the data read  
   printf( "String    = %s\n", s );  
   printf( "Character = %c\n", c );  
   printf( "Integer:  = %d\n", i );  
   printf( "Real:     = %f\n", fp );  
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
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)