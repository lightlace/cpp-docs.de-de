---
title: "_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_mbsnbcnt_l"
  - "_mbsnccnt"
  - "_wcsncnt"
  - "_strncnt"
  - "_mbsnccnt_l"
  - "_mbsnbcnt"
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
  - "_mbsnbcnt"
  - "wcsncnt"
  - "_tcsnbcnt"
  - "_mbsnccnt"
  - "_ftcsnbcnt"
  - "mbsnbcnt"
  - "strncnt"
  - "mbsnbcnt_l"
  - "mbsnccnt_l"
  - "mbsnccnt"
  - "_strncnt"
  - "_wcsncnt"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbcnt-Funktion"
  - "_mbsnbcnt_l-Funktion"
  - "_mbsnccnt-Funktion"
  - "_mbsnccnt_l-Funktion"
  - "_strncnt-Funktion"
  - "_tcsnbcnt-Funktion"
  - "_wcsncnt-Funktion"
  - "mbsnbcnt-Funktion"
  - "mbsnbcnt_l-Funktion"
  - "mbsnccnt-Funktion"
  - "mbsnccnt_l-Funktion"
  - "strncnt-Funktion"
  - "tcsnbcnt-Funktion"
  - "wcsncnt-Funktion"
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt die Anzahl von Bytes oder Zeichen innerhalb einer angegebenen Zählers zurück.  
  
> [!IMPORTANT]
>  `_mbsnbcnt`, `_mbsnbcnt_l`, `_mbsnccnt` und `_mbsnccnt_l` können nicht in Anwendungen eingesetzt werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
size_t _strncnt(  
   const char *str,  
   size_t count  
);  
size_t _wcsncnt(  
   const wchar_t *str,  
   size_t count  
);  
size_t _mbsnbcnt(  
   const unsigned char *str,  
   size_t count   
);  
size_t _mbsnbcnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
size_t _mbsnccnt(  
   const unsigned char *str,  
   size_t count  
);  
size_t _mbsnccnt_l(  
   const unsigned char *str,  
   size_t count,  
   _locale_t locale  
);  
  
```  
  
#### Parameter  
 `str`  
 Zu untersuchende Zeichenfolge.  
  
 `count`  
 Anzahl von Zeichen oder Bytes, die in `str` zu untersuchen sind.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## Rückgabewert  
 `_mbsnbcnt` und `_mbsnbcnt_l` geben die Anzahl von Bytes zurück, die im ersten `count` eines Multibytezeichens von `str` gefunden werden.  `_mbsnccnt` und `_mbsnccnt_l` geben die Anzahl von Zeichen zurück, die im ersten `count` der Bytes von `str` gefunden werden.  Wenn ein NULL\-Zeichen erreicht wird, bevor die Überprüfung von `str` abgeschlossen ist, geben sie die Anzahl von Bytes oder Zeichen zurück, die vor dem NULL\-Zeichen gefunden werden.  Wenn `str` aus weniger als `count` Zeichen oder Bytes besteht, geben sie die Anzahl von Bytes oder Zeichen in der Zeichenfolge zurück.  Wenn `count` kleiner als null ist, geben sie 0 zurück.  In früheren Versionen hatten diese Funktionen einen Rückgabewert vom Typ `int` statt `size_t`.  
  
 `_strncnt` gibt die Anzahl von Zeichen in den ersten `count` Bytes der Einzelbytezeichenfolge `str` zurück.  `_wcsncnt` gibt die Anzahl von Zeichen in den ersten `count` Breitzeichen der Breitzeichenfolge `str` zurück.  
  
## Hinweise  
 `_mbsnbcnt` und `_mbsnbcnt_l` zählen die Anzahl von Bytes, die im ersten `count` eines Multibytezeichens von `str` gefunden werden.  `_mbsnbcnt` und `_mbsnbcnt_l` ersetzen `mtob` und sollten anstelle von `mtob` verwendet werden.  
  
 `_mbsnccnt` und `_mbsnccnt_l` zählen die Anzahl von Zeichen, die im ersten `count` der Bytes von `str` gefunden werden.  Wenn `_mbsnccnt` und `_mbsnccnt_l` eine NULL im zweiten Byte eines Doppelbytezeichens entdecken, wird das erste Byte auch als NULL betrachtet und ist nicht im zurückgegebenen Zählwert enthalten.  `_mbsnccnt` und `_mbsnccnt_l` ersetzen `btom` und sollten anstelle von `btom` verwendet werden.  
  
 Wenn `str` ein NULL\-Zeiger ist oder wenn `count` 0 ist, rufen diese Funktionen den Handler für ungültige Parameter auf, wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. `errno` wird auf `EINVAL` gesetzt, und die Funktion gibt 0 zurück.  
  
 Der Ausgabewert ist von der `LC_CTYPE`\-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  Die Versionen dieser Funktionen ohne das `_l`\-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`\-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter.  Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### Zuordnung generischer Textroutinen  
  
|Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|-------------|------------------------------------------|----------------------|-------------------------|  
|`_tcsnbcnt`|`_strncnt`|`_mbsnbcnt`|`_wcsncnt`|  
|`_tcsnccnt`|`_strncnt`|`_mbsnbcnt`|`n/a`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnbcnt`|  
|`_wcsncnt`|`n/a`|`n/a`|`_mbsnccnt`|  
|`n/a`|`n/a`|`_mbsnbcnt_l`|`_mbsnccnt_l`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_mbsnbcnt`|\<mbstring.h\>|  
|`_mbsnbcnt_l`|\<mbstring.h\>|  
|`_mbsnccnt`|\<mbstring.h\>|  
|`_mbsnccnt_l`|\<mbstring.h\>|  
|`_strncnt`|\<tchar.h\>|  
|`_wcsncnt`|\<tchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
  
```  
// crt_mbsnbcnt.c  
  
#include  <mbstring.h>  
#include  <stdio.h>  
  
int main( void )  
{  
   unsigned char str[] = "This is a multibyte-character string.";  
   unsigned int char_count, byte_count;  
   char_count = _mbsnccnt( str, 10 );  
   byte_count = _mbsnbcnt( str, 10 );  
   if ( byte_count - char_count )  
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );  
   else  
      printf( "The first 10 characters are single-byte.\n");  
}  
```  
  
## Ausgabe  
  
```  
The first 10 characters are single-byte.  
```  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Mehrbytezeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbsnbcat, \_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)