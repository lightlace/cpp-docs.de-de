---
title: _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcsnicmp
- _strnicmp_l
- _wcsnicmp_l
- _strnicmp
- _mbsnicmp
- _mbsnicmp_l
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
- wcsnicmp_l
- _strnicmp
- _ftcsnicmp
- mbsnicmp_l
- _ftcsncicmp
- mbsnicmp
- _tcsncicmp
- _mbsnicmp
- _tcsnicmp
- strnicmp_l
- _wcsnicmp
- _wcsnicmp_l
- CORECRT_WSTRING/_wcsnicmp
- CORECRT_WSTRING/_wcsnicmp_l
- string/_strnicmp
- string/_strnicmp_l
dev_langs: C++
helpviewer_keywords:
- tcsnicmp function
- _tcsncicmp function
- _mbsnicmp_l function
- mbsnicmp_l function
- wcsnicmp_l function
- wcsnicmp function
- string comparison [C++], lowercase
- ftcsnicmp function
- strnicmp_l function
- strncmp function
- _strnicmp function
- strings [C++], comparing characters of
- _wcsnicmp_l function
- tcsncicmp function
- string comparison [C++], strncmp function
- _mbsnicmp function
- ftcsncicmp function
- _tcsnicmp function
- _ftcsncicmp function
- _strnicmp_l function
- _ftcsnicmp function
- characters [C++], comparing
- mbsnicmp function
- _wcsnicmp function
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c926c23553545a76bc8e1d0a0427c20ea65f3156
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="strnicmp-wcsnicmp-mbsnicmp-strnicmpl-wcsnicmpl-mbsnicmpl"></a>_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
Vergleicht die angegebene Anzahl von Zeichen zweier Zeichenfolgen ohne Berücksichtigung von Groß-/Kleinbuchstaben.  
  
> [!IMPORTANT]
>  `_mbsnicmp` und `_mbsnicmp_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _strnicmp(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsnicmp(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsnicmp(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strnicmp_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsnicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsnicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `count`  
 Anzahl der zu vergleichenden Zeichen.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt die Beziehung zwischen den untergeordneten Zeichenfolgen wie folgt an.  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|< 0|Die untergeordnete Zeichenfolge `string1` ist kleiner als die untergeordnete Zeichenfolge `string2`.|  
|0|Die untergeordnete Zeichenfolge `string1` ist mit der untergeordneten Zeichenfolge `string2` identisch.|  
|> 0|Die untergeordnete Zeichenfolge `string1` ist größer als die untergeordnete Zeichenfolge `string2`.|  
  
 Bei einem Parameterüberprüfungsfehler geben diese Funktionen `_NLSCMPERROR` zurück (definiert in \<string.h> und \<mbstring.h>).  
  
## <a name="remarks"></a>Hinweise  
 Die `_strnicmp`-Funktion vergleicht ordinal höchstens die ersten `count` Zeichen von `string1` und `string2`. Der Vergleich erfolgt ohne Berücksichtigung der Groß-/Kleinschreibung, indem jedes Zeichen in Kleinbuchstaben konvertiert wird. `_strnicmp` ist eine Version von `strncmp` ohne Berücksichtigung von Groß- und Kleinschreibung. Der Vergleich endet, wenn in jeder Zeichenfolge beendende NULL-Zeichen erreicht wird, bevor `count` Zeichen verglichen wurden. Wenn beim Erreichen des beendenden NULL-Zeichens die Zeichenfolgen gleich sind, bevor `count` Zeichen verglichen wurden, ist die kürzere Zeichenfolge kleiner.  
  
 Die Zeichen von 91 bis 96 in der ASCII-Tabelle ('[', '\\', ']', '^', '_' und '\`') werden als kleiner als jedes beliebige alphabetische Zeichen ausgewertet. Diese Reihenfolge ist identisch mit der von `stricmp`.  
  
 `_wcsnicmp` und `_mbsnicmp` sind Breitzeichen- und Multibytezeichenversionen von `_strnicmp`. Die Argumente von `_wcsnicmp` sind Breitzeichen-Zeichenfolgen, die von `_mbsnicmp` sind Multibyte-Zeichenfolgen. `_mbsnicmp` erkennt Multibyte-Zeichenfolgen entsprechend der aktuellen Multibyte-Codepage und gibt bei einem Fehler `_NLSCMPERROR` zurück. Weitere Informationen finden Sie unter [Codepages](../../c-runtime-library/code-pages.md). Diese drei Funktionen verhalten sich andernfalls identisch. Diese Funktionen werden von der Gebietsschemaeinstellung beeinflusst: Die Versionen, die nicht über die `_l`-Suffix verfügen, verwenden das aktuelle Gebietsschema für ihr gebietsschemaabhängiges Verhalten, und die Versionen mit `_l`-Suffix verwenden stattdessen `locale`, das übergeben wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Mit allen diesen Funktionen werden ihre Parameter überprüft. Wenn `string1` oder `string2` ein NULL-Zeiger ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsncicmp`|`_strnicmp`|`_mbsnicmp`|`_wcsnicmp`|  
|`_tcsnicmp`|`_strnicmp`|`_mbsnbicmp`|`_wcsnicmp`|  
|`_tcsncicmp_l`|`_strnicmp_l`|`_mbsnicmp_l`|`_wcsnicmp_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_strnicmp`, `_strnicmp_l`|<string.h>|  
|`_wcsnicmp`, `_wcsnicmp_l`|<string.h> oder <wchar.h>|  
|`_mbsnicmp`, `_mbsnicmp_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [strncmp](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strcat, wcscat, _mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)