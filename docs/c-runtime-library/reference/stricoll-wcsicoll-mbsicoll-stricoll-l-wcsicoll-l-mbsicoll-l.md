---
title: _stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsicoll_l
- _stricoll_l
- _mbsicoll
- _wcsicoll_l
- _wcsicoll
- _stricoll
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
- stricoll
- _stricoll
- _wcsicoll
- mbsicoll_l
- _mbsicoll
- _ftcsicoll
- wcsicoll_l
- _tcsicoll
- mbsicoll
- stricoll_l
dev_langs:
- C++
helpviewer_keywords:
- code pages, using for string comparisons
- _ftcsicoll function
- _mbsicoll_l function
- _mbsicoll function
- mbsicoll function
- stricoll function
- tcsicoll function
- string comparison [C++], culture-specific
- _tcsicoll function
- _stricoll function
- _stricoll_l function
- _wcsicoll function
- mbsicoll_l function
- stricoll_l function
- strings [C++], comparing by code page
- ftcsicoll function
ms.assetid: 8ec93016-5a49-49d2-930f-721566661d82
caps.latest.revision: 22
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
ms.openlocfilehash: 4291a8027dd01c705642af0d3651cc2fbf1277cb
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="stricoll-wcsicoll-mbsicoll-stricolll-wcsicolll-mbsicolll"></a>_stricoll, _wcsicoll, _mbsicoll, _stricoll_l, _wcsicoll_l, _mbsicoll_l
Vergleicht Zeichenfolgen mithilfe gebietsschemaspezifischen Informationen.  
  
> [!IMPORTANT]
>  `_mbsicoll` und `_mbsicoll_l` können nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _stricoll(  
   const char *string1,  
   const char *string2   
);  
int _wcsicoll(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicoll(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricoll_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `string1, string2`  
 Zu vergleichende mit NULL endende Zeichenfolgen.  
  
 `locale`  
 Das zu verwendende Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Funktionen gibt einen Wert, der angibt, der Beziehung der `string1` auf `string2`wie folgt.  
  
|Rückgabewert|Verhältnis von string1 zu string2|  
|------------------|----------------------------------------|  
|< 0|`string1` kleiner als `string2`|  
|0|`string1` identisch mit `string2`|  
|> 0|`string1` größer als `string2`|  
|`_NLSCMPERROR`|Es ist ein Fehler aufgetreten.|  
  
 Jede dieser Funktion gibt `_NLSCMPERROR` zurück. Um `_NLSCMPERROR` zu verwenden, nehmen Sie entweder `STRING.H` oder `MBSTRING.H` auf. `_wcsicoll` kann fehlschlagen, wenn `string1` oder `string2` NULL ist oder Codes mit Breitzeichen außerhalb der Domäne der Sortierreihenfolge enthält. Wenn ein Fehler auftritt, legt `_wcsicoll``errno` möglicherweise auf `EINVAL` fest. Um einen Aufruf von `_wcsicoll` auf einen Fehler zu überprüfen, legen Sie `errno` auf 0 fest, und überprüfen Sie dann `errno`, nachdem Sie `_wcsicoll` aufgerufen haben.  
  
## <a name="remarks"></a>Hinweise  
 Jede dieser Funktionen vergleicht `string1` und `string2` ohne Beachtung der Groß-/Kleinschreibung entsprechend der derzeit verwendeten Codepage. Diese Funktionen sollten nur verwendet werden, wenn es in der aktuellen Codepage einen Unterschied zwischen der Reihenfolge des Zeichensatzes und der lexikografischen Reihenfolge gibt, und dieser Unterschied für den Zeichenfolgenvergleich relevant ist.  
  
 `_stricmp` unterscheidet sich dadurch von `_stricoll`, dass der `_stricmp`-Vergleich von `LC_CTYPE` beeinflusst wird, während der `_stricoll`-Vergleich den `LC_CTYPE`- und `LC_COLLATE`-Kategorien des Gebietsschemas entspricht. Weitere Informationen zur `LC_COLLATE`-Kategorie finden Sie unter [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) und [Gebietsschemakategorien](../../c-runtime-library/locale-categories.md). Die Versionen dieser Funktionen ohne das `_l`-Suffix verwenden das aktuelle Gebietsschema. Die Versionen mit dem `_l`-Suffix sind beinahe identisch, verwenden jedoch stattdessen das ihnen übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Mit allen diesen Funktionen werden ihre Parameter überprüft. Wenn entweder `string1` oder `string2` `NULL`-Zeiger ist, wird, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben, der Handler für ungültige Parameter aufgerufen. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `_NLSCMPERROR` zurück und stellen `errno` auf `EINVAL` ein.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsicoll`|`_stricoll`|`_mbsicoll`|`_wcsicoll`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_stricoll`, `_stricoll_l`|\<string.h>|  
|`_wcsicoll`, `_wcsicoll_l`|\<wchar.h>, \<string.h>|  
|`_mbsicoll`, `_mbsicoll_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)
