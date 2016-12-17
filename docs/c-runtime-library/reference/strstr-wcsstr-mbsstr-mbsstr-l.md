---
title: "strstr, wcsstr, _mbsstr, _mbsstr_l"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbsstr"
  - "wcsstr"
  - "_mbsstr_l"
  - "strstr"
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
apitype: "DLLExport"
f1_keywords: 
  - "_fstrstr"
  - "_ftcsstr"
  - "strstr"
  - "wcsstr"
  - "_mbsstr"
  - "_tcsstr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstrstr-Funktion"
  - "_ftcsstr-Funktion"
  - "_mbsstr-Funktion"
  - "_mbsstr_l-Funktion"
  - "_tcsstr-Funktion"
  - "fstrstr-Funktion"
  - "ftcsstr-Funktion"
  - "mbsstr-Funktion"
  - "mbsstr_l-Funktion"
  - "Zeichenfolgen [C++], Suchen"
  - "strstr-Funktion"
  - "Teilzeichenfolgen, Suchen"
  - "tcsstr-Funktion"
  - "wcsstr-Funktion"
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: 32
caps.handback.revision: "30"
ms.author: "corob"
manager: "ghogen"
---
# strstr, wcsstr, _mbsstr, _mbsstr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Zeiger auf das erste Vorkommen einer Suchzeichenfolge in einer Zeichenfolge zurück.  
  
> [!IMPORTANT]
>  `_mbsstr` und `_mbsstr_l` können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strstr(  
   const char *str,  
   const char *strSearch   
); // C only  
char *strstr(  
   char *str,  
   const char *strSearch   
); // C++ only  
const char *strstr(  
   const char *str,  
   const char *strSearch   
); // C++ only  
wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C only  
wchar_t *wcsstr(  
   wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
const wchar_t *wcsstr(  
   const wchar_t *str,  
   const wchar_t *strSearch   
); // C++ only  
unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C only  
unsigned char *_mbsstr(  
   unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
const unsigned char *_mbsstr(  
   const unsigned char *str,  
   const unsigned char *strSearch   
); // C++ only  
unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C only  
unsigned char *_mbsstr_l(  
   unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbsstr_l(  
   const unsigned char *str,  
   const unsigned char *strSearch,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `str`  
 Zu suchende mit NULL endende Zeichenfolge.  
  
 `strSearch`  
 Zu suchende mit NULL endende Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt einen Zeiger auf das erste Vorkommen von `strSearch` in `str` zurück, oder `NULL`, wenn `strSearch` in `str` nicht angezeigt wird.  Wenn `strSearch` auf eine Zeichenfolge der Länge 0 \(Null\) zeigt wird, gibt die Funktion `str` zurück.  
  
## Hinweise  
 Die `strstr`\-Funktion gibt einen Zeiger auf das erste Vorkommen von `strSearch` in `str` zurück.  Die Suche umfasst keine abschließenden Nullzeichen.  `wcsstr` ist die Breitzeichenversion von `strstr`, und `_mbsstr` ist die Multibytezeichenversion.  Die Argumente und der Rückgabewert von `wcsstr` sind Breitzeichen\-Zeichenfolgen; die von `_mbsstr` sind Mehrbyte\-Zeichenfolgen.  `_mbsstr` überprüft die eigenen Parameter.  Wenn `str` oder `strSearch` den Wert `NULL` aufweist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt `_mbsstr``errno` auf `EINVAL` fest und gibt 0 zurück.  `strstr` und `wcsstr` überprüfen ihre Parameter nicht.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
> [!IMPORTANT]
>  Diese Funktionen können eine Bedrohung aufgrund eines Pufferüberlaufproblems darstellen.  Pufferüberlaufprobleme können für Angriffe auf ein System eingesetzt werden, da sie die Ausführung von willkürlichem Code ermöglichen können, was zur einer unbefugten Ausweitung der Berechtigungen führen kann.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 In C akzeptieren diese Funktionen einen `const`\-Zeiger als erstes Argument.  In C\+\+ sind zwei Überladungen verfügbar.  Die Überladung, die einen Zeiger auf `const` akzeptiert, gibt einen Zeiger auf `const` zurück, und die Version, die einen Zeiger auf Nicht\-`const` akzeptiert, gibt einen Zeiger auf Nicht\-`const` zurück.  Das Makro \_CONST\_CORRECT\_OVERLOADS wird definiert, wenn sowohl die `const`\-Version als auch die Nicht\-`const`\-Version dieser Funktionen verfügbar sind.  Wenn Sie das Nicht\-`const`\-Verhalten für beide C\+\+\-Überladungen benötigen, definieren Sie das Symbol \_CONST\_RETURN.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen, die das `_l`\-Suffix nicht verwenden, verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**nicht verfügbar**|**nicht verfügbar**|`_mbsstr_l`|**nicht verfügbar**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strstr`|\<string.h\>|  
|`wcsstr`|\<string.h\> oder \<wchar.h\>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strstr.c  
  
#include <string.h>  
#include <stdio.h>  
  
char str[] =    "lazy";  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int  result;  
   printf( "String to be searched:\n   %s\n", string );  
   printf( "   %s\n   %s\n\n", fmt1, fmt2 );  
   pdest = strstr( string, str );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf( "%s found at position %d\n", str, result );  
   else  
      printf( "%s not found\n", str );  
}  
```  
  
  **Zu suchende Zeichenfolge:**  
 **Der schnelle braune Hund springt über den faulen Fuchs.**  
 **1         2         3         4         5**  
 **12345678901234567890123456789012345678901234567890**  
**faul an Position 36 gefunden**   
## .NET Framework-Entsprechung  
 [System::String::IndexOf](https://msdn.microsoft.com/en-us/library/system.string.indexof.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strcmp, wcscmp, \_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strpbrk, wcspbrk, \_mbspbrk, \_mbspbrk\_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic\_string::find](../Topic/basic_string::find.md)