---
title: "strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l"
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
  - "_mbspbrk"
  - "wcspbrk"
  - "_mbspbrk_l"
  - "strpbrk"
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
  - "_fstrpbrk"
  - "_mbspbrk"
  - "strpbrk"
  - "_tcspbrk"
  - "_ftcspbrk"
  - "wcspbrk"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fstrpbrk-Funktion"
  - "_ftcspbrk-Funktion"
  - "_mbspbrk-Funktion"
  - "_mbspbrk_l-Funktion"
  - "_tcspbrk-Funktion"
  - "Zeichensätze [C++], Überprüfen der Zeichenfolgen auf Zeichen"
  - "Zeichen [C++], Überprüfen von Zeichenfolgen"
  - "fstrpbrk-Funktion"
  - "ftcspbrk-Funktion"
  - "mbspbrk-Funktion"
  - "mbspbrk_l-Funktion"
  - "Zeichenfolgen [C++], Scannen"
  - "strpbrk-Funktion"
  - "tcspbrk-Funktion"
  - "wcspbrk-Funktion"
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: 30
caps.handback.revision: "28"
ms.author: "corob"
manager: "ghogen"
---
# strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durchsucht Zeichenfolgen nach Zeichen in angegebenen Zeichensätzen.  
  
> [!IMPORTANT]
>  `_mbspbrk` und `_mbspbrk_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C only  
char *strpbrk(  
   char *str,  
   const char *strCharSet   
); // C++ only  
const char *strpbrk(  
   const char *str,  
   const char *strCharSet   
); // C++ only  
wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C only  
wchar_t *wcspbrk(  
   wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
const wchar_t *wcspbrk(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
); // C++ only  
unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C only  
unsigned char *_mbspbrk(  
   unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
const unsigned char *_mbspbrk(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
); // C++ only  
unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C only  
unsigned char *_mbspbrk_l(  
   unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbspbrk_l(  
   const unsigned char *str,  
   const unsigned char* strCharSet,  
   _locale_t locale  
); // C++ only  
```  
  
#### Parameter  
 `str`  
 Auf NULL endende gesuchte Zeichenfolge.  
  
 `strCharSet`  
 Mit NULL endender Zeichensatz.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt einen Zeiger auf das erste Vorkommen eines beliebigen Zeichens von `strCharSet` in `str` zurück oder einen `NULL`\-Zeiger, wenn zwei Zeichenfolgenargumente über kein gemeinsames Zeichen verfügen.  
  
## Hinweise  
 Die `strpbrk`\-Funktion gibt einen Zeiger auf das erste Vorkommen eines Zeichens in `str` zurück, das zu dem Zeichensatz in `strCharSet` gehört.  Die Suche umfasst nicht das abschließende Nullzeichen.  
  
 `wcspbrk` und `_mbspbrk` sind Breitzeichen\- und Multibytezeichenversionen von `strpbrk`.  Die Argumente und der Rückgabewert von `wcspbrk` sind Breitzeichen\-Zeichenfolgen; die von `_mbspbrk` sind Mehrbyte\-Zeichenfolgen.  
  
 `_mbspbrk` überprüft die eigenen Parameter.  Wenn `str` oder `strCharSet` den Wert `NULL` aufweisen, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt `_mbspbrk``NULL` zurück und setzt `errno` auf `EINVAL`.  `strpbrk` und `wcspbrk` überprüfen ihre Parameter nicht.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 `_mbspbrk` ähnelt `_mbscspn`, außer dass `_mbspbrk` einen Zeiger anstelle eines Werts vom Typ [size\_t](../../c-runtime-library/standard-types.md) zurückgibt.  
  
 In C akzeptieren diese Funktionen einen `const`\-Zeiger als erstes Argument.  In C\+\+ sind zwei Überladungen verfügbar.  Die Überladung, die einen Zeiger zu `const` akzeptiert, gibt einen Zeiger zu `const` zurück; die Version, die einen Zeiger auf Nicht\-`const` akzeptiert, gibt einen Zeiger auf Nicht\-`const` zurück.  Das Makro \_CONST\_CORRECT\_OVERLOADS wird definiert, wenn sowohl die `const`\-Version als auch die Nicht\-`const`\-Version dieser Funktionen verfügbar sind.  Wenn Sie das Nicht\-`const`\-Verhalten für beide C\+\+\-Überladungen benötigen, definieren Sie das Symbol \_CONST\_RETURN.  
  
 Die Ausgabewert ist von der Einstellung der `LC_CTYPE`\-Kategorieeinstellung des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die Version mit dem `_l`\-Suffix ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**nicht verfügbar**|**nicht verfügbar**|`_mbspbrk_l`|**nicht verfügbar**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strpbrk`|\<string.h\>|  
|`wcspbrk`|\<string.h\> oder \<wchar.h\>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strpbrk.c  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";  
   char *result = NULL;  
  
   // Return pointer to first digit in "string".  
   printf( "1: %s\n", string );  
   result = strpbrk( string, "0123456789" );  
   printf( "2: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "3: %s\n", result++ );  
   result = strpbrk( result, "0123456789" );  
   printf( "4: %s\n", result );  
}  
```  
  
  **1: Die 3 Männer und 2 Jungen hatten 5 Schweine gegessen**  
**2: 3 Männer und 2 Jungen hatten 5 Schweine gegessen**  
**3: 2 Jungen hatten 5 Schweine gegessen**  
**4: 5 Schweine**   
## .NET Framework-Entsprechung  
 [System::String::IndexOfAny](https://msdn.microsoft.com/en-us/library/system.string.indexofany.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strchr, wcschr, \_mbschr, \_mbschr\_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)