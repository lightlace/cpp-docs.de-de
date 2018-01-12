---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs: C++
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 323ee2842799cdfe948bdf0a8af7ec2bfad92439
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l
Durchsucht Zeichenfolgen nach Zeichen in angegebenen Zeichensätzen.  
  
> [!IMPORTANT]
>  `_mbspbrk` und `_mbspbrk_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Auf NULL endende gesuchte Zeichenfolge.  
  
 `strCharSet`  
 Mit NULL endender Zeichensatz.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das erste Vorkommen eines beliebigen Zeichens von `strCharSet` in `str` zurück oder einen `NULL`-Zeiger, wenn zwei Zeichenfolgenargumente über kein gemeinsames Zeichen verfügen.  
  
## <a name="remarks"></a>Hinweise  
 Die `strpbrk`-Funktion gibt einen Zeiger auf das erste Vorkommen eines Zeichens in `str` zurück, das zu dem Zeichensatz in `strCharSet` gehört. Die Suche umfasst nicht das abschließende Nullzeichen.  
  
 `wcspbrk` und `_mbspbrk` sind Breitzeichen- und Multibytezeichenversionen von `strpbrk`. Die Argumente und der Rückgabewert von `wcspbrk` sind Breitzeichen-Zeichenfolgen; die von `_mbspbrk` sind Mehrbyte-Zeichenfolgen.  
  
 `_mbspbrk` überprüft die eigenen Parameter. Wenn `str` oder `strCharSet` `NULL` ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, gibt `_mbspbrk` `NULL` zurück und setzt `errno` auf `EINVAL`. `strpbrk` und `wcspbrk` überprüfen ihre Parameter nicht. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 `_mbspbrk` ähnelt `_mbscspn`, außer dass `_mbspbrk` einen Zeiger anstelle eines Werts vom Typ [size_t](../../c-runtime-library/standard-types.md) zurückgibt.  
  
 In C akzeptieren diese Funktionen einen `const`-Zeiger als erstes Argument. In C++ sind zwei Überladungen verfügbar. Die Überladung, die einen Zeiger zu `const` akzeptiert, gibt einen Zeiger zu `const` zurück; die Version, die einen Zeiger auf Nicht-`const` akzeptiert, gibt einen Zeiger auf Nicht-`const` zurück. Das Makro `_CRT_CONST_CORRECT_OVERLOADS` wird definiert, wenn sowohl die `const` und nicht-`const` Versionen dieser Funktionen sind verfügbar. Wenn Sie das nicht-`const` -Verhalten für beide C++-Überladungen, definieren Sie das Symbol `_CONST_RETURN`.  
  
 Die Ausgabewert ist von der Einstellung der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen. Weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten. Die Version mit dem `_l`-Suffix ist beinahe identisch, verwendet jedoch stattdessen den ihr übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcspbrk`|`strpbrk`|`_mbspbrk`|`wcspbrk`|  
|**n/v**|**n/v**|`_mbspbrk_l`|**n/v**|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`strpbrk`|\<string.h>|  
|`wcspbrk`|\<string.h> oder \<wchar.h>|  
|`_mbspbrk`, `_mbspbrk_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
1: The 3 men and 2 boys ate 5 pigs  
  
2: 3 men and 2 boys ate 5 pigs  
  
3: 2 boys ate 5 pigs  
  
4: 5 pigs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strchr, wcschr, _mbschr, _mbschr_l](../../c-runtime-library/reference/strchr-wcschr-mbschr-mbschr-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)