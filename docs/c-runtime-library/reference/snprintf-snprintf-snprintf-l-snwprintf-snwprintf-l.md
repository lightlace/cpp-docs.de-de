---
title: "snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwprintf"
  - "_snprintf"
  - "_snprintf_l"
  - "_snwprintf_l"
  - "snprintf"
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
  - "_snprintf"
  - "snprintf_l"
  - "snwprintf_l"
  - "sntprintf"
  - "snprintf"
  - "_sntprintf"
  - "_sntprintf_l"
  - "sntprintf_l"
  - "snwprintf"
  - "_snprintf_l"
  - "_snwprintf"
  - "_snwprintf_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "snwprintf_l-Funktion"
  - "sntprintf_l-Funktion"
  - "snprintf_l-Funktion"
  - "_snwprintf_l-Funktion"
  - "_sntprintf_l-Funktion"
  - "_snwprintf-Funktion"
  - "_snprintf-Funktion"
  - "_sntprintf-Funktion"
  - "_snprintf_l-Funktion"
  - "snwprintf-Funktion"
  - "snprintf-Funktion"
  - "sntprintf-Funktion"
  - "Formatierter Text [C++]"
ms.assetid: 5976c9c8-876e-4ac9-a515-39f3f7fd0925
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt formatierte Daten in eine Zeichenfolge. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).  
  
## Syntax  
  
```  
int snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf(  
   char *buffer,  
   size_t count,  
   const char *format [,  
   argument] ...   
);  
int _snprintf_l(  
   char *buffer,  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _snwprintf(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
);  
int _snwprintf_l(  
   wchar_t *buffer,  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
template <size_t size>  
int _snprintf(  
   char (&buffer)[size],  
   size_t count,  
   const char *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snprintf_l(  
   char (&buffer)[size],  
   size_t count,  
   const char *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format [,  
   argument] ...   
); // C++ only  
template <size_t size>  
int _snwprintf_l(  
   wchar_t (&buffer)[size],  
   size_t count,  
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
); // C++ only  
```  
  
