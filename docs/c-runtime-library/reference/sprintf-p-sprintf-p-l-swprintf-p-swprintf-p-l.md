---
title: "_sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_swprintf_p"
  - "_sprintf_p_l"
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
  - "_sprintf_p"
  - "_swprintf_p_l"
  - "_sprintf_p_l"
  - "_swprintf_p"
  - "sprintf_p"
  - "swprint_p_l"
  - "swprintf_p"
  - "swprintf_p_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "sprintf_p_l-Funktion"
  - "swprintf_p-Funktion"
  - "swprintf_p_l-Funktion"
  - "_sprintf_p-Funktion"
  - "_sprintf_p_l-Funktion"
  - "_swprintf_p-Funktion"
  - "sprintf_p-Funktion"
  - "_stprintf_p-Funktion"
  - "stprintf_p-Funktion"
  - "_swprintf_p_l-Funktion"
  - "stprintf_p_l-Funktion"
  - "Formatierter Text [C++]"
  - "_stprintf_p_l-Funktion"
ms.assetid: a2ae78e8-6b0c-48d5-87a9-ea2365b0693d
caps.latest.revision: 18
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# _sprintf_p, _sprintf_p_l, _swprintf_p, _swprintf_p_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

zum formatierte Daten in eine Zeichenfolge mit der Möglichkeit, die Reihenfolge anzugeben, dass die Parameter in der Formatzeichenfolge verwendet werden.  
  
## Syntax  
  
```  
int _sprintf_p(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_p_l(  
   char *buffer,  
   size_t sizeOfBuffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _swprintf_p(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_p_l(  
   wchar_t *buffer,  
   size_t sizeOfBuffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] …   
);  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für die Ausgabe  
  
 `sizeOfBuffer`  
 Die maximale Anzahl der zu speichernden Zeichen.  
  
 `format`  
 Formatsteuerzeichenfolge  
  
 `argument`  
 Optionale Argumente  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 Die Anzahl geschriebener Zeichen oder "– 1" bei einem Fehler.  
  
## Hinweise  
 Die `_sprintf_p` \- Funktion formatiert und speichert eine Reihe von Zeichen und Werte in `buffer`.  Jedes `argument` \(falls vorhanden\) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert und ausgegeben.  Das Format besteht aus normalen Zeichen und hat die gleiche Form und Funktion wie das Argument `format` für `printf_p`.  Ein `NULL` Zeichen wird nach dem geschriebenen letzten Zeichen angefügt.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  Der Unterschied zwischen `_sprintf_p` und `sprintf_s` ist, dass `_sprintf_p` positionelle Parameter unterstützt, wodurch festgelegt werden kann, in welcher Reihenfolge die Argumente in der Formatzeichenfolge verwendet werden.  Weitere Informationen finden Sie unter [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_swprintf_p` ist eine Breitzeichen\-Version von `_sprintf_p`. Die Zeigerargumente zu `_swprintf_p` sind Breitzeichen\-Zeichenfolgen.  Die Erkennung von Codierungsfehlern in `_swprintf_p` unterscheidet sich möglicherweise von der in `_sprintf_p`.  `_swprintf_p` und `fwprintf_p` identisch verhalten sich, dass `_swprintf_p` schreibt Ausgabe in eine Zeichenfolge anstatt an ein Silverlight\-Ziel vom Typ `FILE`, und `_swprintf_p` erfordert den `count`\-Parameter, die maximale Anzahl der zu schreibenden Zeichen anzugeben.  Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
 `_sprintf_p` gibt die Anzahl von Bytes zurück, die in `buffer` gespeicherten und nicht angerechnet das abschließende Zeichen `NULL`.  `_swprintf_p` gibt die Anzahl der Breitzeichen zurück, die in `buffer` gespeicherten und nicht angerechnet das abschließende `NULL` Breitzeichen.  Wenn `buffer` oder `format` ein NULL\-Zeiger ist oder wenn Formatzeichenfolge die ungültige Formatierungszeichen enthält, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_stprintf_p`|`_sprintf_p`|`_sprintf_p`|`_swprintf_p`|  
|`_stprintf_p_l`|`_sprintf_p_l`|`_sprintf_p_l`|`_swprintf_p_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_sprintf_p`, `_sprintf_p_l`|\<stdio.h\>|  
|`_swprintf_p`, `_swprintf_p_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_sprintf_p.c  
// This program uses _sprintf_p to format various  
// data and place them in the string named buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
    char     buffer[200],  
            s[] = "computer", c = 'l';  
    int      i = 35,  
            j;  
    float    fp = 1.7320534f;  
  
    // Format and print various data:   
    j  = _sprintf_p( buffer, 200,  
                     "   String:    %s\n", s );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Character: %c\n", c );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Integer:   %d\n", i );  
    j += _sprintf_p( buffer + j, 200 - j,   
                     "   Real:      %f\n", fp );  
  
    printf( "Output:\n%s\ncharacter count = %d\n",   
            buffer, j );  
}  
```  
  
  **Ausgabe:**  
 **Zeichenfolge:    Computer**  
 **Zeichen: l**  
 **Ganze Zahl:   35**  
 **Reelle Zahl:      1.732053**  
**Zeichenanzahl \= 79**   
## Beispiel  
  
```  
// crt_swprintf_p.c  
// This is the wide character example which  
// also demonstrates _swprintf_p returning  
// error code.  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    wchar_t buffer[BUFFER_SIZE];  
    int     len;  
  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%2$s %1$d",  
                      0, L" marbles in your head.");  
    _printf_p( "Wrote %d characters\n", len );  
  
    // _swprintf_p fails because string contains WEOF (\xffff)  
    len = _swprintf_p(buffer, BUFFER_SIZE, L"%s",   
                      L"Hello\xffff world" );  
    _printf_p( "Wrote %d characters\n", len );  
}  
```  
  
  **Umgeschrieben 24 Zeichen**  
**Umgeschrieben \-1 Zeichen**   
## .NET Framework-Entsprechung  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [\_fprintf\_p, \_fprintf\_p\_l, \_fwprintf\_p, \_fwprintf\_p\_l](../../c-runtime-library/reference/fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [\_printf\_p, \_printf\_p\_l, \_wprintf\_p, \_wprintf\_p\_l](../../c-runtime-library/reference/printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)   
 [printf\_p\-Positionsparameter](../../c-runtime-library/printf-p-positional-parameters.md)