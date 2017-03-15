---
title: "strchr, wcschr, _mbschr, _mbschr_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "strchr"
  - "wcschr"
  - "_mbschr_l"
  - "_mbschr"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_ftcschr"
  - "strchr"
  - "wcschr"
  - "_tcschr"
  - "_mbschr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcschr-Funktion"
  - "_mbschr-Funktion"
  - "_mbschr_l-Funktion"
  - "_tcschr-Funktion"
  - "Zeichen [C++], Suchen in Zeichenfolgen"
  - "ftcschr-Funktion"
  - "mbschr-Funktion"
  - "mbschr_l-Funktion"
  - "strchr-Funktion"
  - "Zeichenfolgen [C++], Suchen"
  - "tcschr-Funktion"
  - "wcschr-Funktion"
ms.assetid: 2639905d-e983-43b7-b885-abef32cfac43
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# strchr, wcschr, _mbschr, _mbschr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sucht ein Zeichen in einer Zeichenfolge unter Verwendung des aktuellen Gebietsschemas oder einer angegebenen LC\_CTYPE\-Konvertierungszustandskategorie.  
  
> [!IMPORTANT]
>  `_mbschr` und `_mbschr_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strchr(  
   const char *str,  
   int c   
);  // C only  
char *strchr(  
   char * str,  
   int c   
); // C++ only  
const char *strchr(  
   const char * str,  
   int c   
); // C++ only  
wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcschr(  
   wchar_t *str,  
   wchar_t c   
);  // C++ only  
const wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
);  // C++ only  
unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbschr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only   
unsigned char *_mbschr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `str`  
 Mit NULL endende Quellzeichenfolge.  
  
 `c`  
 Zu suchende Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf das erste Vorkommen von `c` in `str` oder `NULL` zurück, wenn `c` nicht gefunden wurde.  
  
## Hinweise  
 Die `strchr`\-Funktion sucht das erste Vorkommen von `c` in `str` oder gibt `NULL` zurück, wenn `c` nicht gefunden wurde.  Das abschließende Nullzeichen ist in der Suche nicht enthalten.  
  
 `wcschr`, `_mbschr` und `_mbschr_l` sind Breitzeichen\- und Multibytezeichenversionen von `strchr`.  Die Argumente und der Rückgabewert von `wcschr` sind Breitzeichen\-Zeichenfolgen; die von `_mbschr` sind Mehrbyte\-Zeichenfolgen.  `_mbschr` erkennt Multibyte\-Zeichenfolgen.  Wenn darüber hinaus die Zeichenfolge ein NULL\-Zeiger ist, ruft `_mbschr` den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt `_mbschr``NULL` zurück und setzt `errno` auf `EINVAL`.  `strchr` und `wcschr` überprüfen ihre Parameter nicht.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Die Ausgabewert ist von der Einstellung der `LC_CTYPE`\-Kategorieeinstellung des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 In C akzeptieren diese Funktionen einen `const`\-Zeiger als erstes Argument.  In C\+\+ sind zwei Überladungen verfügbar.  Die Überladung, die einen Zeiger zu `const` akzeptiert, gibt einen Zeiger zu `const` zurück; die Version, die einen Zeiger auf Nicht\-`const` akzeptiert, gibt einen Zeiger auf Nicht\-`const` zurück.  Das Makro \_CONST\_CORRECT\_OVERLOADS wird definiert, wenn sowohl die `const`\-Version als auch die Nicht\-`const`\-Version dieser Funktionen verfügbar sind.  Wenn Sie das Nicht\-`const`\-Verhalten für beide C\+\+\-Überladungen benötigen, definieren Sie das Symbol \_CONST\_RETURN.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcschr`|`strchr`|`_mbschr`|`wcschr`|  
|**Nicht zutreffend**|**nicht verfügbar**|`_mbschr_l`|**nicht verfügbar**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strchr`|\<string.h\>|  
|`wcschr`|\<string.h\> oder \<wchar.h\>|  
|`_mbschr`, `_mbschr_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strchr.c  
//   
// This program illustrates searching for a character  
// with strchr (search forward) or strrchr (search backward).  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int  ch = 'r';  
  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
  
   printf_s( "String to be searched:\n      %s\n", string );  
   printf_s( "      %s\n      %s\n\n", fmt1, fmt2 );  
   printf_s( "Search char:   %c\n", ch );  
  
   // Search forward.   
   pdest = strchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   first %c found at position %d\n",   
              ch, result );  
   else  
      printf_s( "Result:   %c not found\n", ch );  
  
   // Search backward.   
   pdest = strrchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   last %c found at position %d\n", ch, result );  
   else  
      printf_s( "Result:\t%c not found\n", ch );  
}  
```  
  
  **Zu suchende Zeichenfolge:**  
 **Der schnelle braune Hund springt über den faulen Fuchs.**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**Search char:   r**  
**Result:   first r found at position 12**  
**Result:   last r found at position 30**   
## .NET Framework-Entsprechung  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strstr, wcsstr, \_mbsstr, \_mbsstr\_l](../../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)