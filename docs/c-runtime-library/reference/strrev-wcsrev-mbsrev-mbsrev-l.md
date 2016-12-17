---
title: "_strrev, _wcsrev, _mbsrev, _mbsrev_l"
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
  - "_wcsrev"
  - "_mbsrev"
  - "_strrev"
  - "_mbsrev_l"
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
  - "_strrev"
  - "_ftcsrev"
  - "_tcsrev"
  - "mbsrev"
  - "mbsrev_l"
  - "_wcsrev_fstrrev"
  - "_mbsrev"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ftcsrev-Funktion"
  - "_mbsrev-Funktion"
  - "_mbsrev_l-Funktion"
  - "_strrev-Funktion"
  - "_tcsrev-Funktion"
  - "_wcsrev-Funktion"
  - "Zeichen [C++], Umkehren der Reihenfolge"
  - "Zeichen [C++], Wechsel"
  - "ftcsrev-Funktion"
  - "mbsrev-Funktion"
  - "mbsrev_l-Funktion"
  - "Umkehren von Zeichen in Zeichenfolgen"
  - "Zeichenfolgen [C++], Umkehren"
  - "strrev-Funktion"
  - "tcsrev-Funktion"
  - "wcsrev-Funktion"
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
caps.latest.revision: 25
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# _strrev, _wcsrev, _mbsrev, _mbsrev_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kehrt die Zeichen einer Zeichenfolge um.  
  
> [!IMPORTANT]
>  `_mbsrev` und `_mbsrev_l` können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
char *_strrev(  
   char *str   
);  
wchar_t *_wcsrev(  
   wchar_t *str   
);  
unsigned char *_mbsrev(  
   unsigned char *str   
);  
unsigned char *_mbsrev_l(  
   unsigned char *str,  
   _locale_t locale   
);  
```  
  
#### Parameter  
 `str`  
 Umzukehrende auf NULL endende Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 Gibt einen Zeiger zur geänderten Zeichenfolge zurück.  Kein Rückgabewert ist zur Fehleranzeige reserviert.  
  
## Hinweise  
 Die `_strrev`\-Funktion kehrt die Reihenfolge der Elemente in `string` um.  Das abschließende NULL\-Zeichen bleibt bestehen.  `_wcsrev` und `_mbsrev` sind Breitzeichen\- und Multibytezeichenversionen von `_strrev`.  Die Argumente und der Rückgabewert von `_wcsrev` sind Breitzeichen\-Zeichenfolgen; die von `_mbsrev` sind Mehrbyte\-Zeichenfolgen.  Bei `_mbsrev` wird die Reihenfolge von Bytes in jedem Multibytezeichen in `string` nicht geändert.  Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 `_mbsrev` überprüft die eigenen Parameter.  Wenn entweder `string1` oder `string2` ein NULL\-Zeiger ist, wird, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen.  Wenn die weitere Ausführung zugelassen wird, gibt `_mbsrev``NULL` zurück und setzt `errno` auf `EINVAL`.  `_strrev` und `_wcsrev` überprüfen ihre Parameter nicht.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, \_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`\-Suffix das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`\-Suffix den übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
> [!IMPORTANT]
>  Diese Funktionen sind möglicherweise für Pufferüberlaufrisiken anfällig.  Pufferüberläufe können für Systemangriffe eingesetzt werden, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcsrev`|`_strrev`|`_mbsrev`|`_wcsrev`|  
|**nicht verfügbar**|**nicht verfügbar**|`_mbsrev_l`|**nicht verfügbar**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_strrev`|\<string.h\>|  
|`_wcsrev`|\<string.h\> oder \<wchar.h\>|  
|`_mbsrev`, `_mbsrev_l`|\<mbstring.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_strrev.c  
// This program checks a string to see  
// whether it is a palindrome: that is, whether  
// it reads the same forward and backward.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* string = "Able was I ere I saw Elba";  
   int result;  
  
   // Reverse string and compare (ignore case):  
   result = _stricmp( string, _strrev( _strdup( string ) ) );  
   if( result == 0 )  
      printf( "The string \"%s\" is a palindrome\n", string );  
   else  
      printf( "The string \"%s\" is not a palindrome\n", string );  
}  
```  
  
  **Die Zeichenfolge "Anna hetzte Hanna" ist ein Palindrom**   
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcpy, wcscpy, \_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)