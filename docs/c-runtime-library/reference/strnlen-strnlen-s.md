---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
dev_langs:
- C++
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
caps.latest.revision: 35
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: f7cba068af7ec6f14970d174d2b3e9b4121d7c40
ms.lasthandoff: 02/24/2017

---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
Ruft die Länge einer Zeichenfolge durch Verwendung des aktuellen oder einen übergebenen Gebietsschemas ab. Dies sind sicherere Versionen von [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).  
  
> [!IMPORTANT]
>  `_mbsnlen`, `_mbsnlen_l`, `_mbstrnlen` und `_mbstrnlen_l` können nicht in Anwendungen eingesetzt werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t strnlen(  
   const char *str,  
   size_t numberOfElements   
);  
size_t strnlen_s(  
   const char *str,  
   size_t numberOfElements   
);  
size_t wcsnlen(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t wcsnlen_s(  
   const wchar_t *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen(  
   const unsigned char *str,  
   size_t numberOfElements  
);  
size_t _mbsnlen_l(  
   const unsigned char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
size_t _mbstrnlen(  
   const char *str,  
   size_t numberOfElements  
);  
size_t _mbstrnlen_l(  
   const char *str,  
   size_t numberOfElements,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `str`  
 Mit NULL endende Zeichenfolge.  
  
 `numberOfElements`  
 Die Größe des Zeichenfolgenpuffers.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Funktionen geben die Anzahl von Zeichen in der Zeichenfolge zurück (ohne das abschließende Nullzeichen). Wenn in den ersten `numberOfElements` Bytes der Zeichenfolge (oder Breitzeichen für `wcsnlen`) kein NULL-Terminator auftritt, wird `numberOfElements` zurückgegeben, um den Fehlerzustand anzuzeigen; Zeichenfolgen mit NULL-Terminatoren sind in jedem Falle kürzer als `numberOfElements`.  
  
 `_mbstrnlen` und `_mbstrnlen_l` geben -1 zurück, wenn die Zeichenfolge ein ungültiges Multibytezeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  `strnlen` ist kein Ersatz für `strlen`; `strnlen` ist nur für eine Verwendung zur Berechnung der Größe nicht vertrauenswürdiger eingehender Daten in einem Puffer von bekannter Größe gedacht – z. B. eines Netzwerkpakets. `strnlen` berechnet die Länge, geht jedoch nicht hinter das Ende des Puffers zurück, wenn die Zeichenfolge keinen Terminator aufweist. Verwenden Sie in anderen Situationen `strlen`. (Dasselbe gilt für `wcsnlen`, `_mbsnlen` und `_mbstrnlen`.)  
  
 Jede dieser Funktionen gibt die Anzahl von Zeichen in `str` zurück, jedoch ohne das NULL-Terminatorzeichen. `strnlen` und `strnlen_s` interpretieren die Zeichenfolge allerdings als Einzelbytezeichenfolge, sodass der Rückgabewert immer der Anzahl von Bytes entspricht, selbst wenn die Zeichenfolge Multibytezeichen enthält. `wcsnlen` und `wcsnlen_s` sind Breitzeichenversionen von `strnlen` bzw. `strnlen_s`; die Argumente für `wcsnlen` und `wcsnlen_s` sind Breitzeichen-Zeichenfolgen, und die Zeichenzählung erfolgt in Breitzeicheneinheiten. Andernfalls verhalten sich `wcsnlen` und `strnlen` identisch, ebenso `strnlen_s` und `wcsnlen_s`.  
  
 `strnlen`, `wcsnlen,` und `_mbsnlen` überprüfen ihre Parameter nicht. Wenn `str` gleich `NULL` ist, tritt eine Zugriffsverletzung auf.  
  
 `strnlen_s` und `wcsnlen_s` überprüfen die eigenen Parameter. Wenn `str` gleich `NULL` ist, geben die Funktionen 0 zurück.  
  
 `_mbstrnlen` überprüft auch die eigenen Parameter. Wenn `str` gleich `NULL` oder wenn `numberOfElements` größer als `INT_MAX` ist, generiert `_mbstrnlen` eine Ausnahme wegen eines ungültigen Parameters, wie unter [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, setzt `_mbstrnlen` `errno` auf `EINVAL` und gibt -1 zurück.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsnlen`|`strnlen`|`strnlen`|`wcsnlen`|  
|`_tcscnlen`|`strnlen`|`_mbsnlen`|`wcsnlen`|  
|`_tcscnlen_l`|`strnlen`|`_mbsnlen_l`|`wcsnlen`|  
  
 `_mbsnlen` und `_mbstrnlen` geben die Anzahl von Multibytezeichen in einer Multibytezeichenfolge zurück. `_mbsnlen` erkennt Multibytezeichensequenzen anhand der Multibyte-Codepage, die aktuell in Verwendung ist, oder anhand des übergebenen Gebietsschemas, überprüft jedoch nicht die Gültigkeit der Multibytezeichen. `_mbstrnlen` überprüft die Gültigkeit von Multibytezeichen und erkennt Multibytezeichensequenzen. Wenn die an `_mbstrnlen` übergebene Zeichenfolge ein ungültiges Multibytezeichen enthält, wird `errno` auf `EILSEQ` gesetzt.  
  
 Der Ausgabewert ist von der `LC_CTYPE`-Kategorieneinstellung des Gebietsschemas betroffen; weitere Informationen finden Sie unter [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Die Versionen dieser Funktionen sind nahezu identisch, außer dass diejenigen ohne das `_l`-Suffix für dieses Gebietsschema-abhängige Verhalten das aktuelle Gebietsschema verwenden, und diejenigen mit `_l`-Suffix den übergebenen Gebietsschemaparameter. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`strnlen`, `strnlen_s`|\<string.h>|  
|`wcsnlen`, `wcsnlen_s`|\<string.h> oder \<wchar.h>|  
|`_mbsnlen`, `_mbsnlen_l`|\<mbstring.h>|  
|`_mbstrnlen`, `_mbstrnlen_l`|\<stdlib.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
  
```  
  
      // crt_strnlen.c  
  
#include <string.h>  
  
int main()  
{  
   // str1 is 82 characters long. str2 is 159 characters long   
  
   char* str1 = "The length of a string is the number of characters\n"  
               "excluding the terminating null.";  
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"  
                "than the maximum size specified, the maximum size is\n"  
                "returned rather than the actual size of the string.";  
   size_t len;  
   size_t maxsize = 100;  
  
   len = strnlen(str1, maxsize);  
   printf("%s\n Length: %d \n\n", str1, len);  
  
   len = strnlen(str2, maxsize);  
   printf("%s\n Length: %d \n", str2, len);  
}  
```  
  
```Output  
The length of a string is the number of characters  
excluding the terminating null.  
 Length: 82   
  
strnlen takes a maximum size. If the string is longer  
than the maximum size specified, the maximum size is  
returned rather than the actual size of the string.  
 Length: 100   
```  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 [System::String::Length](https://msdn.microsoft.com/en-us/library/system.string.length.aspx)  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [Locale](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