#### Parameter  
 `buffer`  
 Speicherort für die Ausgabe.  
  
 `count`  
 Die maximale Anzahl der zu speichernden Zeichen.  
  
 `format`  
 Formatsteuerzeichenfolge.  
  
 `argument`  
 Optionale Argumente.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
 Weitere Informationen finden Sie unter [Syntax der Formatangabe: printf\- und wprintf\-Funktionen](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## Rückgabewert  
 Zulassen, dass `len` die Länge der formatierten Datenzeichenfolge ist, ausschließlich der abschließenden 0 \(null\).`len` und `count` sind Bytes für `snprintf` und `_snprintf`, Breitzeichen für `_snwprintf`.  
  
 Für alle Funktionen gilt: Wenn `len` \< `count`, werden `len`\-Zeichen in `buffer` gespeichert, wird ein NULL\-Terminator angefügt, und wird `len` zurückgegeben.  
  
 Wenn `len` größer als oder gleich `count` ist, schneidet die `snprintf`\-Funktion die Ausgabe ab, indem ein NULL\-Terminators an `buffer[count-1]` platziert wird. Der zurückgegebene Wert ist `len`, die Anzahl der Zeichen, die ausgegeben worden wären, wenn `count` groß genug wäre. Die `snprintf`\-Funktion gibt einen negativen Wert zurück, wenn ein Codierungsfehler auftritt.  
  
 Für alle Funktionen anderen Funktionen als `snprintf` gilt: Wenn `len` \= `count`, werden `len` Zeichen in `buffer` gespeichert, wird kein NULL\-Terminator angefügt, und wird `len` zurückgegeben. Wenn `len` \> `count`, `count`\-Zeichen in `buffer` gespeichert werden, wird kein NULL\-Terminator angefügt, und ein negativer Wert wird zurückgegeben.  
  
 Wenn `buffer` ein NULL\-Zeiger ist und `count` NULL ist, wird `len` als Anzahl der Zeichen zurückgegeben, die zur Formatierung der Ausgabe erforderlich sind, ausschließlich der abschließenden NULL. Um einen erfolgreichen Aufruf mit denselben `argument`\- und `locale`\-Parametern durchzuführen, ordnen Sie einen Puffer zu, der mindestens `len` \+ 1 Zeichen enthält.  
  
 Wenn `buffer` ein NULL\-Zeiger ist und `count` ungleich NULL ist oder wenn `format` ein NULL\-Zeiger ist, wird der ungültige Parameterhandler ausgelöst, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen "– 1" zurück und legen `errno` auf `EINVAL` fest.  
  
 Informationen zu diesen und anderen Fehlercodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Hinweise  
 Die `snprintf`\-Funktion und die `_snprintf`\-Funktionsfamilie formatieren und speichern `count` oder weniger Zeichen in `buffer`. Die `snprintf`\-Funktion speichert immer ein abschließendes NULL\-Zeichen, das die Ausgabe bei Bedarf abschneidet. Die `_snprintf`\-Funktionsfamilie fügt ein abschließendes NULL\-Zeichen nur an, wenn die Länge der formatierten Zeichenfolge streng genommen weniger als `count` Zeichen ist. Jedes `argument` \(falls vorhanden\) wird entsprechend der jeweiligen Formatangabe in `format` konvertiert und ausgegeben. Das Format besteht aus normalen Zeichen und hat die gleiche Form und Funktion wie das `format`\-Argument für [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md). Wenn der Kopiervorgang zwischen Zeichenfolgen ausgeführt wird, die sich überschneiden, ist das Verhalten nicht definiert.  
  
> [!IMPORTANT]
>  Stellen Sie sicher, dass `format` keine benutzerdefinierte Zeichenfolge ist. Da die `_snprintf`\-Funktionen keine NULL\-Terminierung garantieren, achten Sie insbesondere bei einem Rückgabewert von `count` darauf, dass ihnen Code folgt, der den NULL\-Terminator hinzufügt. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Beginnend mit der UCRT in Visual Studio 2015 und Windows 10 ist `snprintf` nicht mehr identisch mit `_snprintf`. Das Verhalten der `snprintf`\-Funktion ist jetzt mit dem Standard C99 konform.  
  
 `_snwprintf` ist eine Breitzeichen\-Version von `_snprintf`. Die Zeigerargumente zu `_snwprintf` sind Breitzeichen\-Zeichenfolgen. Die Erkennung von Codierungsfehlern in `_snwprintf` unterscheidet sich möglicherweise von der in `_snprintf`.`_snwprintf` genauso wie `swprintf` schreibt die Ausgabe in eine Zeichenfolge anstatt in ein Ziel vom Typ `FILE`.  
  
 Die Versionen dieser Funktionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch den Gebietsschemaparameter, der anstelle des aktuellen Threadgebietsschemas übergeben wurde.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden. Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_sntprintf`|`_snprintf`|`_snprintf`|`_snwprintf`|  
|`_sntprintf_l`|`_snprintf_l`|`_snprintf_l`|`_snwprintf_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`snprintf`, `_snprintf`,  `_snprintf_l`|\<stdio.h\>|  
|`_snwprintf`, `_snwprintf_l`|\<stdio.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```c  
// crt_snprintf.c  
// compile with: /W3  
#include <stdio.h>  
#include <stdlib.h>  
  
#if !defined(__cplusplus)  
typedef int bool;  
const bool true = 1;  
const bool false = 0;  
#endif  
  
#define FAIL 0 // change to 1 and see what happens  
  
int main(void)  
{  
   char buffer[200];  
   const static char s[] = "computer"  
#if FAIL  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
"computercomputercomputercomputercomputercomputercomputercomputer"  
#endif  
   ;  
   const char c = 'l';   
   const int i = 35;  
#if FAIL  
   const double fp = 1e300; // doesn't fit in the buffer  
#else  
   const double fp = 1.7320534;  
#endif  
   /* !subtract one to prevent "squeezing out" the terminal nul! */  
   const int bufferSize = sizeof(buffer)/sizeof(buffer[0]) - 1;  
   int bufferUsed = 0;  
   int bufferLeft = bufferSize - bufferUsed;  
   bool bSuccess = true;  
   buffer[0] = 0;  
  
   /* Format and print various data: */  
  
   if (bufferLeft > 0)  
   {  
      int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
      bufferLeft, "   String: %s\n", s ); // C4996  
      // Note: _snprintf is deprecated; consider _snprintf_s instead  
      if (bSuccess = (perElementBufferUsed >= 0))  
      {  
         bufferUsed += perElementBufferUsed;  
         bufferLeft -= perElementBufferUsed;  
         if (bufferLeft > 0)  
         {  
            int perElementBufferUsed = _snprintf(&buffer[bufferUsed],   
            bufferLeft, "   Character: %c\n", c ); // C4996  
            if (bSuccess = (perElementBufferUsed >= 0))  
            {  
               bufferUsed += perElementBufferUsed;  
               bufferLeft -= perElementBufferUsed;  
               if (bufferLeft > 0)  
               {  
                  int perElementBufferUsed = _snprintf(&buffer  
                  [bufferUsed], bufferLeft, "   Integer: %d\n", i ); // C4996  
                  if (bSuccess = (perElementBufferUsed >= 0))  
                  {  
                     bufferUsed += perElementBufferUsed;  
                     bufferLeft -= perElementBufferUsed;  
                     if (bufferLeft > 0)  
                     {  
                        int perElementBufferUsed = _snprintf(&buffer  
                        [bufferUsed], bufferLeft, "   Real: %f\n", fp ); // C4996  
                        if (bSuccess = (perElementBufferUsed >= 0))  
                        {  
                           bufferUsed += perElementBufferUsed;  
                        }  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
  
   if (!bSuccess)  
   {  
      printf("%s\n", "failure");  
   }  
   else  
   {  
      /* !store nul because _snprintf doesn't necessarily (if the string   
       * fits without the terminal nul, but not with it)!  
       * bufferUsed might be as large as bufferSize, which normally is   
       * like going one element beyond a buffer, but in this case   
       * subtracted one from bufferSize, so we're ok.  
       */  
      buffer[bufferUsed] = 0;  
      printf( "Output:\n%s\ncharacter count = %d\n", buffer, bufferUsed );  
   }  
   return EXIT_SUCCESS;  
}  
```  
  
```Output  
Ausgabe: Zeichenfolge: Computer Zeichen: l Ganze Zahl: 35 Reelle Zahl: 1,732053 Zeichenanzahl = 69  
```  
  
## Siehe auch  
 [Stream\-E\/A](../../c-runtime-library/stream-i-o.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [vprintf\-Funktionen](../../c-runtime-library/vprintf-functions.md)