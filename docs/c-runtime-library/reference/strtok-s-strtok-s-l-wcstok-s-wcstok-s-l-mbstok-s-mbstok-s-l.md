---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstok_s_l
- _mbstok_s_l
- _mbstok_s
- strtok_s
- wcstok_s
- _strtok_s_l
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
- _tcstok_s_l
- _wcstok_s_l
- _tcstok_s
- _mbstok_s_l
- strtok_s
- wcstok_s
- _mbstok_s
- _strtok_s_l
dev_langs:
- C++
helpviewer_keywords:
- _strtok_s_l function
- _mbstok_s_l function
- strings [C++], searching
- mbstok_s_l function
- wcstok_s_l function
- _wcstok_s_l function
- _tcstok_s function
- _tcstok_s_l function
- strtok_s_l function
- wcstok_s function
- tokens, finding in strings
- mbstok_s function
- _mbstok_s function
- strtok_s function
ms.assetid: 7696c972-f83b-4617-8c82-95973e9fdb46
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4313f785ba5197c3659e74384b7d6ecda8e8c7be
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l
Sucht das nächste Token in einer Zeichenfolge unter Verwendung des aktuellen Gebietsschemas oder eines Gebietsschemas, das übergeben wird. Diese Versionen von [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  `_mbstok_s` und `_mbstok_s_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      char *strtok_s(  
char *strToken,  
const char *strDelimit,  
   char **context  
);  
char *_strtok_s_l(  
char *strToken,  
const char *strDelimit,  
   char **context,  
_locale_tlocale  
);  
wchar_t *wcstok_s(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context  
);  
wchar_t *_wcstok_s_l(  
wchar_t *strToken,  
const wchar_t *strDelimit,   
   wchar_t**context,  
_locale_tlocale  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context  
);  
unsigned char *_mbstok_s(  
unsigned char*strToken,  
const unsigned char *strDelimit,   
   char **context,  
_locale_tlocale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `strToken`  
 Zeichenfolge, die mindestens ein Token enthält.  
  
 `strDelimit`  
 Gruppe von Trennzeichen.  
  
 `context`  
 Wird verwendet, um Positionsinformationen zwischen Aufrufen von `strtok_s` zu speichern  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das nächste Token zurück, das in `strToken` gefunden wird. Wenn keine weiteren Token gefunden werden, wird `NULL` zurückgegeben. Jeder Aufruf ändert `strToken`, indem er das Trennzeichen, das nach dem zurückgegebenen Token auftritt, durch ein `NULL`-Zeichen ersetzt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`strToken`|`strDelimit`|`context`|Rückgabewert|`errno`|  
|----------------|------------------|---------------|------------------|-------------|  
|`NULL`|alle|Zeiger auf einen NULL-Zeiger|`NULL`|`EINVAL`|  
|alle|`NULL`|alle|`NULL`|`EINVAL`|  
|alle|alle|`NULL`|`NULL`|`EINVAL`|  
  
 Wenn `strToken``NULL` ist, aber der Kontext ein Zeiger auf einen gültigen Kontextzeiger ist, gibt es keinen Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Die `strtok_s`-Funktion sucht das nächste Token in `strToken`. Der Satz von Zeichen in `strDelimit` gibt mögliche Trennzeichen des in `strToken` gefunden Tokens für den aktuellen Aufruf an. `wcstok_s` und `_mbstok_s` sind Breitzeichen- und Multibytezeichenversionen von `strtok_s`. Die Argumente und Rückgabewerte von `wcstok_s` und `_wcstok_s_l` sind Breitzeichenzeichenfolgen; die von `_mbstok_s` and `_mbstok_s_l` sind Multibyte-Zeichenfolgen. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
 Diese Funktion überprüft ihre Parameter. Wenn ein Fehlerzustand gemäß der Fehlerzustandstabelle auftritt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `NULL` zurück.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|  
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|  
  
 Beim ersten Aufruf von `strtok_s` überspringt die Funktion vorangestellte Trennzeichen, gibt einen Zeiger auf das erste Token in `strToken` zurück und beendet das Token mit einem NULL-Zeichen. Vom restlichen `strToken` können weitere Token durch mehrere Aufrufe von `strtok_s` geholt werden. Jeder Aufruf von `strtok_s` ändert `strToken`, indem er ein NULL-Zeichen nach dem zurückgegebenen Token einfügt. Der `context`-Zeiger erfasst, aus welcher Zeichenfolge gelesen wird und an welcher Stelle in der Zeichenfolge das nächste Token gelesen werden soll. Um das nächste Token von `strToken` zu lesen, rufen Sie `strtok_s` mit einem `NULL`-Wert für das `strToken`-Argument auf, und übergeben Sie den gleichen `context`-Parameter. Das `NULL` `strToken`-Argument bewirkt, dass `strtok_s` im geänderten `strToken` nach dem nächsten Token sucht. Das `strDelimit`-Argument kann zwischen zwei Aufrufen jeden beliebigen Wert annehmen, damit der Satz von Trennzeichen variieren kann.  
  
 Da der `context`-Parameter den in `strtok` und `_strtok_l` verwendeten statischen Puffer ersetzt, können zwei Zeichenfolgen im gleichen Thread gleichzeitig analysiert werden.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema für dieses vom Gebietsschema abhängige Verhalten; die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen den ihnen übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`strtok_s`|\<string.h>|  
|`_strtok_s_l`|\<string.h>|  
|`wcstok_s`,<br /><br /> `_wcstok_s_l`|\<string.h> oder \<wchar.h>|  
|`_mbstok_s`,<br /><br /> `_mbstok_s_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_strtok_s.c  
// In this program, a loop uses strtok_s  
// to print all the tokens (separated by commas  
// or blanks) in two strings at the same time.  
//  
  
#include <string.h>  
#include <stdio.h>  
  
char string1[] =  
    "A string\tof ,,tokens\nand some  more tokens";  
char string2[] =  
    "Another string\n\tparsed at the same time.";  
char seps[]   = " ,\t\n";  
char *token1 = NULL;  
char *token2 = NULL;  
char *next_token1 = NULL;  
char *next_token2 = NULL;  
  
int main( void )  
{  
    printf( "Tokens:\n" );  
  
    // Establish string and get the first token:  
    token1 = strtok_s( string1, seps, &next_token1);  
    token2 = strtok_s ( string2, seps, &next_token2);  
  
    // While there are tokens in "string1" or "string2"  
    while ((token1 != NULL) || (token2 != NULL))  
    {  
        // Get next token:  
        if (token1 != NULL)  
        {  
            printf( " %s\n", token1 );  
            token1 = strtok_s( NULL, seps, &next_token1);  
        }  
        if (token2 != NULL)  
        {  
            printf("        %s\n", token2 );  
            token2 = strtok_s (NULL, seps, &next_token2);  
        }  
    }  
}  
```  
  
```Output  
Tokens:  
 A  
        Another  
 string  
        string  
 of  
        parsed  
 tokens  
        at  
 and  
        the  
 some  
        same  
 more  
        time.  
 tokens  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn, wcscspn, _mbscspn, _mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
