---
title: strstr, wcsstr, _mbsstr, _mbsstr_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsstr
- wcsstr
- _mbsstr_l
- strstr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrstr
- _ftcsstr
- strstr
- wcsstr
- _mbsstr
- _tcsstr
dev_langs: C++
helpviewer_keywords:
- strings [C++], searching
- mbsstr function
- _ftcsstr function
- ftcsstr function
- fstrstr function
- _tcsstr function
- substrings, finding
- mbsstr_l function
- tcsstr function
- _mbsstr function
- wcsstr function
- _fstrstr function
- _mbsstr_l function
- strstr function
ms.assetid: 03d70c3f-2473-45cb-a5f8-b35beeb2748a
caps.latest.revision: "32"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2d67a57a698fdc4069c2de15520e014c7c3491e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strstr-wcsstr-mbsstr-mbsstrl"></a>strstr, wcsstr, _mbsstr, _mbsstr_l
Gibt einen Zeiger auf das erste Vorkommen einer Suchzeichenfolge in einer Zeichenfolge zurück.  
  
> [!IMPORTANT]
>  `_mbsstr` und `_mbsstr_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Zu suchende mit NULL endende Zeichenfolge.  
  
 `strSearch`  
 Zu suchende mit NULL endende Zeichenfolge.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das erste Vorkommen von `strSearch` in `str` zurück, oder `NULL`, wenn `strSearch` in `str` nicht angezeigt wird. Wenn `strSearch` auf eine Zeichenfolge der Länge 0 (Null) zeigt wird, gibt die Funktion `str` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `strstr`-Funktion gibt einen Zeiger auf das erste Vorkommen von `strSearch` in `str` zurück. Die Suche umfasst keine abschließenden Nullzeichen. `wcsstr` ist die Breitzeichenversion von `strstr`, und `_mbsstr` ist die Multibytezeichenversion. Die Argumente und der Rückgabewert von `wcsstr` sind Breitzeichen-Zeichenfolgen; die von `_mbsstr` sind Mehrbyte-Zeichenfolgen. `_mbsstr` überprüft die eigenen Parameter. Wenn `str` oder `strSearch` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt `_mbsstr``errno` auf `EINVAL` fest und gibt 0 zurück. `strstr` und `wcsstr` überprüfen ihre Parameter nicht. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
> [!IMPORTANT]
>  Diese Funktionen können eine Bedrohung aufgrund eines Pufferüberlaufproblems darstellen. Pufferüberlaufprobleme können für Angriffe auf ein System eingesetzt werden, da sie die Ausführung von willkürlichem Code ermöglichen können, was zur einer unbefugten Ausweitung der Berechtigungen führen kann. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 In C akzeptieren diese Funktionen einen `const`-Zeiger als erstes Argument. In C++ sind zwei Überladungen verfügbar. Die Überladung, die einen Zeiger auf `const` akzeptiert, gibt einen Zeiger auf `const` zurück, und die Version, die einen Zeiger auf Nicht-`const` akzeptiert, gibt einen Zeiger auf Nicht-`const` zurück. Das Makro `_CRT_CONST_CORRECT_OVERLOADS` wird definiert, wenn sowohl die `const` und nicht-`const` Versionen dieser Funktionen sind verfügbar. Wenn Sie das nicht-`const` -Verhalten für beide C++-Überladungen, definieren Sie das Symbol `_CONST_RETURN`.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen, die das `_l`-Suffix nicht verwenden, verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsstr`|`strstr`|`_mbsstr`|`wcsstr`|  
|**n/v**|**n/v**|`_mbsstr_l`|**n/v**|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strstr`|\<string.h>|  
|`wcsstr`|\<string.h> oder \<wchar.h>|  
|`_mbsstr`, `_mbsstr_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```C  
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
  
```Output  
String to be searched:  
   The quick brown dog jumps over the lazy fox  
            1         2         3         4         5  
   12345678901234567890123456789012345678901234567890  
  
lazy found at position 36  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [basic_string::find](../../standard-library/basic-string-class.md#find)  
