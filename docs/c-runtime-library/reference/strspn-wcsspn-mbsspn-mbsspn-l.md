---
title: "strspn, wcsspn, _mbsspn, _mbsspn_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsspn_l"
  - "wcsspn"
  - "strspn"
  - "_mbsspn"
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
  - "_ftcsspn"
  - "wcsspn"
  - "_mbsspn"
  - "_tcsspn"
  - "strspn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ftcsspn-Funktion"
  - "_mbsspn-Funktion"
  - "_mbsspn_l-Funktion"
  - "_tcsspn-Funktion"
  - "ftcsspn-Funktion"
  - "mbsspn-Funktion"
  - "mbsspn_l-Funktion"
  - "Zeichenfolgen [C++], Suchen"
  - "strspn-Funktion"
  - "Teilzeichenfolgen, Suchen"
  - "tcsspn-Funktion"
  - "wcsspn-Funktion"
ms.assetid: d077284a-809f-4068-959e-c6d6262677eb
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# strspn, wcsspn, _mbsspn, _mbsspn_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Index des ersten Zeichens in einer Zeichenfolge zurück, die keinem Zeichensatz angehört.  
  
> [!IMPORTANT]
>  `_mbsspn` und `_mbsspn_l` können nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t strspn(  
   const char *str,  
   const char *strCharSet   
);  
size_t wcsspn(  
   const wchar_t *str,  
   const wchar_t *strCharSet   
);  
size_t _mbsspn(  
   const unsigned char *str,  
   const unsigned char *strCharSet   
);  
size_t _mbsspn_l(  
   const unsigned char *str,  
   const unsigned char *strCharSet,  
   _locale_t locale  
);  
```  
  
#### Parameter  
 `str`  
 Zu suchende mit NULL endende Zeichenfolge.  
  
 `strCharSet`  
 Mit NULL endender Zeichensatz.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt einen ganzzahligen Wert zurück, der die Länge der untergeordneten Zeichenfolge in `str` angibt, die vollständig aus Zeichen in `strCharSet`*besteht.* Wenn `str` mit einem Zeichen beginnt, das nicht in `strCharSet` *enthalten ist,* gibt die Funktion 0 \(null\) zurück.  
  
## Hinweise  
 Die `strspn`\-Funktion gibt den Index des ersten Zeichens in `str` zurück, das nicht dem Zeichensatz in `strCharSet` angehört.  Die Suche umfasst keine abschließenden Nullzeichen.  
  
 `wcsspn` und `_mbsspn` sind Breitzeichen\- und Multibytezeichenversionen von `strspn`**.** Die Argumente von `wcsspn` sind Breitzeichen\-Zeichenfolgen, die von `_mbsspn` sind Multibyte\-Zeichenfolgen.  `_mbsspn` überprüft die eigenen Parameter.  Wenn `str` oder `strCharSet``NULL` ist, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, legt `_mbspn``errno` auf `EINVAL` fest und gibt 0 zurück.  `strspn` und `wcsspn` überprüfen ihre Parameter nicht.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsspn`|`strspn`|`_mbsspn`|`wcsspn`|  
|**nicht verfügbar**|**nicht verfügbar**|`_mbsspn_l`|**nicht verfügbar**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strspn`|\<string.h\>|  
|`wcsspn`|\<string.h\> oder \<wchar.h\>|  
|`_mbsspn`, `_mbsspn_l`|\<mbstring.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strspn.c  
// This program uses strspn to determine  
// the length of the segment in the string "cabbage"  
// consisting of a's, b's, and c's. In other words,  
// it finds the first non-abc letter.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[] = "cabbage";  
   int  result;  
   result = strspn( string, "abc" );  
   printf( "The portion of '%s' containing only a, b, or c "  
           "is %d bytes long\n", string, result );  
}  
```  
  
  **Der Teil von "cabbage", der nur a, b oder c enthält, ist 5 Bytes lang**   
## .NET Framework-Entsprechung  
 [System::String::Substring](https://msdn.microsoft.com/en-us/library/system.string.substring.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_strspnp, \_wcsspnp, \_mbsspnp, \_mbsspnp\_l](../../c-runtime-library/reference/strspnp-wcsspnp-mbsspnp-mbsspnp-l.md)   
 [strcspn, wcscspn, \_mbscspn, \_mbscspn\_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, \_mbsncmp, \_mbsncmp\_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [\_strnicmp, \_wcsnicmp, \_mbsnicmp, \_strnicmp\_l, \_wcsnicmp\_l, \_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, \_mbsrchr, \_mbsrchr\_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)