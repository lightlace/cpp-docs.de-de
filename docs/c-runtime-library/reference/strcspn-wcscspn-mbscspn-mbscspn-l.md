---
title: "strcspn, wcscspn, _mbscspn, _mbscspn_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbscspn_l"
  - "wcscspn"
  - "_mbscspn"
  - "strcspn"
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
  - "strcspn"
  - "_mbscspn"
  - "wcscspn"
  - "_ftcscspn"
  - "_tcscspn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcscspn-Funktion"
  - "_mbscspn-Funktion"
  - "_mbscspn_l-Funktion"
  - "_tcscspn-Funktion"
  - "ftcscspn-Funktion"
  - "mbscspn-Funktion"
  - "mbscspn_l-Funktion"
  - "strcspn-Funktion"
  - "Zeichenfolgen [C++], Suchen"
  - "tcscspn-Funktion"
  - "wcscspn-Funktion"
ms.assetid: f73f51dd-b533-4e46-ba29-d05c553708a6
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# strcspn, wcscspn, _mbscspn, _mbscspn_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Index des ersten Vorkommens in einer Zeichenfolge eines Zeichens zurück, das zu einem Zeichensatz gehört.  
  
> [!IMPORTANT]
>  `_mbschr` und `_mbschr_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t strcspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcscspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbscspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbscspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Auf NULL endende gesuchte Zeichenfolge.  
  
 `strCharSet`  
 Mit NULL endender Zeichensatz.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Diese Funktionen geben den Index des ersten Zeichens in `str` zurück, das sich in `strCharSet` befindet.  Wenn sich keines der Zeichen in `str` in `strCharSet` befindet, entspricht der Rückgabewert der Länge von `str`.  
  
 Kein Rückgabewert ist zur Fehleranzeige reserviert.  
  
## Hinweise  
 `wcscspn` und `_mbscspn` sind Breitzeichen\- und Multibytezeichenversionen von `strcspn`.  Die Argumente von `wcscspn` sind Breitzeichen\-Zeichenfolgen, die von `_mbscspn` sind Multibyte\-Zeichenfolgen.  
  
 `_mbscspn` überprüft die eigenen Parameter.  Wenn entweder `str` oder `strCharSet` ein NULL\-Zeiger ist, wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, gibt die Funktion 0 zurück und stellt `errno` auf `EINVAL` ein.  `strcspn` und `wcscspn` überprüfen ihre Parameter nicht.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcscspn`|`strcspn`|`_mbscspn`|`wcscspn`|  
|`n/a`|`n/a`|`_mbscspn_l`|`n/a`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strcspn`|\<string.h\>|  
|`wcscspn`|\<string.h\> oder \<wchar.h\>|  
|`_mbscspn`, `_mbscspn_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strcspn.c  
  
#include <string.h>  
#include <stdio.h>  
  
void test( const char * str, const char * strCharSet )  
{  
   int pos = strcspn( str, strCharSet );  
   printf( "strcspn( \"%s\", \"%s\" ) = %d\n", str, strCharSet, pos );      
}  
  
int main( void )  
{  
   test( "xyzbxz", "abc" );  
   test( "xyzbxz", "xyz" );  
   test( "xyzbxz", "no match" );  
   test( "xyzbxz", "" );  
   test( "", "abc" );  
   test( "", "" );  
}  
```  
  
  **strcspn\( "xyzbxz", "abc" \) \= 3**  
**strcspn\( "xyzbxz", "xyz" \) \= 0**  
**strcspn\( "xyzbxz", "no match" \) \= 6**  
**strcspn\( "xyzbxz", "" \) \= 6**  
**strcspn\( "", "abc" \) \= 0**  
**strcspn\( "", "" \) \= 0**   
## .NET Framework-Entsprechung  
 [System::String::Substring](https://msdn.microsoft.com/en-us/library/system.string.substring.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, \_mbsspn, \_mbsspn\_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)