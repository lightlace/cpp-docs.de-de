---
title: "strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l"
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
  - "_mbslen"
  - "_mbslen_l"
  - "_mbstrlen"
  - "wcslen"
  - "_mbstrlen_l"
  - "strlen"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mbstrlen"
  - "wcslen"
  - "_tcslen"
  - "_ftcslen"
  - "strlen"
  - "_mbslen"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcslen-Funktion"
  - "_mbslen-Funktion"
  - "_mbslen_l-Funktion"
  - "_mbstrlen-Funktion"
  - "_mbstrlen_l-Funktion"
  - "_tcslen-Funktion"
  - "ftcslen-Funktion"
  - "Längen, Zeichenfolgen"
  - "mbslen-Funktion"
  - "mbslen_l-Funktion"
  - "mbstrlen-Funktion"
  - "mbstrlen_l-Funktion"
  - "Zeichenfolgenlänge, Abrufen"
  - "Zeichenfolgen [C++], Abrufen der Länge"
  - "strlen-Funktion"
  - "tcslen-Funktion"
  - "wcslen-Funktion"
ms.assetid: 16462f2a-1e0f-4eb3-be55-bf1c83f374c2
caps.latest.revision: 32
caps.handback.revision: "30"
ms.author: "corob"
manager: "ghogen"
---
# strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Länge einer Zeichenfolge mithilfe des aktuellen Gebietsschemas oder einem angegebenen Gebietsschema ab.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [strnlen, strnlen\_s, wcsnlen, wcsnlen\_s, \_mbsnlen, \_mbsnlen\_l, \_mbstrnlen, \_mbstrnlen\_l](../../c-runtime-library/reference/strnlen-strnlen-s.md).  
  
> [!IMPORTANT]
>  `_mbslen`, `_mbslen_l`, `_mbstrlen` und `_mbstrlen_l` können nicht in Anwendungen eingesetzt werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t strlen(    const char *str ); size_t wcslen(    const wchar_t *str  ); size_t _mbslen(    const unsigned char *str  ); size_t _mbslen_l(    const unsigned char *str,    _locale_t locale ); size_t _mbstrlen(    const char *str ); size_t _mbstrlen_l(    const char *str,    _locale_t locale );  
```  
  
#### Parameter  
 `str`  
 Mit NULL endende Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt die Anzahl der Zeichen in `str` zurück, ohne das abschließende `NULL`\-Zeichen.  Es ist kein Rückgabewert zur Fehleranzeige reserviert, mit Ausnahme von `_mbstrlen` und `_mbstrlen_l`, die `((size_t)(-1))` zurückgeben, wenn die Zeichenfolge ein ungültiges Multibytezeichen enthält.  
  
## Hinweise  
 `strlen` interpretiert die Zeichenfolge als Einzelbytezeichenfolge, sodass der Rückgabewert immer der Anzahl von Bytes entspricht, selbst wenn die Zeichenfolge Multibytezeichen enthält.  `wcslen` ist eine Breitzeichenversion von `strlen`. Das Argument von `wcslen` ist eine Zeichenfolge mit Breitzeichen, und die Anzahl von Zeichen wird in \(2\-Byte\-\)Breitzeichen angegeben.  `wcslen` und `strlen` verhalten sich andernfalls identisch.  
  
 **Sicherheitshinweis** Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar.  Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE und \_MBCS nicht definiert.|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|-------------------------------------------|----------------------|-------------------------|  
|`_tcslen`|`strlen`|`strlen`|`wcslen`|  
|`_tcsclen`|`strlen`|`_mbslen`|`wcslen`|  
|`_tcsclen_l`|`strlen`|`_mbslen_l`|`wcslen`|  
  
 `_mbslen` und `_mbslen_l` geben die Anzahl von Multibytezeichen in einer Multibyte\-Zeichenfolge zurück, überprüfen jedoch nicht die Gültigkeit der Multibytezeichen.  `_mbstrlen` und `_mbstrlen_l` überprüfen die Gültigkeit von Multibytezeichen und erkennen Multibyte\-Zeichenfolgen.  Wenn die an `_mbstrlen` oder `_mbstrlen_l` übergebene Zeichenfolge ein ungültiges Multibytezeichen für die Codepage enthält, gibt sie "– 1" zurück und legt `errno` auf `EILSEQ` fest.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strlen`|\<string.h\>|  
|`wcslen`|\<string.h\> oder \<wchar.h\>|  
|`_mbslen`, `_mbslen_l`|\<mbstring.h\>|  
|`_mbstrlen`, `_mbstrlen_l`|\<stdlib.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strlen.c  
// Determine the length of a string. For the multi-byte character  
// example to work correctly, the Japanese language support for  
// non-Unicode programs must be enabled by the operating system.  
  
#include <string.h>  
#include <locale.h>  
  
int main()  
{  
   char* str1 = "Count.";  
   wchar_t* wstr1 = L"Count.";  
   char * mbstr1;  
   char * locale_string;  
  
   // strlen gives the length of single-byte character string  
   printf("Length of '%s' : %d\n", str1, strlen(str1) );  
  
   // wstrlen gives the length of a wide character string  
   wprintf(L"Length of '%s' : %d\n", wstr1, wcslen(wstr1) );  
  
   // A multibyte string: [A] [B] [C] [katakana A] [D] [\0]  
   // in Code Page 932. For this example to work correctly,  
   // the Japanese language support must be enabled by the  
   // operating system.  
   mbstr1 = "ABC" "\x83\x40" "D";  
  
   locale_string = setlocale(LC_CTYPE, "Japanese_Japan");  
  
   if (locale_string == NULL)  
   {  
      printf("Japanese locale not enabled. Exiting.\n");  
      exit(1);  
   }  
   else  
   {  
      printf("Locale set to %s\n", locale_string);  
   }  
  
   // _mbslen will recognize the Japanese multibyte character if the  
   // current locale used by the operating system is Japanese  
   printf("Length of '%s' : %d\n", mbstr1, _mbslen(mbstr1) );  
  
   // _mbstrlen will recognize the Japanese multibyte character  
   // since the CRT locale is set to Japanese even if the OS locale  
   // isnot.   
   printf("Length of '%s' : %d\n", mbstr1, _mbstrlen(mbstr1) );  
   printf("Bytes in '%s' : %d\n", mbstr1, strlen(mbstr1) );     
  
}  
```  
  
  **Länge von "Anzahl". : 6**  
**Länge von "Anzahl". : 6**  
**Länge von "ABCァD" : 5**  
**Länge von "ABCァD" : 5**  
**Bytes in "ABCァD" : 6**   
## .NET Framework-Entsprechung  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcat, wcscat, \_mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll\-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)