---
title: strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
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
dev_langs: C++
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
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5d5b92497bedcfd766975e62c886dd64676fc71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strtoks-strtoksl-wcstoks-wcstoksl-mbstoks-mbstoksl"></a>strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l

Sucht das nächste Token in einer Zeichenfolge unter Verwendung des aktuellen Gebietsschemas oder eines Gebietsschemas, das übergeben wird. Diese Versionen von [strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l](../../c-runtime-library/reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) enthalten Sicherheitsverbesserungen, wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  `_mbstok_s` und `_mbstok_s_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```
char* strtok_s(  
   char* str,  
   const char* delimiters,  
   char** context  
);

char* _strtok_s_l(  
   char* str,  
   const char* delimiters,  
   char** context,  
   _locale_t locale  
);  

wchar_t* wcstok_s(  
   wchar_t* str,  
   const wchar_t* delimiters,   
   wchar_t** context  
); 
 
wchar_t *_wcstok_s_l(  
   wchar_t* str,  
   const wchar_t* delimiters,   
   wchar_t** context,  
   _locale_t locale  
);  

unsigned char* _mbstok_s(  
   unsigned char* str,  
   const unsigned char* delimiters,   
   char** context  
);  

unsigned char* _mbstok_s(  
   unsigned char* str,  
   const unsigned char* delimiters,   
   char** context,  
   _locale_t locale  
);  
```  
  
### <a name="parameters"></a>Parameter  

*str*  
Eine Zeichenfolge mit dem mindestens ein Token gefunden.  
  
*Trennzeichen*  
Der Satz von Trennzeichen, die zu verwendenden Zeichen.  
  
*Kontext*  
Verwendet, um Positionsinformationen zwischen Aufrufen an die Funktion zu speichern.  
  
*locale*  
Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  

Gibt einen Zeiger auf das nächste Token in gefunden *str*. Gibt `NULL` Wenn keine weiteren Token gefunden werden. Jeder Aufruf ändert *str* durch das Ersetzen einer `NULL` Zeichen für Trennzeichen, das nach dem zurückgegebenen Token auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|*str*|*Trennzeichen*|*Kontext*|Rückgabewert|`errno`|  
|----------------|------------------|---------------|------------------|-------------|  
|`NULL`|any|Zeiger auf einen NULL-Zeiger|`NULL`|`EINVAL`|  
|any|`NULL`|any|`NULL`|`EINVAL`|  
|any|any|`NULL`|`NULL`|`EINVAL`|  
  
Wenn *str* ist `NULL` jedoch *Kontext* ist ein Zeiger auf einen gültigen Kontextzeiger kein Fehler vorliegt.  
  
## <a name="remarks"></a>Hinweise  

Die `strtok_s` Funktionsreihe sucht das nächste Token in *str*. Der Satz von Zeichen im *Trennzeichen* gibt mögliche Trennzeichen des Tokens in gefunden werden *str* für den aktuellen Aufruf. `wcstok_s` und `_mbstok_s` sind Breitzeichen- und Multibytezeichenversionen von `strtok_s`. Die Argumente und Rückgabewerte von `wcstok_s` und `_wcstok_s_l` sind Breitzeichenzeichenfolgen; die von `_mbstok_s` and `_mbstok_s_l` sind Multibyte-Zeichenfolgen. Anderenfalls verhalten sich diese Funktionen identisch.  

Diese Funktion überprüft ihre Parameter. Wenn ein Fehlerzustand gemäß der Fehlerzustandstabelle auftritt, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `NULL` zurück.

Beim ersten Aufruf von `strtok_s` die Funktion vorangestellte Trennzeichen überspringt und gibt einen Zeiger auf das erste Token in *str*, beendet das Token mit einem Null-Zeichen. Weitere Token können der Rest des geholt werden *str* durch eine Reihe von Aufrufen an `strtok_s`. Jeder Aufruf von `strtok_s` ändert *str* durch ein Null-Zeichen nach dem zurückgegebenen Token einfügt. Die *Kontext* -Zeiger erfasst, aus welcher Zeichenfolge gelesen wird und, in dem in der Zeichenfolge das nächste Token gelesen werden. Lesen Sie das nächste Token von *str*, Aufrufen `strtok_s` mit einer `NULL` Wert für die *str* Argument, und übergeben Sie den gleichen *Kontext* Parameter. Die `NULL` *str* Argument bewirkt, dass `strtok_s` , suchen Sie nach dem nächsten Token im geänderten *str*. Die *Trennzeichen* Argument kann jeden beliebigen Wert annehmen zwischen zwei aufrufen zur nächsten, damit der Satz von Trennzeichen variieren kann.

Da die *Kontext* Parameter hat Vorrang vor der im verwendeten statischen Puffer `strtok` und `_strtok_l`, es ist möglich, zwei Zeichenfolgen im gleichen Thread gleichzeitig analysiert werden.

Der Ausgabewert ist von der `LC_CTYPE`-Kategorieeinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen ohne das `_l` -Suffix verwenden das aktuelle Gebietsschema des Threads für dieses vom Gebietsschema abhängiges Verhalten. Die Versionen mit dem `_l` -Suffix sind beinahe identisch, verwenden jedoch stattdessen den *Gebietsschema* Parameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|`strtok_s`|\<string.h>|
|`_strtok_s_l`|\<string.h>|
|`wcstok_s`,<br />`_wcstok_s_l`|\<string.h> oder \<wchar.h>|
|`_mbstok_s`,<br />`_mbstok_s_l`|\<mbstring.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcstok_s`|`strtok_s`|`_mbstok_s`|`wcstok_s`|
|`_tcstok_s_l`|`_strtok_s_l`|`_mbstok_s_l`|`_wcstok_s_l`|

## <a name="example"></a>Beispiel

```C
// crt_strtok_s.c
// In this program, a loop uses strtok_s
// to print all the tokens (separated by commas
// or blanks) in two strings at the same time.

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

int main(void)
{
    printf("Tokens:\n");

    // Establish string and get the first token:
    token1 = strtok_s(string1, seps, &next_token1);
    token2 = strtok_s(string2, seps, &next_token2);

    // While there are tokens in "string1" or "string2"
    while ((token1 != NULL) || (token2 != NULL))
    {
        // Get next token:
        if (token1 != NULL)
        {
            printf(" %s\n", token1);
            token1 = strtok_s(NULL, seps, &next_token1);
        }
        if (token2 != NULL)
        {
            printf("        %s\n", token2);
            token2 = strtok_s(NULL, seps, &next_token2);
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