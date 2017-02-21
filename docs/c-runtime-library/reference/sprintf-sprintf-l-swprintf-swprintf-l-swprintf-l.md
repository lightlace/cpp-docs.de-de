---
title: "sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__swprintf_l"
  - "sprintf"
  - "_sprintf_l"
  - "_swprintf_l"
  - "swprintf"
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
  - "ntdll.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_stprintf_l"
  - "__swprintf_l"
  - "sprintf_l"
  - "swprintf"
  - "_sprintf_l"
  - "sprintf"
  - "_stprintf"
  - "stprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__swprintf_l-Funktion"
  - "_CRT_NON_CONFORMING_SWPRINTFS"
  - "_sprintf_l-Funktion"
  - "_stprintf-Funktion"
  - "_stprintf_l-Funktion"
  - "_swprintf_l-Funktion"
  - "Formatierter Text [C++]"
  - "sprintf-Funktion"
  - "sprintf_l-Funktion"
  - "stprintf-Funktion"
  - "stprintf_l-Funktion"
  - "Zeichenfolgen [C++], Schreiben in"
  - "swprintf-Funktion"
  - "swprintf_l-Funktion"
ms.assetid: f6efe66f-3563-4c74-9455-5411ed939b81
caps.latest.revision: 36
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 36
---
# sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreiben Sie formatierte Daten in eine Zeichenfolge.  Sicherere Versionen einiger dieser Funktionen sind verfügbar; siehe [sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md).  Die sicheren Versionen von `swprintf` und `_swprintf_l` akzeptieren keinen `count`\-Parameter.  
  
## Syntax  
  
```  
int sprintf(  
   char *buffer,  
   const char *format [,  
   argument] ...   
);  
int _sprintf_l(  
   char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int swprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument]...  
);  
int _swprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
int __swprintf_l(  
   wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int sprintf(  
   char (&buffer)[size],  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _sprintf_l(  
   char (&buffer)[size],  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für die Ausgabe  
  
 `count`  
 Maximale Anzahl, der in der Unicode\-Version dieser Funktion zu speichernde Zeichen.  
  
 `format`  
 Formatsteuerzeichenfolge  
  
 `argument`  
 Optionale Argumente  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Formatangaben](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 Die Anzahl geschriebener Zeichen oder "– 1" bei einem Fehler.  Wenn `buffer` oder `format` ein NULL\-Zeiger ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 `sprintf` gibt die in `buffer` gespeicherte Byteanzahl zurück. Das beendende NULL\-Zeichen wird dabei nicht mitgezählt.  `swprintf`gibt die Anzahl der in `buffer` gespeicherten Breitzeichen zurück. Das beendende NULL\-Breitzeichen wird dabei nicht mitgezählt.  
  
## Hinweise  
 Die `sprintf`\-Funktion formatiert und speichert eine Reihe von Zeichen und Werte in `buffer`.  Jedes `argument` \(falls vorhanden\) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert und ausgegeben.  Das Format besteht aus normalen Zeichen und hat die gleiche Form und Funktion wie das `format`\-Argument für [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  Ein NULL\-Zeichen wird nach dem letzten geschriebenen Zeichen angefügt.  Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
> [!IMPORTANT]
>  Bei der Verwendung von `sprintf` gibt es keine Möglichkeit, die Anzahl der geschriebenen Zeichen einzuschränken. Demnach ist Code mit `sprintf` für Pufferüberläufe anfällig.  Erwägen Sie die Verwendung der verwandten Funktion [\_snprintf](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), die eine Maximalzahl für Zeichen angibt, die an `buffer` geschrieben werden können, oder verwenden Sie [\_scprintf](../../c-runtime-library/reference/scprintf-scprintf-l-scwprintf-scwprintf-l.md), um die Größe des erforderlichen Puffers zu bestimmen.  Stellen Sie zudem sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist.  
  
 `swprintf` ist eine Breitzeichen\-Version von `sprintf`. Die Zeigerargumente zu `swprintf` sind Breitzeichen\-Zeichenfolgen.  Die Erkennung von Codierungsfehlern in `swprintf` unterscheidet sich möglicherweise von der in `sprintf`.  `swprintf` und `fwprintf` verhalten sich identisch, außer dass die Ausgabe von `swprintf` in eine Zeichenfolge anstatt an ein Ziel des `FILE`\-Typs schreibt, und dass `swprintf` den `count`\-Parameter zur Angabe der maximale Anzahl zu schreibender Zeichen erfordert.  Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den ihnen übergebenen Gebietsschemaparameter anstelle des aktuellen Threadgebietsschemas.  
  
 `swprintf` ist zum ISO\-C\-Standard konform. Dieser erfordert den zweiten Parameter `count` des `size_t`\-Typs.  Um das alte, nicht dem Standard entsprechende, Verhalten zu erzwingen, definieren Sie `_CRT_NON_CONFORMING_SWPRINTFS`.  In einer zukünftigen Version wird das alte Verhalten möglicherweise entfernt. Daher sollte Code so geändert werden, dass das neue konforme Verhalten verwendet wird.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_stprintf`|`sprintf`|`sprintf`|`_swprintf`|  
|`_stprintf_l`|`_sprintf_l`|`_sprintf_l`|`__swprintf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`sprintf`, `_sprintf_l`|\<stdio.h\>|  
|`swprintf`, `_swprintf_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
```  
// crt_sprintf.c  
// compile with: /W3  
// This program uses sprintf to format various  
// data and place them in the string named buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  buffer[200], s[] = "computer", c = 'l';  
   int   i = 35, j;  
   float fp = 1.7320534f;  
  
   // Format and print various data:   
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996  
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996  
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996  
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996  
   // Note: sprintf is deprecated; consider using sprintf_s instead  
  
   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );  
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
// crt_swprintf.c  
// wide character example  
// also demonstrates swprintf returning error code  
#include <stdio.h>  
  
int main( void )  
{  
   wchar_t buf[100];  
   int len = swprintf( buf, 100, L"%s", L"Hello world" );  
   printf( "wrote %d characters\n", len );  
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );  
   // swprintf fails because string contains WEOF (\xffff)  
   printf( "wrote %d characters\n", len );  
}  
```  
  
  **11 Zeichen geschrieben**  
**\-1 Zeichen geschrieben**   
## .NET Framework-Entsprechung  
 [System::String::Format](https://msdn.microsoft.com/en-us/library/system.string.format.aspx)  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)