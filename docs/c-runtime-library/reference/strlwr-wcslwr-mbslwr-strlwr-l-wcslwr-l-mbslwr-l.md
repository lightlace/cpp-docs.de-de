---
title: "_strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_strlwr_l"
  - "_strlwr"
  - "_wcslwr_l"
  - "_mbslwr_l"
  - "_wcslwr"
  - "_mbslwr"
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
  - "_strlwr"
  - "wcslwr_l"
  - "_ftcslwr"
  - "mbslwr_l"
  - "_mbslwr"
  - "_wcslwr"
  - "strlwr_l"
  - "_tcslwr"
  - "mbslwr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcslwr-Funktion"
  - "_mbslwr-Funktion"
  - "_mbslwr_l-Funktion"
  - "_strlwr-Funktion"
  - "_strlwr_l-Funktion"
  - "_tcslwr-Funktion"
  - "_tcslwr_l-Funktion"
  - "_wcslwr-Funktion"
  - "_wcslwr_l-Funktion"
  - "Groß- und Kleinschreibung, Konvertieren"
  - "Umwandeln von Groß-/Kleinschreibung"
  - "Umwandeln von Groß-/Kleinschreibung, CRT-Funktionen"
  - "ftcslwr-Funktion"
  - "mbslwr-Funktion"
  - "mbslwr_l-Funktion"
  - "Zeichenfolgenkonvertierung [C++], Groß- und Kleinschreibung"
  - "Zeichenfolgen [C++], Groß- und Kleinschreibung"
  - "Zeichenfolgen [C++], Umwandeln von Groß-/Kleinschreibung"
  - "strlwr_l-Funktion"
  - "tcslwr-Funktion"
  - "tcslwr_l-Funktion"
  - "wcslwr_l-Funktion"
ms.assetid: d279181d-2e7d-401f-ab44-6e7c2786a046
caps.latest.revision: 36
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 36
---
# _strlwr, _wcslwr, _mbslwr, _strlwr_l, _wcslwr_l, _mbslwr_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konvertiert eine Zeichenfolge in Kleinbuchstaben.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md).  
  
> [!IMPORTANT]
>  `_mbslwr` und `_mbslwr_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *_strlwr(  
   char * str  
);  
wchar_t *_wcslwr(  
   wchar_t * str  
);  
unsigned char *_mbslwr(  
   unsigned char * str  
);  
char *_strlwr_l(  
   char * str,  
   _locale_t locale  
);  
wchar_t *_wcslwr_l(  
   wchar_t * str,  
   _locale_t locale  
);  
unsigned char *_mbslwr_l(  
   unsigned char * str,  
   _locale_t locale   
);  
template <size_t size>  
char *_strlwr(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wcslwr(  
   wchar_t (&str)[size]  
); // C++ only  
template <size_t size>  
unsigned char *_mbslwr(  
   unsigned char (&str)[size]  
); // C++ only  
template <size_t size>  
char *_strlwr_l(  
   char (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
wchar_t *_wcslwr_l(  
   wchar_t (&str)[size],  
   _locale_t locale  
); // C++ only  
template <size_t size>  
unsigned char *_mbslwr_l(  
   unsigned char (&str)[size],  
   _locale_t locale   
); // C++ only  
```  
  
#### Parameter  
 `str`  
 In Kleinbuchstaben zu konvertierende auf NULL abschließende Zeichenfolge.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## Rückgabewert  
 Jede dieser Funktionen gibt einen Zeiger auf die konvertierte Zeichenfolge zurück.  Da die Änderung an der jeweiligen Stelle ausgeführt wurde, gleicht der zurückgegebene Zeiger dem als das Eingabeargument übergebenen Zeiger.  Kein Rückgabewert ist zur Fehleranzeige reserviert.  
  
## Hinweise  
 Die `_strlwr` \-Funktion konvertiert alle Großbuchstaben in `str` in Kleinbuchstaben, wie durch die `LC_CTYPE`\-Kategorieeinstellung des Gebietsschemas bestimmt.  Andere Zeichen sind nicht betroffen.  Weitere Informationen zu `LC_CTYPE` finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für ihr vom Gebietsschema abhängiges Verhalten; die Versionen mit dem `_l` \-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Die Funktionen `_wcslwr` und `_mbslwr` sind Breitzeichen\- und Multibytezeichenversionen von `_strlwr`.  Das Argument und der Rückgabewert von `_wcslwr` sind Breitzeichen\-Zeichenfolgen, die von `_mbslwr` sind Multibyte\-Zeichenfolgen.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Wenn `str` ein `NULL`\-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen die ursprüngliche Zeichenfolge zurück und legen `errno` auf `EINVAL` fest.  
  
 In C\+\+ haben diese Funktionen Vorlagenüberladungen, mit denen die neueren, sicheren Entsprechungen dieser Funktionen aufgerufen werden.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcslwr`|`_strlwr`|`_mbslwr`|`_wcslwr`|  
|`_tcslwr_l`|`_strlwr_l`|`_mbslwr_l`|`_wcslwr_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strlwr`, `_strlwr_l`|\<string.h\>|  
|`_wcslwr`, `_wcslwr_l`|\<string.h\> oder \<wchar.h\>|  
|`_mbslwr`, `_mbslwr_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strlwr.c  
// compile with: /W3  
// This program uses _strlwr and _strupr to create  
// uppercase and lowercase copies of a mixed-case string.  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The String to End All Strings!";  
   char * copy1 = _strdup( string ); // make two copies  
   char * copy2 = _strdup( string );  
  
   _strlwr( copy1 ); // C4996  
   // Note: _strlwr is deprecated; consider using _strlwr_s instead  
   _strupr( copy2 ); // C4996  
   // Note: _strupr is deprecated; consider using _strupr_s instead  
  
   printf( "Mixed: %s\n", string );  
   printf( "Lower: %s\n", copy1 );  
   printf( "Upper: %s\n", copy2 );  
  
   free( copy1 );  
   free( copy2 );  
}  
```  
  
  **Gemischt: Die Zeichenfolge zum Beenden aller Zeichenfolgen\!**  
**Kleinbuchstaben: die zeichenfolge zum beenden aller zeichenfolgen\!**  
**Großbuchstaben: DIE ZEICHENFOLGE ZUM BEENDEN ALLER ZEICHENFOLGEN\!**   
## .NET Framework-Entsprechung  
 [System::String::ToLower](https://msdn.microsoft.com/en-us/library/system.string.tolower.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)