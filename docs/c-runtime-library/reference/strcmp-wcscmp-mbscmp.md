---
title: strcmp, wcscmp, _mbscmp | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wcscmp
- _mbscmp
- strcmp
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _mbscmp
- wcscmp
- strcmp
- _tcscmp
- _ftcscmp
dev_langs:
- C++
helpviewer_keywords:
- tcscmp function
- strcmp function
- strings [C++], comparing
- mbscmp function
- string comparison [C++]
- _mbscmp function
- wcscmp function
- _tcscmp function
- _ftcscmp function
- ftcscmp function
ms.assetid: 5d216b57-7a5c-4cb3-abf0-0f4facf4396d
caps.latest.revision: ''
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: addc2c215d0c914e3caee3dba4d32f94ca91e62c
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="strcmp-wcscmp-mbscmp"></a>strcmp, wcscmp, _mbscmp
Vergleichen von Zeichenfolgen  
  
> [!IMPORTANT]
>  `_mbscmp` kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int strcmp(  
   const char *string1,  
   const char *string2   
);  
int wcscmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbscmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `string1`, `string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert für jede dieser Funktionen gibt die Ordinalbeziehung von `string1` zu `string2` an.  
  
|Wert|Verhältnis von string1 zu string2|  
|-----------|----------------------------------------|  
|< 0|`string1` ist kleiner als `string2`|  
|0|`string1` ist identisch mit `string2`|  
|> 0|`string1` ist größer als `string2`|  
  
 Bei einem Parameterüberprüfungsfehler gibt `_mbscmp` `_NLSCMPERROR` zurück, was in \<string.h> und \<mbstring.h> definiert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `strcmp`-Funktion führt einen Ordinalvergleich von `string1` und `string2` durch und gibt einen Wert, der die Beziehung angibt. `wcscmp` und `_mbscmp` sind Breitzeichen- bzw. Multibytezeichenversionen von `strcmp`. `_mbscmp` erkennt Multibyte-Zeichenfolgen entsprechend der aktuellen Multibyte-Codepage und gibt bei einem Fehler `_NLSCMPERROR` zurück. Weitere Informationen finden Sie unter [Codepages](../../c-runtime-library/code-pages.md). Wenn `string1` oder `string2` ein NULL-Zeiger ist, ruft `_mbscmp`, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, den Handler für ungültige Parameter auf. Wenn die weitere Ausführung zugelassen wird, gibt `_mbscmp` `_NLSCMPERROR` zurück und setzt `errno` auf `EINVAL`. `strcmp` und `wcscmp` überprüfen ihre Parameter nicht. Diese drei Funktionen verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcscmp`|`strcmp`|`_mbscmp`|`wcscmp`|  
  
 Die `strcmp`-Funktionen unterscheiden sich von den `strcoll`-Funktionen dahingehend, dass die `strcmp`-Vergleiche ordinal sind und nicht vom Gebietsschema beeinflusst werden. `strcoll` vergleicht Zeichenfolgen lexikografisch mithilfe der `LC_COLLATE`-Kategorie des aktuellen Gebietsschemas. Weitere Informationen über die `LC_COLLATE`-Kategorie finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Im Gebietsschema "C" ist die Reihenfolge der Zeichen im Zeichensatz (ASCII-Zeichensatz) die gleiche wie die lexikografische Zeichenreihenfolge. In anderen Gebietsschemata kann die Reihenfolge der Zeichen im Zeichensatz jedoch von der lexikografischen Reihenfolge abweichen. In bestimmten europäischen Gebietsschemas steht im Zeichensatz das Zeichen "a" (Wert 0x61) vor dem Zeichen "ä" (Wert 0xE4), das Zeichen "ä" steht jedoch lexikografisch gesehen jedoch vor dem Zeichen "a".  
  
 In Gebietsschemas, für die der Zeichensatz und die lexikografische Zeichenreihenfolge unterschiedlich sind, können Sie `strcoll` anstelle von `strcmp` für den lexikografischen Vergleich von Zeichenfolgen verwenden. Sie können auch `strxfrm` für die ursprünglichen Zeichenfolgen verwenden und dann `strcmp` für die resultierenden Zeichenfolgen verwenden.  
  
 Bei den `strcmp`-Funktionen wird die Groß-/Kleinschreibung beachtet. `_stricmp`, `_wcsicmp` und `_mbsicmp` vergleichen Zeichenfolgen, indem sie sie zuerst in Kleinbuchstaben konvertieren. Abhängig von der Großschreibung ist der Vergleich von zwei Zeichenfolgen mit Zeichen zwischen „Z“ und „a““ in der ASCII-Tabelle ('[', '`\`', ']', '`^`', '`_`' und '```') unterschiedlich. Beispielsweise werden die beiden Zeichenfolgen `"ABCDE"` und `"ABCD^"` in eine Richtung verglichen, wenn Kleinschreibung vorliegt (`"abcde"` > `"abcd^"`) und in die andere Richtung, wenn Großschreibung vorliegt (`"ABCDE"` < `"ABCD^"`).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`strcmp`|<string.h>|  
|`wcscmp`|<string.h> oder <wchar.h>|  
|`_mbscmp`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_strcmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof (tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof (tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof (tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp, _memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)